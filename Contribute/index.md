---
title: Przewodnik współautora witryny Microsoft Docs — omówienie
description: W tym przewodniku opisano sposób współtworzenia zawartości witryny dokumentacji firmy Microsoft, docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 04/17/2018
ms.openlocfilehash: 6206f61a69c14575a726da9ce64ad0b765c7aa87
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251442"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Przewodnik współautora witryny Microsoft Docs — omówienie

Przewodnik współautora witryny [docs.microsoft.com](https://docs.microsoft.com) (Docs) — Zapraszamy!

Kilka naszych zestawów dokumentacji to zestawy typu „open source” hostowane w usłudze GitHub. Coraz więcej zespołów w firmie Microsoft przez cały czas wdraża ten model. Nawet zestawy dokumentów, które nie działają całkowicie jako technologia typu „open source”, mają dostępne publicznie repozytoria, w których można wykonywać żądania ściągnięcia. Dzięki temu komunikacja między inżynierami projektu, zespołami ds. zawartości i naszymi klientami jest płynniejsza i ulepszona. Praca w środowisku otwartym oferuje następujące korzyści:

- Planowanie repozytoriów typu „open source” w środowisku otwartym w celu uzyskiwania opinii na temat najbardziej potrzebnych dokumentów.
- Przeglądanie repozytoriów typu „open source” w środowisku otwartym w celu publikowania najbardziej użytecznej zawartości w naszej pierwszej wersji.
- Aktualizowanie repozytoriów typu „open source” w środowisku otwartym w celu ułatwienia stałego udoskonalania zawartości.

Środowisko użytkownika w witrynie [docs.microsoft.com](https://docs.microsoft.com) bezpośrednio integruje przepływy pracy usługi [GitHub](https://github.com), aby jeszcze bardziej ułatwić pracę. Rozpocznij od [edytowania przeglądanego dokumentu](#quick-edits-to-existing-documents). Lub pomóż [recenzować nowe tematy](#review-open-prs) albo [tworzyć opisy problemów z jakością](#create-quality-issues).

> [!IMPORTANT]
> W przypadku wszystkich repozytoriów publikowanych w witrynie docs.microsoft.com stosowany jest [Kodeks postępowania firmy Microsoft dotyczący rozwiązań typu open source](https://opensource.microsoft.com/codeofconduct/) lub [Kodeks postępowania organizacji .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Aby uzyskać więcej informacji, zobacz [często zadawane pytania dotyczące kodu postępowania](https://opensource.microsoft.com/codeofconduct/faq/). W przypadku pytań lub komentarzy możesz też napisać na adres [opencode@microsoft.com](mailto:opencode@microsoft.com) lub [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org).<br>
>
> Drobne poprawki lub wyjaśnienia dotyczące dokumentacji i przykładów kodu w repozytoriach publicznych znajdują się w [Warunkach korzystania z witryny docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Nowe lub ważne zmiany powodują wygenerowanie komentarza w żądaniu ściągnięcia z prośbą o przesłanie internetowej umowy licencyjnej współautorstwa (CLA), jeśli nie jesteś pracownikiem firmy Microsoft. Zanim zrecenzujemy lub zaakceptujemy żądanie ściągnięcia, musisz wypełnić formularz online.

## <a name="quick-edits-to-existing-documents"></a>Szybkie edycje istniejących dokumentów

Szybkie edycje usprawniają proces zgłaszania i naprawiania drobnych błędów i pominięć w dokumentach. Mimo wszelkich wysiłków drobne błędy gramatyczne i błędy pisowni przedostają się do naszych publikowanych dokumentów. Można tworzyć problemy w celu zgłaszania pomyłek, ale szybszym i prostszym sposobem naprawienia błędu jest utworzenie żądania ściągnięcia. W prawie każdym artykule jest wyświetlany przycisk edycji, taki jak pokazany na poniższym rysunku. Kliknięcie przycisku **Edytuj** spowoduje przejście do pliku źródłowego w usłudze GitHub.

![Lokalizacja linku Edytuj](./media/index/edit-article.png)

Następnie kliknij ikonę ołówka pokazaną na poniższym rysunku, aby edytować artykuł.

> [!NOTE]
> Jeśli ikona ołówka jest nieaktywna, musisz zalogować się do konta usługi GitHub lub utworzyć nowe konto. Wprowadź zmiany w edytorze internetowym. Możesz kliknąć kartę **Podgląd zmian**, aby sprawdzić formatowanie zmiany.

![Lokalizacja ikony ołówka](./media/index/editicon.png)

Po wprowadzeniu zmian przewiń stronę w dół. Wprowadź tytuł i opis żądania ściągnięcia, a następnie kliknij pozycję **Zaproponuj zmianę pliku**, jak pokazano na poniższym rysunku:

![proponowanie zmiany](./media/index/submit-pull-request.png)

Gotowe. Członkowie zespołu ds. zawartości przejrzą i scalą żądanie ściągnięcia. Możesz otrzymać opinię z żądaniem zmian, jeśli wprowadzono większe zmiany.

Interfejs użytkownika służący do edycji w usłudze GitHub reaguje na uprawnienia dotyczące repozytorium. Poprzednie obrazy są dokładne w przypadku współautorów, którzy nie mają uprawnień do zapisu w repozytorium docelowym. Usługa GitHub automatycznie tworzy rozwidlenie repozytorium docelowego na Twoim koncie. Jeśli masz uprawnienia do zapisu w repozytorium docelowym, usługa GitHub tworzy nową gałąź w tym repozytorium. Nazwa gałęzi ma format **\<identyfikator_usługi_GitHub\>-patch-n** korzystający z identyfikatora usługi GitHub oraz numerycznego identyfikatora gałęzi poprawki.

Żądania ściągnięcia są używane dla wszystkich zmian, nawet w przypadku współautorów z dostępem do zapisu. Większość repozytoriów ma chronioną gałąź `master`, dlatego aktualizacje muszą być przesyłane jako żądania ściągnięcia.

Środowisko edytowania w przeglądarce jest najlepsze w przypadku drobnych lub rzadko wprowadzanych zmian. Jeśli tworzysz obszerną zawartość lub używasz zaawansowanych funkcji Git (takich jak zarządzanie gałęziami i zaawansowane rozwiązywanie konfliktów scalania), musisz [utworzyć rozgałęzienie repozytorium i pracować lokalnie](how-to-write-workflows-major.md).

## <a name="review-open-prs"></a>Recenzowanie otwartych żądań ściągnięcia

Możesz czytać nowe tematy przed ich opublikowaniem, sprawdzając aktualnie otwarte żądania ściągnięcia. Recenzje są zgodne z procesem [przepływu usługi GitHub](https://guides.github.com/introduction/flow/). Proponowane aktualizacje lub nowe artykuły są widoczne w repozytoriach publicznych. Zapoznaj się z nimi i dodaj komentarze. Przejrzyj nasze repozytoria dokumentów i sprawdź otwarte żądania ściągnięcia w interesujących Cię obszarach. Opinie członków społeczności na temat proponowanych aktualizacji pomagają całej społeczności.

## <a name="create-quality-issues"></a>Tworzenie problemów z jakością

Praca nad naszymi dokumentami trwa przez cały czas. Dobrze opisane problemy pomagają nam skoncentrować wysiłki na obszarach najistotniejszych dla społeczności. Im więcej szczegółów podasz, tym bardziej pomocny będzie problem. Powiedz nam, jakich informacji szukano. Powiedz nam, których terminów wyszukiwania użyto. Jeśli nie możesz rozpocząć pracy, powiedz nam, jak chcesz zacząć eksplorowanie nieznanej technologii.

Rozmowa o potrzebach rozpoczyna się od opisu problemów. Zespół ds. zawartości odpowie na te problemy, przedstawiając pomysły dotyczące treści do dodania, i poprosi o Twoją opinię. Po utworzeniu wersji próbnej poprosimy Cię o [recenzję żądania ściągnięcia](#review-open-prs).

## <a name="get-more-involved"></a>Zwiększanie zaangażowania

Inne tematy pomogą Ci w produktywny sposób rozpocząć współtworzenie zawartości witryny Microsoft Docs. Zawierają one objaśnienia dotyczące pracy z repozytoriami usługi GitHub, narzędziami języka znaczników Markdown oraz rozszerzeniami używanymi na platformie Microsoft Docs.
