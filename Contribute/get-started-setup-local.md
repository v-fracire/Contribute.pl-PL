---
title: Konfigurowanie lokalnego repozytorium Git
description: Ten artykuł zawiera wskazówki dotyczące tworzenia lokalnego repozytorium Git i współtworzenia dokumentacji, z uwzględnieniem procesów tworzenia rozwidlenia i klonowania.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.openlocfilehash: 2ad0de552d481e2460ca0f56570181e33d0a6608
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238994"
---
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="0137e-103">Konfigurowanie lokalnego repozytorium Git na potrzeby dokumentacji</span><span class="sxs-lookup"><span data-stu-id="0137e-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="0137e-104">W tym artykule opisano kroki prowadzące do skonfigurowania repozytorium Git na komputerze lokalnym na potrzeby współtworzenia dokumentacji firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0137e-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="0137e-105">Współautorzy mogą korzystać z lokalnie sklonowanego repozytorium, dodając nowe artykuły, wprowadzając istotne zmiany w istniejących artykułach lub zmieniając ich grafikę.</span><span class="sxs-lookup"><span data-stu-id="0137e-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="0137e-106">Aby rozpocząć współtworzenie zawartości, należy jeden raz wykonać poniższe działania związane z konfigurowaniem:</span><span class="sxs-lookup"><span data-stu-id="0137e-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="0137e-107">Określenie odpowiedniego repozytorium</span><span class="sxs-lookup"><span data-stu-id="0137e-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="0137e-108">Utworzenie rozwidlenia repozytorium do swojego konta w usłudze GitHub</span><span class="sxs-lookup"><span data-stu-id="0137e-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="0137e-109">Wybranie lokalnego folderu na sklonowane pliki</span><span class="sxs-lookup"><span data-stu-id="0137e-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="0137e-110">Sklonowanie repozytorium na komputerze lokalnym</span><span class="sxs-lookup"><span data-stu-id="0137e-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="0137e-111">Skonfigurowanie wartości zdalnego połączenia nadrzędnego</span><span class="sxs-lookup"><span data-stu-id="0137e-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0137e-112">Jeśli wprowadzasz jedynie drobne zmiany do artykułu, *nie musisz* wykonywać kroków opisanych w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="0137e-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="0137e-113">Możesz przejść bezpośrednio do [przepływu pracy dla szybkich zmian](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="0137e-113">You can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>

## <a name="overview"></a><span data-ttu-id="0137e-114">Omówienie</span><span class="sxs-lookup"><span data-stu-id="0137e-114">Overview</span></span>

<span data-ttu-id="0137e-115">W celu współtworzenia zawartości witryny dokumentacji firmy Microsoft można lokalnie tworzyć i edytować pliki Markdown poprzez klonowanie odpowiedniego repozytorium dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="0137e-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="0137e-116">Firma Microsoft wymaga wykonania rozwidlenia odpowiedniego repozytorium do konta użytkownika w usłudze GitHub, dzięki czemu użytkownik będzie miał uprawnienia do odczytu i zapisu umożliwiające przechowywanie proponowanych zmian.</span><span class="sxs-lookup"><span data-stu-id="0137e-116">Microsoft requires you to fork the appropriate repository into your own github account, so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="0137e-117">W dalszej kolejności użytkownik stosuje żądania ściągnięcia w celu scalenia zmian w centralnym repozytorium udostępnionym tylko do odczytu.</span><span class="sxs-lookup"><span data-stu-id="0137e-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![Trójkąt GitHub](./media/git-and-github-initial-setup.png)

<span data-ttu-id="0137e-119">Jeśli dopiero zaczynasz pracę z usługą GitHub, obejrzyj poniższy film w celu zapoznania się z koncepcyjnym omówieniem procesu tworzenia rozwidlenia i klonowania:</span><span class="sxs-lookup"><span data-stu-id="0137e-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="0137e-120">Określenie repozytorium</span><span class="sxs-lookup"><span data-stu-id="0137e-120">Determine the repository</span></span>

<span data-ttu-id="0137e-121">Dokumentacja, która jest obsługiwana w witrynie [docs.microsoft.com](https://docs.microsoft.com), znajduje się w różnych repozytoriach witryny [github.com](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="0137e-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="0137e-122">Jeśli nie masz pewności, z którego repozytorium należy skorzystać, zajrzyj do artykułu w witrynie docs.microsoft.com, korzystając z przeglądarki sieci Web.</span><span class="sxs-lookup"><span data-stu-id="0137e-122">If you are unsure of which repository to use, then visit the article on docs.microsoft.com using your web browser.</span></span> <span data-ttu-id="0137e-123">Wybierz link **Edytuj** (ikona ołówka) w prawej górnej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="0137e-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![Kliknij przycisk Edytuj, aby określić repozytorium i lokalizację pliku.](media/index/edit-article.png)

2. <span data-ttu-id="0137e-125">Ten link umożliwia przejście do lokalizacji w witrynie github.com, w której we właściwym repozytorium znajduje się odpowiedni plik Markdown.</span><span class="sxs-lookup"><span data-stu-id="0137e-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="0137e-126">Zapisz adres URL, aby określić nazwę repozytorium.</span><span class="sxs-lookup"><span data-stu-id="0137e-126">Note the URL to view the repository name.</span></span>

   ![Zwróć uwagę, że adres URL określa lokalizację repozytorium.](media/public-repo.png)

   <span data-ttu-id="0137e-128">Na przykład na potrzeby publicznego dodawania zawartości dostępne są następujące popularne repozytoria:</span><span class="sxs-lookup"><span data-stu-id="0137e-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="0137e-129">Dokumentacja platformy Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="0137e-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="0137e-130">Dokumentacja programu SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="0137e-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="0137e-131">Dokumentacja programu Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="0137e-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="0137e-132">Dokumentacja platformy .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="0137e-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="0137e-133">Dokumentacja pakietu Azure .Net SDK [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="0137e-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="0137e-134">Utworzenie rozwidlenia repozytorium</span><span class="sxs-lookup"><span data-stu-id="0137e-134">Fork the repository</span></span>
<span data-ttu-id="0137e-135">Korzystając z odpowiedniego repozytorium, utwórz rozwidlenie repozytorium do własnego konta usługi GitHub przy użyciu witryny usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="0137e-136">Osobiste rozwidlenie jest wymagane, ponieważ wszystkie repozytoria główne dokumentacji oferują dostęp tylko do odczytu, co oznacza, że nie możesz wprowadzać zmian bezpośrednio w zawartości repozytoriów.</span><span class="sxs-lookup"><span data-stu-id="0137e-136">A personal fork is required since all main documentation repositories provide read-only access, which means you cannot make changes directly on content in the repositories.</span></span> <span data-ttu-id="0137e-137">W celu dokonania zmian musisz przesłać do repozytorium głównego [żądanie ściągnięcia](git-github-fundamentals.md#pull-requests) ze swojego rozwidlenia.</span><span class="sxs-lookup"><span data-stu-id="0137e-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="0137e-138">Aby wykonać ten proces, najpierw musisz dysponować swoją własną kopią repozytorium, do której masz prawa do zapisu.</span><span class="sxs-lookup"><span data-stu-id="0137e-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="0137e-139">Do tego służy *rozwidlenie* GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="0137e-140">Przejdź do strony GitHub repozytorium głównego i naciśnij przycisk **Fork** (Rozwidlenie) w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="0137e-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Przykład profilu GitHub](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="0137e-142">W odpowiedzi na pytanie o miejsce utworzenia rozwidlenia repozytorium wskaż kafelek swojego konta usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="0137e-143">Spowoduje to utworzenie rozwidlenia, czyli kopii repozytorium w ramach Twojego konta usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="0137e-144">Wybieranie folderu lokalnego</span><span class="sxs-lookup"><span data-stu-id="0137e-144">Choose a local folder</span></span>
<span data-ttu-id="0137e-145">Utwórz folder lokalny, w którym będzie przechowywana lokalna kopia repozytorium.</span><span class="sxs-lookup"><span data-stu-id="0137e-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="0137e-146">Niektóre repozytoria mogą być duże, nawet do 5 GB, na przykład azure-docs.</span><span class="sxs-lookup"><span data-stu-id="0137e-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="0137e-147">Wybierz lokalizację z dostępnym miejscem na dysku.</span><span class="sxs-lookup"><span data-stu-id="0137e-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="0137e-148">Wybierz nazwę folderu, która będzie łatwa do zapamiętania i wpisywania.</span><span class="sxs-lookup"><span data-stu-id="0137e-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="0137e-149">Na przykład rozważ użycie folderu głównego `C:\docs\` lub utwórz folder w swoim katalogu profilu użytkownika `~/Documents/docs/`.</span><span class="sxs-lookup"><span data-stu-id="0137e-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="0137e-150">Nie należy wybierać lokalnej ścieżki folderu zagnieżdżonej wewnątrz lokalizacji innego folderu repozytorium Git.</span><span class="sxs-lookup"><span data-stu-id="0137e-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="0137e-151">Chociaż dopuszczalne jest przechowywanie folderów sklonowanych usługi Git obok siebie, zagnieżdżanie folderów Git jeden wewnątrz drugiego powoduje błędy podczas śledzenia plików.</span><span class="sxs-lookup"><span data-stu-id="0137e-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="0137e-152">Uruchamianie powłoki Git Bash</span><span class="sxs-lookup"><span data-stu-id="0137e-152">Launch Git Bash</span></span>

   ![Uruchamianie powłoki Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="0137e-154">Domyślną lokalizacją, w której uruchamiana jest powłoka Git Bash, jest zwykle katalog macierzysty (~) lub `/c/users/<Windows-user-account>/` w systemie operacyjnym Windows.</span><span class="sxs-lookup"><span data-stu-id="0137e-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="0137e-155">Aby określić bieżący katalog, wpisz ciąg `pwd` w wierszu polecenia $.</span><span class="sxs-lookup"><span data-stu-id="0137e-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="0137e-156">Zmień katalog (za pomocą polecenia cd) na folder utworzony na potrzeby lokalnego hostowania repozytorium.</span><span class="sxs-lookup"><span data-stu-id="0137e-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="0137e-157">Pamiętaj, że powłoka Git Bash używa dla ścieżek folderów konwencji z ukośnikami zamiast ukośników odwrotnych.</span><span class="sxs-lookup"><span data-stu-id="0137e-157">Note that Git Bash uses Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="0137e-158">Na przykład `cd /c/docs/ ` lub `cd ~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="0137e-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="0137e-159">Tworzenie lokalnego klona</span><span class="sxs-lookup"><span data-stu-id="0137e-159">Create a local clone</span></span>

<span data-ttu-id="0137e-160">Korzystając z powłoki Git Bash, przygotuj uruchomienie polecenia **clone**, aby ściągnąć kopię repozytorium (rozwidlenie) na Twoje urządzenie w bieżącym katalogu.</span><span class="sxs-lookup"><span data-stu-id="0137e-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="0137e-161">Uwierzytelnianie przy użyciu programu Git Credential Manager</span><span class="sxs-lookup"><span data-stu-id="0137e-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="0137e-162">Jeśli została zainstalowana najnowsza wersja usługi Git dla systemu Windows i została zaakceptowana instalacja domyślna, program Git Credential Manager jest domyślnie włączony.</span><span class="sxs-lookup"><span data-stu-id="0137e-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="0137e-163">Program Git Credential Manager bardzo ułatwia uwierzytelnianie, ponieważ likwiduje potrzebę odwoływania się do osobistego tokenu dostępu podczas kolejnego ustanawiania uwierzytelnionych połączeń i dostępów zdalnych w usłudze GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-163">Git Credential Manager makes authentication much easier, because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="0137e-164">Uruchom polecenie **clone**, podając nazwę repozytorium.</span><span class="sxs-lookup"><span data-stu-id="0137e-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="0137e-165">Klonowanie pobiera (klonuje) repozytorium rozwidlone na komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="0137e-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="0137e-166">Adres URL Twojego rozwidlenia w usłudze GitHub potrzebny do polecenia klonowania możesz uzyskać za pośrednictwem przycisku **Clone or download** (Klonuj lub pobierz) interfejsu użytkownika usługi GitHub:</span><span class="sxs-lookup"><span data-stu-id="0137e-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Clone or download (Klonuj lub pobierz)](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="0137e-168">Upewnij się, że podczas procesu klonowania została określona ścieżka do *Twojego rozwidlenia*, a nie do repozytorium głównego, z którego zostało utworzone rozwidlenie.</span><span class="sxs-lookup"><span data-stu-id="0137e-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="0137e-169">W przeciwnym razie nie będziesz mieć możliwości współtworzenia zmian.</span><span class="sxs-lookup"><span data-stu-id="0137e-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="0137e-170">Twoje rozwidlenie jest przywoływane za pośrednictwem Twojego osobistego konta użytkownika usługi GitHub, na przykład `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="0137e-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="0137e-171">Twoje polecenie klonowania powinno wyglądać podobnie do tego:</span><span class="sxs-lookup"><span data-stu-id="0137e-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="0137e-172">Po wyświetleniu monitu wprowadź swoje poświadczenia usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![Logowanie do usługi GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="0137e-174">Po wyświetleniu monitu wprowadź kod uwierzytelniania dwuetapowego.</span><span class="sxs-lookup"><span data-stu-id="0137e-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![Uwierzytelnianie dwuetapowe w usłudze GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="0137e-176">Twoje poświadczenia zostaną zapisane i będą używane do uwierzytelniania przyszłych żądań kierowanych do usługi GitHub.</span><span class="sxs-lookup"><span data-stu-id="0137e-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="0137e-177">To uwierzytelnianie należy wykonać jednokrotnie dla danego komputera.</span><span class="sxs-lookup"><span data-stu-id="0137e-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="0137e-178">Polecenie clone uruchamia i pobiera kopię plików repozytorium z rozwidlenia do nowego folderu na dysku lokalnym.</span><span class="sxs-lookup"><span data-stu-id="0137e-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="0137e-179">Nowy folder zostaje utworzony w bieżącym folderze.</span><span class="sxs-lookup"><span data-stu-id="0137e-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="0137e-180">Może to potrwać kilka minut w zależności od rozmiaru repozytorium.</span><span class="sxs-lookup"><span data-stu-id="0137e-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="0137e-181">Po zakończeniu możesz eksplorować folder, aby wyświetlić jego strukturę.</span><span class="sxs-lookup"><span data-stu-id="0137e-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="0137e-182">Konfigurowanie zdalnego połączenia nadrzędnego</span><span class="sxs-lookup"><span data-stu-id="0137e-182">Configure remote upstream</span></span>
<span data-ttu-id="0137e-183">Po sklonowaniu repozytorium skonfiguruj połączenie zdalne z repozytorium głównym przeznaczone tylko do odczytu, o nazwie **upstream**.</span><span class="sxs-lookup"><span data-stu-id="0137e-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="0137e-184">Z adresu URL połączenia nadrzędnego będziesz korzystać w celu synchronizowania Twojego lokalnego repozytorium z najnowszymi zmianami wykonywanymi przez innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="0137e-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="0137e-185">Polecenie **git remote** służy do ustawiania wartości konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0137e-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="0137e-186">Polecenie **fetch** służy do odświeżania informacji o gałęzi z repozytorium nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="0137e-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="0137e-187">Jeśli korzystasz z programu **Git Credential Manager**, użyj poniższych poleceń.</span><span class="sxs-lookup"><span data-stu-id="0137e-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="0137e-188">Zastąp elementy zastępcze \<repo\> i \<organization\>.</span><span class="sxs-lookup"><span data-stu-id="0137e-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="0137e-189">Wyświetl skonfigurowane wartości i potwierdź, że adresy URL są poprawne.</span><span class="sxs-lookup"><span data-stu-id="0137e-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="0137e-190">Upewnij się, że adresy URL źródła (**origin**) wskazują na Twoje osobiste rozwidlenie.</span><span class="sxs-lookup"><span data-stu-id="0137e-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="0137e-191">Upewnij się, że adresy URL repozytorium **upstream** wskazują repozytorium główne, takie jak MicrosoftDocs lub Azure.</span><span class="sxs-lookup"><span data-stu-id="0137e-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="0137e-192">Poniżej pokazany jest przykład danych wyjściowych połączenia zdalnego.</span><span class="sxs-lookup"><span data-stu-id="0137e-192">Example remote output is shown.</span></span> <span data-ttu-id="0137e-193">Fikcyjne konto usługi git o nazwie MyGitAccount jest konfigurowane przy użyciu osobistego tokenu dostępu w celu uzyskania dostępu do repozytorium azure-docs:</span><span class="sxs-lookup"><span data-stu-id="0137e-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="0137e-194">W przypadku popełnienia błędu możesz usunąć wartość połączenia zdalnego.</span><span class="sxs-lookup"><span data-stu-id="0137e-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="0137e-195">Aby usunąć wartość połączenia nadrzędnego, uruchom polecenie `git remote remove upstream`.</span><span class="sxs-lookup"><span data-stu-id="0137e-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0137e-196">Kolejne kroki</span><span class="sxs-lookup"><span data-stu-id="0137e-196">Next steps</span></span>
- <span data-ttu-id="0137e-197">Aby dowiedzieć się więcej na temat dodawania i aktualizowania zawartości, przejdź do strony [GitHub contribution workflows](how-to-write-workflows-major.md) (Przepływy pracy dotyczące współautorstwa w usłudze GitHub).</span><span class="sxs-lookup"><span data-stu-id="0137e-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>