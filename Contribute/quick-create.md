---
title: 'Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault | Microsoft Docs'
description: 'Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 27ebd3e348fc231d8b82e6c17f282bd9ca4afb9f
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308829"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="b3434-103">Szybki start: konfigurowanie i pobieranie wpisów tajnych z usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="b3434-104">W tym przewodniku Szybki start przedstawiono sposób przechowywania wpisu tajnego w usłudze Key Vault oraz pobierania go przy użyciu aplikacji internetowej.</span><span class="sxs-lookup"><span data-stu-id="b3434-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="b3434-105">Aby wyświetlić wartość wpisu tajnego, musisz uruchomić ją na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="b3434-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="b3434-106">W tym przewodniku Szybki start używana jest platforma Node.js oraz tożsamości usługi zarządzanej (MSI)</span><span class="sxs-lookup"><span data-stu-id="b3434-106">The quickstart uses Node.js and Managed service identities (MSIs)</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b3434-107">Tworzenie usługi Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="b3434-108">Przechowywanie wpisu tajnego w usłudze Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-108">Store a secret in Key Vault.</span></span>
> * <span data-ttu-id="b3434-109">Pobieranie wpisu tajnego z usługi Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="b3434-110">Tworzenie aplikacji internetowej platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="b3434-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="b3434-111">[Włączanie tożsamości usługi zarządzanej](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="b3434-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="b3434-112">Przyznawanie wymaganych uprawnień w celu umożliwienia aplikacji internetowej odczytu danych z usługi Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="b3434-113">Przed kontynuowaniem upewnij się, że znasz [podstawowe pojęcia](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="b3434-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

> [!NOTE]
> <span data-ttu-id="b3434-114">Aby przekonać się, dlaczego poniższy samouczek jest najlepszym rozwiązaniem, najpierw należy zapoznać się z kilkoma pojęciami.</span><span class="sxs-lookup"><span data-stu-id="b3434-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="b3434-115">Usługa Key Vault to centralne repozytorium do programistycznego przechowywania wpisów tajnych.</span><span class="sxs-lookup"><span data-stu-id="b3434-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="b3434-116">W tym celu aplikacje i użytkownicy muszą najpierw uwierzytelnić się w usłudze Key Vault, tj. podać wpis tajny.</span><span class="sxs-lookup"><span data-stu-id="b3434-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="b3434-117">Zgodnie z najlepszymi rozwiązaniami dotyczącymi bezpieczeństwa pierwszy wpis tajny musi być okresowo obracany.</span><span class="sxs-lookup"><span data-stu-id="b3434-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="b3434-118">Jednak aplikacje [tożsamości usługi zarządzanej](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) uruchamiane na platformie Azure otrzymują tożsamość, która jest automatycznie zarządzana przez tę platformę.</span><span class="sxs-lookup"><span data-stu-id="b3434-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="b3434-119">Dzięki temu można rozwiązać **początkowy problem dotyczący wpisu tajnego**, gdzie użytkownicy i aplikacje mogą postępować zgodnie z najlepszymi praktykami i nie muszą pamiętać o obracaniu pierwszego wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="b3434-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3434-120">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b3434-120">Prerequisites</span></span>

<span data-ttu-id="b3434-121">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="b3434-121">::: zone pivot="nodejs"</span></span>
* <span data-ttu-id="b3434-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="b3434-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span></span>
* <span data-ttu-id="b3434-123">[Visual Studio 2017 w wersji 15.7.3 lub nowszej](https://www.microsoft.com/net/download/windows) z następującymi obciążeniami:</span><span class="sxs-lookup"><span data-stu-id="b3434-123">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="b3434-124">Tworzenie aplikacji na platformie ASP.NET i aplikacji internetowej</span><span class="sxs-lookup"><span data-stu-id="b3434-124">ASP.NET and web development</span></span>
  * <span data-ttu-id="b3434-125">Tworzenie aplikacji dla wielu platform w środowisku .NET Core</span><span class="sxs-lookup"><span data-stu-id="b3434-125">.NET Core cross-platform development</span></span>
* <span data-ttu-id="b3434-126">[Zestaw .NET Core 2.1 SDK lub nowszy](https://www.microsoft.com/net/download/windows) :::zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-126">[.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download/windows) ::: zone-end</span></span>
* <span data-ttu-id="b3434-127">Git ([pobieranie](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="b3434-127">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="b3434-128">Subskrypcja platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="b3434-128">An Azure subscription.</span></span> <span data-ttu-id="b3434-129">Jeśli nie masz subskrypcji platformy Azure, przed rozpoczęciem utwórz [bezpłatne konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).</span><span class="sxs-lookup"><span data-stu-id="b3434-129">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="b3434-130">[Interfejs wiersza polecenia platformy Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) w wersji 2.0.4 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="b3434-130">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="b3434-131">Jest on dostępny w systemach Windows, Mac i Linux.</span><span class="sxs-lookup"><span data-stu-id="b3434-131">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="b3434-132">Logowanie na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="b3434-132">Login to Azure</span></span>

<span data-ttu-id="b3434-133">Aby zalogować się do platformy Azure przy użyciu interfejsu wiersza polecenia, możesz wpisać:</span><span class="sxs-lookup"><span data-stu-id="b3434-133">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="b3434-134">Tworzenie grupy zasobów</span><span class="sxs-lookup"><span data-stu-id="b3434-134">Create resource group</span></span>

<span data-ttu-id="b3434-135">Utwórz grupę zasobów za pomocą polecenia [az group create](/cli/azure/group#az-group-create).</span><span class="sxs-lookup"><span data-stu-id="b3434-135">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="b3434-136">Grupa zasobów platformy Azure to logiczny kontener przeznaczony do wdrażania zasobów platformy Azure i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="b3434-136">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="b3434-137">Wybierz nazwę grupy zasobów i wypełnij symbol zastępczy.</span><span class="sxs-lookup"><span data-stu-id="b3434-137">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="b3434-138">Poniższy przykład obejmuje tworzenie grupy zasobów o nazwie *<YourResourceGroupName>* w lokalizacji *eastus*.</span><span class="sxs-lookup"><span data-stu-id="b3434-138">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="b3434-139">W tym samouczku używana jest utworzona teraz grupa zasobów.</span><span class="sxs-lookup"><span data-stu-id="b3434-139">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="b3434-140">Tworzenie usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-140">Create an Azure Key Vault</span></span>

<span data-ttu-id="b3434-141">Następnie utworzysz magazyn Key Vault, wykorzystując grupę zasobów utworzoną w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="b3434-141">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="b3434-142">Chociaż w tym artykule jako nazwa magazynu Key Vault używana jest wartość „ContosoKeyVault”, musisz użyć unikatowej nazwy.</span><span class="sxs-lookup"><span data-stu-id="b3434-142">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="b3434-143">Podaj następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="b3434-143">Provide the following information:</span></span>

* <span data-ttu-id="b3434-144">Nazwa magazynu — **wybierz tutaj nazwę magazynu Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="b3434-144">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="b3434-145">Nazwa grupy zasobów — **wybierz tutaj nazwę grupy zasobów**.</span><span class="sxs-lookup"><span data-stu-id="b3434-145">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="b3434-146">Lokalizacja — **Wschodnie stany USA**.</span><span class="sxs-lookup"><span data-stu-id="b3434-146">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="b3434-147">Twoje konto platformy Azure jest teraz jedynym kontem z uprawnieniami do wykonywania jakichkolwiek operacji na tym nowym magazynie.</span><span class="sxs-lookup"><span data-stu-id="b3434-147">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="b3434-148">Dodawanie wpisu tajnego do magazynu kluczy</span><span class="sxs-lookup"><span data-stu-id="b3434-148">Add a secret to key vault</span></span>

<span data-ttu-id="b3434-149">Dodajemy wpis tajny, aby zilustrować, jak to działa.</span><span class="sxs-lookup"><span data-stu-id="b3434-149">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="b3434-150">Możesz zapisywać parametry połączenia SQL lub inne informacje, które muszą być przechowywane bezpiecznie, ale jednocześnie być dostępne dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3434-150">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="b3434-151">W tym samouczku hasło będzie miało nazwę **AppSecret** i będzie w nim przechowywana wartość **MySecret**.</span><span class="sxs-lookup"><span data-stu-id="b3434-151">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="b3434-152">Wpisz poniższe polecenia, aby w magazynie Key Vault utworzyć wpis tajny o nazwie **AppSecret**, w którym będzie przechowywana wartość **MySecret**:</span><span class="sxs-lookup"><span data-stu-id="b3434-152">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="b3434-153">Aby wyświetlić wartość zawartą we wpisie tajnym jako zwykły tekst:</span><span class="sxs-lookup"><span data-stu-id="b3434-153">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="b3434-154">To polecenie powoduje wyświetlenie informacji o wpisie tajnym, w tym identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="b3434-154">This command shows the secret information including the URI.</span></span> <span data-ttu-id="b3434-155">Po wykonaniu tych kroków będziesz mieć identyfikator URI wpisu tajnego w usłudze Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-155">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="b3434-156">Zanotuj te informacje.</span><span class="sxs-lookup"><span data-stu-id="b3434-156">Write this information down.</span></span> <span data-ttu-id="b3434-157">Będą one potrzebne w kolejnym kroku.</span><span class="sxs-lookup"><span data-stu-id="b3434-157">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="b3434-158">Klonowanie repozytorium</span><span class="sxs-lookup"><span data-stu-id="b3434-158">Clone the Repo</span></span>

<span data-ttu-id="b3434-159">Sklonuj repozytorium, aby utworzyć kopię lokalną umożliwiającą edytowanie źródła, przez uruchomienie następującego polecenia:</span><span class="sxs-lookup"><span data-stu-id="b3434-159">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

<span data-ttu-id="b3434-160">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="b3434-160">::: zone pivot="nodejs"</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="b3434-161">Instalowanie zależności</span><span class="sxs-lookup"><span data-stu-id="b3434-161">Install dependencies</span></span>

<span data-ttu-id="b3434-162">W tym miejscu zainstalujemy zależności.</span><span class="sxs-lookup"><span data-stu-id="b3434-162">Here we install the dependencies.</span></span> <span data-ttu-id="b3434-163">Uruchom następujące polecenia cd key-vault-node-quickstart npm install</span><span class="sxs-lookup"><span data-stu-id="b3434-163">Run the following commands cd key-vault-node-quickstart npm install</span></span>

<span data-ttu-id="b3434-164">W tym projekcie używane są 2 moduły platformy node:</span><span class="sxs-lookup"><span data-stu-id="b3434-164">This project used 2 node modules:</span></span>

* [<span data-ttu-id="b3434-165">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="b3434-165">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="b3434-166">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="b3434-166">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="b3434-167">Publikowanie aplikacji internetowej na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="b3434-167">Publish the web application to Azure</span></span>

<span data-ttu-id="b3434-168">Poniżej przedstawiono kilka wymaganych kroków</span><span class="sxs-lookup"><span data-stu-id="b3434-168">Below are the few steps we need to do</span></span>

* <span data-ttu-id="b3434-169">Pierwszy krok to utworzenie planu usługi [Azure App Service](https://azure.microsoft.com/services/app-service/).</span><span class="sxs-lookup"><span data-stu-id="b3434-169">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="b3434-170">Ten plan pozwala na przechowywanie wielu aplikacji internetowych.</span><span class="sxs-lookup"><span data-stu-id="b3434-170">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="b3434-171">Następnie utworzymy aplikację internetową.</span><span class="sxs-lookup"><span data-stu-id="b3434-171">Next we create a web app.</span></span> <span data-ttu-id="b3434-172">W poniższym przykładzie zastąp ciąg <app_name> globalnie unikatową nazwą aplikacji (prawidłowe znaki to a–z, 0–9 i -).</span><span class="sxs-lookup"><span data-stu-id="b3434-172">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="b3434-173">Środowisko uruchomieniowe ma ustawioną wartość NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="b3434-173">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="b3434-174">Aby wyświetlić wszystkie obsługiwane środowiska uruchomieniowe, uruchom polecenie az webapp list-runtimes</span><span class="sxs-lookup"><span data-stu-id="b3434-174">To see all supported runtimes, run az webapp list-runtimes</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="b3434-175">Po utworzeniu aplikacji internetowej w interfejsie wiersza polecenia platformy Azure zostaną wyświetlone dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="b3434-175">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="b3434-176">Przejdź do nowo utworzonej aplikacji internetowej — powinna zostać wyświetlona działająca aplikacja internetowa.</span><span class="sxs-lookup"><span data-stu-id="b3434-176">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="b3434-177">Zastąp ciąg <app_name> unikatową nazwą aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3434-177">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="b3434-178">Powyższe polecenie tworzy również aplikację z możliwością obsługi usługi Git, co pozwala na wdrażanie na platformie Azure z lokalnego repozytorium Git.</span><span class="sxs-lookup"><span data-stu-id="b3434-178">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="b3434-179">Lokalne repozytorium Git jest skonfigurowane dla adresu URL „https://<username>@<nazwa_aplikacji>.scm.azurewebsites.net/<nazwa_aplikacji>.git”</span><span class="sxs-lookup"><span data-stu-id="b3434-179">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="b3434-180">Tworzenie użytkownika wdrożenia Po zakończeniu działania poprzedniego polecenia można dodać zdalne środowisko platformy Azure do lokalnego repozytorium Git.</span><span class="sxs-lookup"><span data-stu-id="b3434-180">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="b3434-181">Zastąp element <url> adresem URL zdalnego repozytorium Git uzyskanego po włączeniu usługi dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3434-181">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
    
<span data-ttu-id="b3434-182">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-182">::: zone-end</span></span>

<span data-ttu-id="b3434-183">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="b3434-183">::: zone pivot="dotnet"</span></span>
## <a name="open-and-edit-the-solution"></a><span data-ttu-id="b3434-184">Otwieranie i edytowanie rozwiązania</span><span class="sxs-lookup"><span data-stu-id="b3434-184">Open and edit the solution</span></span>

<span data-ttu-id="b3434-185">Edytuj plik program.cs, aby uruchomić przykład z określoną nazwą magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3434-185">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="b3434-186">Przejdź do folderu key-vault-dotnet-core-quickstart.</span><span class="sxs-lookup"><span data-stu-id="b3434-186">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="b3434-187">Otwórz plik key-vault-dotnet-core-quickstart.sln w programie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b3434-187">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="b3434-188">Otwórz plik Program.cs i zaktualizuj symbol zastępczy *YourKeyVaultName* przy użyciu nazwy utworzonego wcześniej magazynu kluczy.</span><span class="sxs-lookup"><span data-stu-id="b3434-188">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="b3434-189">To rozwiązanie korzysta z bibliotek NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) i [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).</span><span class="sxs-lookup"><span data-stu-id="b3434-189">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="b3434-190">Uruchamianie aplikacji</span><span class="sxs-lookup"><span data-stu-id="b3434-190">Run the app</span></span>

<span data-ttu-id="b3434-191">Z menu głównego programu Visual Studio 2017 wybierz kolejno pozycje **Debuguj** > **Uruchom** bez debugowania.</span><span class="sxs-lookup"><span data-stu-id="b3434-191">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="b3434-192">Gdy pojawi się przeglądarka, przejdź do strony **Informacje**.</span><span class="sxs-lookup"><span data-stu-id="b3434-192">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="b3434-193">Zostanie wyświetlona wartość wpisu **AppSecret**.</span><span class="sxs-lookup"><span data-stu-id="b3434-193">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="b3434-194">Publikowanie aplikacji internetowej na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="b3434-194">Publish the web application to Azure</span></span>

<span data-ttu-id="b3434-195">Opublikuj tę aplikację na platformie Azure, aby sprawdzić, jak działa na żywo jako aplikacja internetowa oraz czy jest pobierana wartość wpisu tajnego:</span><span class="sxs-lookup"><span data-stu-id="b3434-195">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="b3434-196">W programie Visual Studio wybierz projekt **key-vault-dotnet-core-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="b3434-196">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="b3434-197">Wybierz pozycje **Publikuj** > **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="b3434-197">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="b3434-198">Utwórz nową usługę **App Service** i wybierz pozycję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="b3434-198">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="b3434-199">Zmień nazwę aplikacji na **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="b3434-199">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="b3434-200">Wybierz pozycję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="b3434-200">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
<span data-ttu-id="b3434-201">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-201">::: zone-end</span></span>

## <a name="enable-managed-service-identities"></a><span data-ttu-id="b3434-202">Włączanie tożsamości usługi zarządzanej</span><span class="sxs-lookup"><span data-stu-id="b3434-202">Enable managed service identities</span></span>

<span data-ttu-id="b3434-203">Usługa Azure Key Vault oferuje bezpieczny sposób przechowywania poświadczeń oraz innych kluczy i wpisów tajnych, ale w celu ich pobrania należy uwierzytelnić kod w usłudze Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b3434-203">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="b3434-204">Ułatwia to tożsamość usługi zarządzanej, udostępniając usługom platformy Azure automatycznie zarządzaną tożsamość w usłudze Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b3434-204">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b3434-205">Za pomocą tej tożsamości można uwierzytelnić się w dowolnej usłudze obsługującej uwierzytelnianie usługi Azure AD, w tym w usłudze Key Vault, bez konieczności przechowywania poświadczeń w kodzie.</span><span class="sxs-lookup"><span data-stu-id="b3434-205">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="b3434-206">Wróć do interfejsu wiersza polecenia platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="b3434-206">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="b3434-207">Uruchom polecenie assign-identity w celu utworzenia tożsamości dla tej aplikacji:</span><span class="sxs-lookup"><span data-stu-id="b3434-207">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="b3434-208">To polecenie w tej procedurze odpowiada przejściu do portalu i przełączeniu ustawienia **Tożsamość usługi zarządzanej** na wartość **Włączone** we właściwościach aplikacji internetowej.</span><span class="sxs-lookup"><span data-stu-id="b3434-208">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="b3434-209">Przypisywanie do aplikacji uprawnień do odczytu wpisów tajnych z usługi Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-209">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="b3434-210">Zapisz dane wyjściowe po opublikowaniu aplikacji na platformie Azure.</span><span class="sxs-lookup"><span data-stu-id="b3434-210">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="b3434-211">Powinny one mieć następujący format:</span><span class="sxs-lookup"><span data-stu-id="b3434-211">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="b3434-212">Następnie uruchom to polecenie, używając nazwy Twojego magazynu kluczy i wartości **PrincipalId**:</span><span class="sxs-lookup"><span data-stu-id="b3434-212">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

<span data-ttu-id="b3434-213">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="b3434-213">::: zone pivot="nodejs"</span></span>
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="b3434-214">Wdrażanie aplikacji Node na platformie Azure i pobieranie wartości wpisu tajnego</span><span class="sxs-lookup"><span data-stu-id="b3434-214">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="b3434-215">Teraz wszystko jest gotowe.</span><span class="sxs-lookup"><span data-stu-id="b3434-215">Now that everything is set.</span></span> <span data-ttu-id="b3434-216">Uruchom następujące polecenie, aby wdrożyć aplikację na platformie Azure</span><span class="sxs-lookup"><span data-stu-id="b3434-216">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="b3434-217">Po wykonaniu tej czynności podczas przeglądania witryny https://<nazwa_aplikacji>.azurewebsites.net zobaczysz wartość wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="b3434-217">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="b3434-218">Upewnij się, że nazwa <YourKeyVaultName> została zastąpiona nazwą magazynu</span><span class="sxs-lookup"><span data-stu-id="b3434-218">Make sure that you replaced the name <YourKeyVaultName> with your vault name</span></span>

<span data-ttu-id="b3434-219">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-219">::: zone-end</span></span>

<span data-ttu-id="b3434-220">::: zone pivot="dotnet" Teraz po uruchomieniu aplikacji powinna pojawić się pobrana wartość wpisu tajnego.</span><span class="sxs-lookup"><span data-stu-id="b3434-220">::: zone pivot="dotnet" Now when you run the application, you should see your secret value retrieved.</span></span>
<span data-ttu-id="b3434-221">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-221">::: zone-end</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3434-222">Kolejne kroki</span><span class="sxs-lookup"><span data-stu-id="b3434-222">Next steps</span></span>

<span data-ttu-id="b3434-223">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="b3434-223">::: zone pivot="nodejs"</span></span>
* [<span data-ttu-id="b3434-224">Strona główna usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-224">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="b3434-225">Dokumentacja usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-225">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="b3434-226">Zestaw Azure SDK dla platformy Node</span><span class="sxs-lookup"><span data-stu-id="b3434-226">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* <span data-ttu-id="b3434-227">[Dokumentacja interfejsów API REST platformy Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-227">[Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>

<span data-ttu-id="b3434-228">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="b3434-228">::: zone pivot="dotnet"</span></span>
* [<span data-ttu-id="b3434-229">Strona główna usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-229">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="b3434-230">Dokumentacja usługi Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="b3434-230">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="b3434-231">Zestaw Azure SDK dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="b3434-231">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* <span data-ttu-id="b3434-232">[Dokumentacja interfejsów API REST platformy Azure](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="b3434-232">[Azure REST API reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>
