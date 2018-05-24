---
title: Konfigurowanie lokalnego repozytorium Git
description: Ten artykuł zawiera wskazówki dotyczące tworzenia lokalnego repozytorium Git i współtworzenia dokumentacji, z uwzględnieniem procesów tworzenia rozwidlenia i klonowania.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: f702d0d29ee7dc9c69cb26b79bf6283d91b6b6bc
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a>Konfigurowanie lokalnego repozytorium Git na potrzeby dokumentacji

W tym artykule opisano kroki prowadzące do skonfigurowania repozytorium Git na komputerze lokalnym na potrzeby współtworzenia dokumentacji firmy Microsoft. Współautorzy mogą korzystać z lokalnie sklonowanego repozytorium, dodając nowe artykuły, wprowadzając istotne zmiany w istniejących artykułach lub zmieniając ich grafikę.

Aby rozpocząć współtworzenie zawartości, należy jeden raz wykonać poniższe działania związane z konfigurowaniem:
> [!div class="checklist"]
> * Określenie odpowiedniego repozytorium
> * Utworzenie rozwidlenia repozytorium do swojego konta w usłudze GitHub
> * Wybranie lokalnego folderu na sklonowane pliki
> * Sklonowanie repozytorium na komputerze lokalnym
> * Skonfigurowanie wartości zdalnego połączenia nadrzędnego

> [!IMPORTANT]
> Jeśli wprowadzasz jedynie drobne zmiany do artykułu, *nie musisz* wykonywać kroków opisanych w tym artykule. Możesz przejść bezpośrednio do [przepływu pracy dla szybkich zmian](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Omówienie

W celu współtworzenia zawartości witryny dokumentacji firmy Microsoft można lokalnie tworzyć i edytować pliki Markdown poprzez klonowanie odpowiedniego repozytorium dokumentacji. Firma Microsoft wymaga wykonania rozwidlenia odpowiedniego repozytorium do konta użytkownika w usłudze GitHub, dzięki czemu użytkownik będzie miał uprawnienia do odczytu i zapisu umożliwiające przechowywanie proponowanych zmian. W dalszej kolejności użytkownik stosuje żądania ściągnięcia w celu scalenia zmian w centralnym repozytorium udostępnionym tylko do odczytu.

![Trójkąt GitHub](./media/git-and-github-initial-setup.png)

Jeśli dopiero zaczynasz pracę z usługą GitHub, obejrzyj poniższy film w celu zapoznania się z koncepcyjnym omówieniem procesu tworzenia rozwidlenia i klonowania:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>Określenie repozytorium

Dokumentacja, która jest obsługiwana w witrynie [docs.microsoft.com](https://docs.microsoft.com), znajduje się w różnych repozytoriach witryny [github.com](https://www.github.com).

1. Jeśli nie masz pewności, z którego repozytorium należy skorzystać, zajrzyj do artykułu w witrynie docs.microsoft.com, korzystając z przeglądarki sieci Web. Wybierz link **Edytuj** (ikona ołówka) w prawej górnej części tego artykułu.

   ![Kliknij przycisk Edytuj, aby określić repozytorium i lokalizację pliku.](media/index/edit-article.png)

2. Ten link umożliwia przejście do lokalizacji w witrynie github.com, w której we właściwym repozytorium znajduje się odpowiedni plik Markdown. Zapisz adres URL, aby określić nazwę repozytorium.

   ![Zwróć uwagę, że adres URL określa lokalizację repozytorium.](media/public-repo.png)

   Na przykład na potrzeby publicznego dodawania zawartości dostępne są następujące popularne repozytoria:
   - Dokumentacja platformy Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - Dokumentacja programu SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Dokumentacja programu Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - Dokumentacja platformy .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Dokumentacja pakietu Azure .Net SDK [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>Utworzenie rozwidlenia repozytorium
Korzystając z odpowiedniego repozytorium, utwórz rozwidlenie repozytorium do własnego konta usługi GitHub przy użyciu witryny usługi GitHub.

Osobiste rozwidlenie jest wymagane, ponieważ wszystkie repozytoria główne dokumentacji oferują dostęp tylko do odczytu, co oznacza, że nie możesz wprowadzać zmian bezpośrednio w zawartości repozytoriów. W celu dokonania zmian musisz przesłać do repozytorium głównego [żądanie ściągnięcia](git-github-fundamentals.md#pull-requests) ze swojego rozwidlenia. Aby wykonać ten proces, najpierw musisz dysponować swoją własną kopią repozytorium, do której masz prawa do zapisu. Do tego służy *rozwidlenie* GitHub.

1. Przejdź do strony GitHub repozytorium głównego i naciśnij przycisk **Fork** (Rozwidlenie) w prawym górnym rogu.

   ![Przykład profilu GitHub](./media/contribute-get-started-setup-local/fork.png)

2. W odpowiedzi na pytanie o miejsce utworzenia rozwidlenia repozytorium wskaż kafelek swojego konta usługi GitHub. Spowoduje to utworzenie rozwidlenia, czyli kopii repozytorium w ramach Twojego konta usługi GitHub.

## <a name="choose-a-local-folder"></a>Wybieranie folderu lokalnego
Utwórz folder lokalny, w którym będzie przechowywana lokalna kopia repozytorium. Niektóre repozytoria mogą być duże, nawet do 5 GB, na przykład azure-docs. Wybierz lokalizację z dostępnym miejscem na dysku.

1. Wybierz nazwę folderu, która będzie łatwa do zapamiętania i wpisywania. Na przykład rozważ użycie folderu głównego `C:\docs\` lub utwórz folder w swoim katalogu profilu użytkownika `~/Documents/docs/`.

   > [!IMPORTANT]
   > Nie należy wybierać lokalnej ścieżki folderu zagnieżdżonej wewnątrz lokalizacji innego folderu repozytorium Git. Chociaż dopuszczalne jest przechowywanie folderów sklonowanych usługi Git obok siebie, zagnieżdżanie folderów Git jeden wewnątrz drugiego powoduje błędy podczas śledzenia plików.

2. Uruchamianie powłoki Git Bash

   ![Uruchamianie powłoki Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   Domyślną lokalizacją, w której uruchamiana jest powłoka Git Bash, jest zwykle katalog macierzysty (~) lub `/c/users/<Windows-user-account>/` w systemie operacyjnym Windows.

   Aby określić bieżący katalog, wpisz ciąg `pwd` w wierszu polecenia $. 

3. Zmień katalog (za pomocą polecenia cd) na folder utworzony na potrzeby lokalnego hostowania repozytorium. Pamiętaj, że powłoka Git Bash używa dla ścieżek folderów konwencji z ukośnikami zamiast ukośników odwrotnych.

   Na przykład `cd /c/docs/ ` lub `cd ~/Documents/docs/`

## <a name="create-a-local-clone"></a>Tworzenie lokalnego klona

Korzystając z powłoki Git Bash, przygotuj uruchomienie polecenia **clone**, aby ściągnąć kopię repozytorium (rozwidlenie) na Twoje urządzenie w bieżącym katalogu. 

### <a name="authenticate-by-using-git-credential-manager"></a>Uwierzytelnianie przy użyciu programu Git Credential Manager
Jeśli została zainstalowana najnowsza wersja usługi Git dla systemu Windows i została zaakceptowana instalacja domyślna, program Git Credential Manager jest domyślnie włączony. Program Git Credential Manager bardzo ułatwia uwierzytelnianie, ponieważ likwiduje potrzebę odwoływania się do osobistego tokenu dostępu podczas kolejnego ustanawiania uwierzytelnionych połączeń i dostępów zdalnych w usłudze GitHub.

1. Uruchom polecenie **clone**, podając nazwę repozytorium. Klonowanie pobiera (klonuje) repozytorium rozwidlone na komputer lokalny. 

    > [!Tip]
    > Adres URL Twojego rozwidlenia w usłudze GitHub potrzebny do polecenia klonowania możesz uzyskać za pośrednictwem przycisku **Clone or download** (Klonuj lub pobierz) interfejsu użytkownika usługi GitHub:
    >
    > ![Clone or download (Klonuj lub pobierz)](./media/contribute-get-started-setup-local/clone-or-download.png)

    Upewnij się, że podczas procesu klonowania została określona ścieżka do *Twojego rozwidlenia*, a nie do repozytorium głównego, z którego zostało utworzone rozwidlenie. W przeciwnym razie nie będziesz mieć możliwości współtworzenia zmian. Twoje rozwidlenie jest przywoływane za pośrednictwem Twojego osobistego konta użytkownika usługi GitHub, na przykład `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    Twoje polecenie klonowania powinno wyglądać podobnie do tego:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Po wyświetleniu monitu wprowadź swoje poświadczenia usługi GitHub.

    ![Logowanie do usługi GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. Po wyświetleniu monitu wprowadź kod uwierzytelniania dwuetapowego.

    ![Uwierzytelnianie dwuetapowe w usłudze GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > Twoje poświadczenia zostaną zapisane i będą używane do uwierzytelniania przyszłych żądań kierowanych do usługi GitHub. To uwierzytelnianie należy wykonać jednokrotnie dla danego komputera. 

4. Polecenie clone uruchamia i pobiera kopię plików repozytorium z rozwidlenia do nowego folderu na dysku lokalnym. Nowy folder zostaje utworzony w bieżącym folderze. Może to potrwać kilka minut w zależności od rozmiaru repozytorium. Po zakończeniu możesz eksplorować folder, aby wyświetlić jego strukturę.

## <a name="configure-remote-upstream"></a>Konfigurowanie zdalnego połączenia nadrzędnego
Po sklonowaniu repozytorium skonfiguruj połączenie zdalne z repozytorium głównym przeznaczone tylko do odczytu, o nazwie **upstream**. Z adresu URL połączenia nadrzędnego będziesz korzystać w celu synchronizowania Twojego lokalnego repozytorium z najnowszymi zmianami wykonywanymi przez innych użytkowników. Polecenie **git remote** służy do ustawiania wartości konfiguracji. Polecenie **fetch** służy do odświeżania informacji o gałęzi z repozytorium nadrzędnego.

1. Jeśli korzystasz z programu **Git Credential Manager**, użyj poniższych poleceń. Zastąp elementy zastępcze \<repo\> i \<organization\>.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Wyświetl skonfigurowane wartości i potwierdź, że adresy URL są poprawne. Upewnij się, że adresy URL źródła (**origin**) wskazują na Twoje osobiste rozwidlenie. Upewnij się, że adresy URL repozytorium **upstream** wskazują repozytorium główne, takie jak MicrosoftDocs lub Azure. 
   ```bash
   git remote -v 
   ```

   Poniżej pokazany jest przykład danych wyjściowych połączenia zdalnego. Fikcyjne konto usługi git o nazwie MyGitAccount jest konfigurowane przy użyciu osobistego tokenu dostępu w celu uzyskania dostępu do repozytorium azure-docs:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. W przypadku popełnienia błędu możesz usunąć wartość połączenia zdalnego. Aby usunąć wartość połączenia nadrzędnego, uruchom polecenie `git remote remove upstream`.

## <a name="next-steps"></a>Kolejne kroki
- Aby dowiedzieć się więcej na temat dodawania i aktualizowania zawartości, przejdź do strony [GitHub contribution workflows](how-to-write-workflows-major.md) (Przepływy pracy dotyczące współautorstwa w usłudze GitHub).