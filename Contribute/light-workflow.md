---
title: 'Przepływ pracy w usłudze GitHub: drobne lub rzadkie zmiany'
description: W tym artykule przedstawiono sposób korzystania z przepływu pracy dla współautorów wprowadzających drobne zmiany do artykułów w witrynie docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 10/06/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 8bde44d502e1942b0870df9dd546a97705c2bb4f
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
---
# <a name="github-contribution-workflow-for-minor-or-infrequent-changes"></a>Przepływ pracy w usłudze GitHub: drobne lub rzadkie zmiany

> [!IMPORTANT]
> W przypadku wszystkich repozytoriów publikowanych w witrynie docs.microsoft.com stosowany jest [Kodeks postępowania firmy Microsoft dotyczący rozwiązań typu open source](https://opensource.microsoft.com/codeofconduct/) lub [Kodeks postępowania organizacji .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Aby uzyskać więcej informacji, zobacz [często zadawane pytania dotyczące kodu postępowania](https://opensource.microsoft.com/codeofconduct/faq/). W przypadku pytań lub komentarzy możesz też napisać na adres [opencode@microsoft.com](mailto:opencode@microsoft.com) lub [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org).<br>
>
> Drobne poprawki lub wyjaśnienia dotyczące dokumentacji i przykładów kodu w repozytoriach publicznych znajdują się w [Warunkach korzystania z witryny docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Nowe lub ważne zmiany spowodują wygenerowanie komentarza w żądaniu ściągnięcia z prośbą o przesłanie internetowej umowy licencyjnej współautorstwa (CLA), jeśli nie jesteś pracownikiem firmy Microsoft. Zanim zaakceptujemy żądanie ściągnięcia, musisz wypełnić formularz online.

## <a name="overview"></a>Omówienie

Ten przepływ pracy dotyczy wprowadzania drobnych lub rzadkich zmian przy użyciu internetowego edytora języka znaczników Markdown usługi GitHub. Możliwości użytkownika w edytorze usługi GitHub są ograniczone, ponieważ interfejs użytkownika nie obsługuje wszystkich operacji Git i scenariuszów tworzenia. Jeśli chcesz tworzyć obszerną zawartość lub potrzebujesz pomocy dotyczącej zaawansowanych funkcji Git (takich jak zarządzanie gałęziami i zaawansowane rozwiązywanie konfliktów scalania), zapoznaj się z [przepływem pracy dotyczącym istotnych lub długotrwałych zmian](full-workflow.md).

## <a name="procedure-for-using-the-github-editor-to-propose-your-changes"></a>Procedura proponowania zmian przy użyciu edytora GitHub

1. Przejdź do repozytorium GitHub i pliku Markdown odpowiadających artykułowi. Możesz to zrobić na jeden z następujących sposobów:

   - Odszukaj artykuł, przeglądając pliki Markdown w powiązanym repozytorium GitHub.
   - Przejdź do artykułu w witrynie [docs.microsoft.com](https://docs.microsoft.com/) i wybierz link **Edytuj** w prawym górnym rogu strony.

     ![Lokalizacja linku Edytuj](./media/light-workflow/contributetogit.png)

2. Wybierz ikonę ołówka (**Edytuj ten plik**), aby przejść do trybu edycji:

    ![Lokalizacja ikony ołówka](./media/light-workflow/editicon.png)

3. Wprowadź zmiany przy użyciu języka Markdown na karcie **Edit file** (Edytuj plik), a następnie przejrzyj wprowadzone zmiany na karcie **Preview changes** (Podgląd zmian). Obsługa edytora jest dość prosta, ale jeśli potrzebujesz pomocy, zapoznaj się z następującymi przewodnikami:

   - [Jak używać języka Markdown](how-to-write-use-markdown.md)
   - [Tworzenie plików w usłudze GitHub](https://github.com/blog/1327-creating-files-on-github)
   - [Przekazywanie plików do repozytoriów](https://github.com/blog/2105-upload-files-to-your-repositories)

4. Przewiń stronę do dołu, gdzie zobaczysz jedną z następujących opcji:

   - **Propose file change** (Zaproponuj zmianę pliku): ta opcja pojawia się, gdy masz dostęp do repozytorium w trybie tylko do odczytu, na przykład [edytowanie plików w repozytorium innego użytkownika](https://help.github.com/articles/editing-files-in-another-user-s-repository/). W tym przypadku usługa GitHub utworzy gałąź „poprawka” w Twoim rozwidleniu repozytorium (jeśli rozwidlenie nie istnieje, automatycznie je tworzy). Po wybraniu opcji **Propose file change** (Zaproponuj zmianę pliku) zostanie wyświetlona strona **Comparing changes** (Porównywanie zmian), na której możesz sprawdzić swoje zmiany. Następnie wybierz przycisk **Create pull request** (Utwórz żądanie ściągnięcia), aby przesłać wprowadzone zmiany do kolejki żądań ściągnięcia, i przejdź do [następnej sekcji](#pull-request-processing).

   - **Commit changes** (Zatwierdź zmiany): ta opcja pojawia się, gdy masz uprawnienia do zapisu w repozytorium, np. [edytowanie plików we własnym repozytorium](https://help.github.com/articles/editing-files-in-your-repository/). W takim przypadku usługa GitHub daje dwie opcje zapisania wprowadzonych zmian:

     - **Commit directly to the `<branch-name>` branch** (Zatwierdź bezpośrednio w gałęzi), gdzie `<branch-name>` to nazwa gałęzi aktywnej w momencie kliknięcia przycisku **Edit** (Edytuj). Ta opcja powoduje wprowadzenie zmian bezpośrednio w gałęzi, a nie przy użyciu żądania ściągnięcia. W tym momencie praca jest zakończona.

     - Opcja **Create a new branch for this commit and start a pull request** (Utwórz nową gałąź dla tego zatwierdzenia i uruchom żądanie ściągnięcia) powoduje wyświetlenie monitu o utworzenie nowej gałęzi z nazwą domyślną. Po wybraniu opcji **Propose file change** (Zaproponuj zmianę pliku) zostanie wyświetlona strona **Comparing changes** (Porównywanie zmian), na której możesz sprawdzić swoje zmiany. Następnie wybierz przycisk **Create pull request** (Utwórz żądanie ściągnięcia), aby przesłać wprowadzone zmiany do kolejki żądań ściągnięcia, i przejdź do [następnej sekcji](#pull-request-processing).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Kolejne kroki

- Przejdź do artykułu „Writing essentials” (Podstawy pisania), aby dowiedzieć się więcej o języku Markdown, składni jego rozszerzeń itd.
