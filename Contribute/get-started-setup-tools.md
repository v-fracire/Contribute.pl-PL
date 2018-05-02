---
title: Instalowanie narzędzi do tworzenia zawartości
description: Ten artykuł zawiera informacje przydatne podczas pobierania i instalowania narzędzi klienta potrzebnych do programu Git oraz edytowania plików ze znacznikami języka Markdown.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 01/04/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 0ca942e557640db1ba36d3f5b1064656ed3dea8d
ms.sourcegitcommit: 3ec397fab57ea582edb03a59609f62d886410ee8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="d482f-103">Instalowanie narzędzi do tworzenia zawartości</span><span class="sxs-lookup"><span data-stu-id="d482f-103">Install content authoring tools</span></span>

<span data-ttu-id="d482f-104">W tym artykule opisano kroki interaktywnego instalowania narzędzi klienta Git i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d482f-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d482f-105">Instalowanie programu [Git dla systemu Windows](https://git-scm.com/download/win)</span><span class="sxs-lookup"><span data-stu-id="d482f-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="d482f-106">[Instalowanie narzędzia Visual Studio Code](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="d482f-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="d482f-107">Jeśli wprowadzasz tylko drobne zmiany w artykule, *nie musisz* wykonywać kroków opisanych w tym artykule i możesz przejść bezpośrednio do [przepływu pracy dla drobnych zmian](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="d482f-107">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="d482f-108">Zaleca się, aby kroki te wykonali najważniejsi współautorzy. Pozwoli to na użycie [przepływu pracy dla znacznych/długofalowych zmian](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="d482f-108">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="d482f-109">Nawet jeśli masz uprawnienia do zapisu w repozytorium głównym, *zdecydowanie zalecamy rozwidlenie i sklonowanie repozytorium*, dzięki czemu będziesz mieć uprawnienia do odczytu/zapisu. Pozwoli to na przechowywanie proponowanych zmian w Twoim rozwidleniu. W tym przewodniku założono, że czynności te zostały wykonane.</span><span class="sxs-lookup"><span data-stu-id="d482f-109">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="d482f-110">Instalowanie narzędzi klienckich usługi Git w systemie Windows</span><span class="sxs-lookup"><span data-stu-id="d482f-110">Install Git client tools on Windows</span></span>

 <span data-ttu-id="d482f-111">Zainstaluj najnowszą wersję [narzędzi klienckich dla systemu Git organizacji Software Freedom Conservancy](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="d482f-111">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="d482f-112">Ta instalacja obejmuje system kontroli wersji Git oraz powłokę Git Bash, czyli aplikację wiersza polecenia służącą do interakcji z lokalnym repozytorium Git.</span><span class="sxs-lookup"><span data-stu-id="d482f-112">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="d482f-113">Jeśli wolisz graficzny interfejs użytkownika od interfejsu wiersza polecenia, zobacz [stronę z informacjami o dostępnych klientach z graficznym interfejsem użytkownika organizacji Software Freedom Conservancy](https://git-scm.com/downloads/guis) i zapoznaj się z takimi popularnymi rozwiązaniami, jak [program GitHub Desktop dla usługi GitHub](https://desktop.github.com/) lub [edytor Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx).</span><span class="sxs-lookup"><span data-stu-id="d482f-113">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="d482f-114">Postępuj zgodnie z instrukcjami dla wybranego klienta dotyczącymi instalacji i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d482f-114">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="d482f-115">Z następnego artykułu dowiesz się, jak wykonać [konfigurowanie lokalnego repozytorium Git](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="d482f-115">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="d482f-116">Dodatkowe zasoby dotyczące systemu Git są dostępne w tym miejscu: [Terminologia Git](https://help.github.com/articles/github-glossary) | [Podstawy Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Szkolenia dotyczące Git i GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="d482f-116">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="d482f-117">Zrozumienie edytorów języka Markdown</span><span class="sxs-lookup"><span data-stu-id="d482f-117">Understand Markdown editors</span></span>

<span data-ttu-id="d482f-118">Markdown to prosty język znaczników, łatwy do odczytywania oraz do nauczenia się.</span><span class="sxs-lookup"><span data-stu-id="d482f-118">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="d482f-119">Z tego powodu stał się on szybko standardem w branży.</span><span class="sxs-lookup"><span data-stu-id="d482f-119">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="d482f-120">W celu pisania artykułów w języku Markdown dobrze jest najpierw pobrać i zainstalować edytor tego języka.</span><span class="sxs-lookup"><span data-stu-id="d482f-120">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="d482f-121">Preferowanym narzędziem do edycji języka Markdown w firmie Microsoft jest [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="d482f-121">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="d482f-122">Innym popularnym narzędziem do edytowania języka Markdown jest [Atom](https://atom.io).</span><span class="sxs-lookup"><span data-stu-id="d482f-122">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="d482f-123">Teksty w języku Markdown są zapisywane w plikach z rozszerzeniem .md.</span><span class="sxs-lookup"><span data-stu-id="d482f-123">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="d482f-124">Dodatkowe szczegółowe informacje dotyczące pisania w języku Markdown, m.in. podstawowe informacje dotyczące języka Markdown oraz informacje o funkcjach obsługiwanych przez niestandardowe rozszerzenia języka Markdown na platformie OPS, zostały omówione w artykule [Jak używać języka Markdown](how-to-write-use-markdown.md).</span><span class="sxs-lookup"><span data-stu-id="d482f-124">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="d482f-125">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d482f-125">Visual Studio Code</span></span>

<span data-ttu-id="d482f-126">Narzędzie [Visual Studio Code](https://code.visualstudio.com/), znane także jako VS Code, to lekki edytor, który działa w systemach Windows, Linux i na komputerach Mac.</span><span class="sxs-lookup"><span data-stu-id="d482f-126">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="d482f-127">Obejmuje integrację z usługą Git oraz obsługę rozszerzeń.</span><span class="sxs-lookup"><span data-stu-id="d482f-127">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="d482f-128">Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="d482f-128">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="d482f-129">Strona główna programu VS Code powinna prawidłowo wykryć system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="d482f-129">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="d482f-130">Windows</span><span class="sxs-lookup"><span data-stu-id="d482f-130">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="d482f-131">Mac</span><span class="sxs-lookup"><span data-stu-id="d482f-131">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="d482f-132">Linux</span><span class="sxs-lookup"><span data-stu-id="d482f-132">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="d482f-133">Aby uruchomić program VS Code i otworzyć bieżący folder, uruchom polecenie `code .` w wierszu polecenia lub powłoce bash.</span><span class="sxs-lookup"><span data-stu-id="d482f-133">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="d482f-134">Jeśli bieżący folder jest częścią lokalnego repozytorium usługi Git, integracja z usługą GitHub automatycznie pojawi się w programie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d482f-134">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d482f-135">Kolejne kroki</span><span class="sxs-lookup"><span data-stu-id="d482f-135">Next steps</span></span>

<span data-ttu-id="d482f-136">Teraz możesz przystąpić do [konfigurowania lokalnego repozytorium Git](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="d482f-136">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
