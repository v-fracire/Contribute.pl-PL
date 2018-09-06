---
title: 'Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault | Microsoft Docs'
description: 'Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages, keyvault-platforms
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b758274203748bb6e04c03dec5de38fb77947b4
ms.sourcegitcommit: b0105f322f91bb4dbde47f6da35b3c12271d5b03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43239554"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault

W tym przewodniku Szybki start przedstawiono sposób przechowywania wpisu tajnego w usłudze Key Vault oraz pobierania go przy użyciu aplikacji internetowej. Aby wyświetlić wartość wpisu tajnego, musisz uruchomić ją na platformie Azure. W tym przewodniku Szybki start używana jest platforma Node.js oraz tożsamości usługi zarządzanej (MSI)

> [!div class="checklist"]
> * Tworzenie usługi Key Vault.
> * Przechowywanie wpisu tajnego w usłudze Key Vault.
> * Pobieranie wpisu tajnego z usługi Key Vault.
> * Tworzenie aplikacji internetowej platformy Azure.
> * [Włączanie tożsamości usługi zarządzanej](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * Przyznawanie wymaganych uprawnień w celu umożliwienia aplikacji internetowej odczytu danych z usługi Key Vault.

Przed kontynuowaniem upewnij się, że znasz [podstawowe pojęcia](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).

>[!NOTE]
Aby przekonać się, dlaczego poniższy samouczek jest najlepszym rozwiązaniem, najpierw należy zapoznać się z kilkoma pojęciami. Usługa Key Vault to centralne repozytorium do programistycznego przechowywania wpisów tajnych. W tym celu aplikacje i użytkownicy muszą najpierw uwierzytelnić się w usłudze Key Vault, tj. podać wpis tajny. Zgodnie z najlepszymi rozwiązaniami dotyczącymi bezpieczeństwa pierwszy wpis tajny musi być okresowo obracany. Jednak aplikacje [tożsamości usługi zarządzanej](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) uruchamiane na platformie Azure otrzymują tożsamość, która jest automatycznie zarządzana przez tę platformę. Dzięki temu można rozwiązać **początkowy problem dotyczący wpisu tajnego**, gdzie użytkownicy i aplikacje mogą postępować zgodnie z najlepszymi praktykami i nie muszą pamiętać o obracaniu pierwszego wpisu tajnego

## <a name="prerequisites"></a>Wymagania wstępne

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end

::: zone pivot="dotnet, windows"
* [Visual Studio 2017 w wersji 15.7.3 lub nowszej](https://www.microsoft.com/net/download/windows) z następującymi obciążeniami:
  * Tworzenie aplikacji na platformie ASP.NET i aplikacji internetowej
  * Tworzenie aplikacji dla wielu platform w środowisku .NET Core
* [Zestaw .NET Core 2.1 SDK lub nowszy](https://www.microsoft.com/net/download/windows) :::zone-end

::: zone pivot="dotnet, mac"
* Zobacz [Co nowego w programie Visual Studio dla komputerów Mac](https://visualstudio.microsoft.com/vs/mac/).
:::zone-end

* Git ([pobieranie](https://git-scm.com/downloads)).
* Subskrypcja platformy Azure. Jeśli nie masz subskrypcji platformy Azure, przed rozpoczęciem utwórz [bezpłatne konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
* [Interfejs wiersza polecenia platformy Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) w wersji 2.0.4 lub nowszej. Jest on dostępny w systemach Windows, Mac i Linux.

## <a name="login-to-azure"></a>Logowanie na platformie Azure

Aby zalogować się do platformy Azure przy użyciu interfejsu wiersza polecenia, możesz wpisać:

```azurecli
az login
```

## <a name="create-resource-group"></a>Tworzenie grupy zasobów

Utwórz grupę zasobów za pomocą polecenia [az group create](/cli/azure/group#az-group-create). Grupa zasobów platformy Azure to logiczny kontener przeznaczony do wdrażania zasobów platformy Azure i zarządzania nimi.

Wybierz nazwę grupy zasobów i wypełnij symbol zastępczy.
Poniższy przykład obejmuje tworzenie grupy zasobów o nazwie *<YourResourceGroupName>* w lokalizacji *eastus*.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

W tym samouczku używana jest utworzona teraz grupa zasobów.

## <a name="create-an-azure-key-vault"></a>Tworzenie usługi Azure Key Vault

Następnie utworzysz magazyn Key Vault, wykorzystując grupę zasobów utworzoną w poprzednim kroku. Chociaż w tym artykule jako nazwa magazynu Key Vault używana jest wartość „ContosoKeyVault”, musisz użyć unikatowej nazwy. Podaj następujące informacje:

* Nazwa magazynu — **wybierz tutaj nazwę magazynu Key Vault**.
* Nazwa grupy zasobów — **wybierz tutaj nazwę grupy zasobów**.
* Lokalizacja — **Wschodnie stany USA**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

Twoje konto platformy Azure jest teraz jedynym kontem z uprawnieniami do wykonywania jakichkolwiek operacji na tym nowym magazynie.

## <a name="add-a-secret-to-key-vault"></a>Dodawanie wpisu tajnego do magazynu kluczy

Dodajemy wpis tajny, aby zilustrować, jak to działa. Możesz zapisywać parametry połączenia SQL lub inne informacje, które muszą być przechowywane bezpiecznie, ale jednocześnie być dostępne dla aplikacji. W tym samouczku hasło będzie miało nazwę **AppSecret** i będzie w nim przechowywana wartość **MySecret**.

Wpisz poniższe polecenia, aby w magazynie Key Vault utworzyć wpis tajny o nazwie **AppSecret**, w którym będzie przechowywana wartość **MySecret**:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

Aby wyświetlić wartość zawartą we wpisie tajnym jako zwykły tekst:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

To polecenie powoduje wyświetlenie informacji o wpisie tajnym, w tym identyfikatora URI. Po wykonaniu tych kroków będziesz mieć identyfikator URI wpisu tajnego w usłudze Azure Key Vault. Zanotuj te informacje. Będą one potrzebne w kolejnym kroku.

## <a name="clone-the-repo"></a>Klonowanie repozytorium

Sklonuj repozytorium, aby utworzyć kopię lokalną umożliwiającą edytowanie źródła, przez uruchomienie następującego polecenia:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Instalowanie zależności

W tym miejscu zainstalujemy zależności. Uruchom następujące polecenia cd key-vault-node-quickstart npm install

W tym projekcie używane są 2 moduły platformy node:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>Publikowanie aplikacji internetowej na platformie Azure

Poniżej przedstawiono kilka wymaganych kroków

* Pierwszy krok to utworzenie planu usługi [Azure App Service](https://azure.microsoft.com/services/app-service/). Ten plan pozwala na przechowywanie wielu aplikacji internetowych.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* Następnie utworzymy aplikację internetową. W poniższym przykładzie zastąp ciąg <app_name> globalnie unikatową nazwą aplikacji (prawidłowe znaki to a–z, 0–9 i -). Środowisko uruchomieniowe ma ustawioną wartość NODE|6.9. Aby wyświetlić wszystkie obsługiwane środowiska uruchomieniowe, uruchom polecenie az webapp list-runtimes

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    Po utworzeniu aplikacji internetowej w interfejsie wiersza polecenia platformy Azure zostaną wyświetlone dane wyjściowe podobne do następujących:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Przejdź do nowo utworzonej aplikacji internetowej — powinna zostać wyświetlona działająca aplikacja internetowa. Zastąp ciąg <app_name> unikatową nazwą aplikacji.

    ```text
    http://<app name>.azurewebsites.net
    ```
    Powyższe polecenie tworzy również aplikację z możliwością obsługi usługi Git, co pozwala na wdrażanie na platformie Azure z lokalnego repozytorium Git. 
    Lokalne repozytorium Git jest skonfigurowane dla adresu URL „https://<username>@<nazwa_aplikacji>.scm.azurewebsites.net/<nazwa_aplikacji>.git”

* Tworzenie użytkownika wdrożenia Po zakończeniu działania poprzedniego polecenia można dodać zdalne środowisko platformy Azure do lokalnego repozytorium Git. Zastąp element <url> adresem URL zdalnego repozytorium Git uzyskanego po włączeniu usługi dla aplikacji.

    ```bash
    git remote add azure <url>
    ```
::: zone-end

::: zone pivot="dotnet"

## <a name="open-and-edit-the-solution"></a>Otwieranie i edytowanie rozwiązania

Edytuj plik program.cs, aby uruchomić przykład z określoną nazwą magazynu kluczy.

1. Przejdź do folderu key-vault-dotnet-core-quickstart.
2. Otwórz plik key-vault-dotnet-core-quickstart.sln w programie Visual Studio 2017.
3. Otwórz plik Program.cs i zaktualizuj symbol zastępczy *YourKeyVaultName* przy użyciu nazwy utworzonego wcześniej magazynu kluczy.

To rozwiązanie korzysta z bibliotek NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) i [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).

## <a name="run-the-app"></a>Uruchamianie aplikacji

Z menu głównego programu Visual Studio 2017 wybierz kolejno pozycje **Debuguj** > **Uruchom** bez debugowania. Gdy pojawi się przeglądarka, przejdź do strony **Informacje**. Zostanie wyświetlona wartość wpisu **AppSecret**.

## <a name="publish-the-web-application-to-azure"></a>Publikowanie aplikacji internetowej na platformie Azure

Opublikuj tę aplikację na platformie Azure, aby sprawdzić, jak działa na żywo jako aplikacja internetowa oraz czy jest pobierana wartość wpisu tajnego:

1. W programie Visual Studio wybierz projekt **key-vault-dotnet-core-quickstart**.
2. Wybierz pozycje **Publikuj** > **Uruchom**.
3. Utwórz nową usługę **App Service** i wybierz pozycję **Opublikuj**.
4. Zmień nazwę aplikacji na **keyvaultdotnetcorequickstart**.
5. Wybierz pozycję **Utwórz**.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

::: zone-end

## <a name="enable-managed-service-identities"></a>Włączanie tożsamości usługi zarządzanej

Usługa Azure Key Vault oferuje bezpieczny sposób przechowywania poświadczeń oraz innych kluczy i wpisów tajnych, ale w celu ich pobrania należy uwierzytelnić kod w usłudze Azure Key Vault. Ułatwia to tożsamość usługi zarządzanej, udostępniając usługom platformy Azure automatycznie zarządzaną tożsamość w usłudze Azure Active Directory (Azure AD). Za pomocą tej tożsamości można uwierzytelnić się w dowolnej usłudze obsługującej uwierzytelnianie usługi Azure AD, w tym w usłudze Key Vault, bez konieczności przechowywania poświadczeń w kodzie.

1. Wróć do interfejsu wiersza polecenia platformy Azure.
2. Uruchom polecenie assign-identity w celu utworzenia tożsamości dla tej aplikacji:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>To polecenie w tej procedurze odpowiada przejściu do portalu i przełączeniu ustawienia **Tożsamość usługi zarządzanej** na wartość **Włączone** we właściwościach aplikacji internetowej.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Przypisywanie do aplikacji uprawnień do odczytu wpisów tajnych z usługi Key Vault

Zapisz dane wyjściowe po opublikowaniu aplikacji na platformie Azure. Powinny one mieć następujący format:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Następnie uruchom to polecenie, używając nazwy Twojego magazynu kluczy i wartości **PrincipalId**:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>Wdrażanie aplikacji Node na platformie Azure i pobieranie wartości wpisu tajnego

Teraz wszystko jest gotowe. Uruchom następujące polecenie, aby wdrożyć aplikację na platformie Azure

```bash
git push azure master
```

Po wykonaniu tej czynności podczas przeglądania witryny https://<nazwa_aplikacji>.azurewebsites.net zobaczysz wartość wpisu tajnego.
Upewnij się, że nazwa <YourKeyVaultName> została zastąpiona nazwą Twojego magazynu ::: zone-end

::: zone pivot="dotnet" Teraz po uruchomieniu aplikacji powinna pojawić się pobrana wartość wpisu tajnego.
::: zone-end

## <a name="next-steps"></a>Kolejne kroki

::: zone pivot="nodejs"
* [Strona główna usługi Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Dokumentacja usługi Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [Zestaw Azure SDK dla platformy Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [Dokumentacja interfejsów API REST platformy Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end

::: zone pivot="dotnet"
* [Strona główna usługi Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Dokumentacja usługi Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [Zestaw Azure SDK dla platformy .NET](https://github.com/Azure/azure-sdk-for-net)
* [Dokumentacja interfejsów API REST platformy Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end