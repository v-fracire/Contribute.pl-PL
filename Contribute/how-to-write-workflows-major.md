---
title: 'Przepływ pracy dotyczący współtworzenia dokumentacji w usłudze GitHub: istotne lub długotrwałe zmiany'
description: W tym artykule przedstawiono sposób korzystania z przepływu pracy dla współautorów w przypadku dokonywania istotnych zmian w artykułach w witrynie docs.microsoft.com.
ms.date: 08/30/2017
ms.openlocfilehash: 31f9421fc5edbc2f65c5ff20a86da08c70211ec7
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239830"
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>Przepływ pracy dotyczący współtworzenia dokumentacji w usłudze GitHub: istotne lub długotrwałe zmiany

> [!IMPORTANT]
> W przypadku wszystkich repozytoriów publikowanych w witrynie docs.microsoft.com stosowany jest [Kodeks postępowania firmy Microsoft dotyczący rozwiązań typu open source](https://opensource.microsoft.com/codeofconduct/) lub [Kodeks postępowania organizacji .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Aby uzyskać więcej informacji, zobacz [często zadawane pytania dotyczące kodu postępowania](https://opensource.microsoft.com/codeofconduct/faq/). W przypadku pytań lub komentarzy możesz też napisać na adres [opencode@microsoft.com](mailto:opencode@microsoft.com) lub [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org).<br>
>
> Drobne poprawki lub wyjaśnienia dotyczące dokumentacji i przykładów kodu w repozytoriach publicznych znajdują się w [Warunkach korzystania z witryny docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Nowe lub ważne zmiany spowodują wygenerowanie komentarza w żądaniu ściągnięcia z prośbą o przesłanie internetowej umowy licencyjnej współautorstwa (CLA), jeśli nie jesteś pracownikiem firmy Microsoft. Zanim scalimy żądanie ściągnięcia, musisz wypełnić formularz online.

## <a name="overview"></a>Omówienie

Ten przepływ pracy jest przeznaczony dla współautorów, którzy muszą wprowadzić istotne zmiany lub będą często tworzyć dokumentację w repozytorium. Współautorzy, którzy często tworzą dokumentację, zwykle dokonują trwałych lub długookresowych zmian, które przechodzą wiele cykli kompilacji, weryfikacji i przemieszczania lub trwają wiele dni przed wyrejestrowaniem i scaleniem żądania ściągnięcia.

Przykłady tego typu zmian to:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Terminologia

Zanim rozpoczniemy, omówmy niektóre terminy i krótkie nazwy dotyczące systemu Git i serwisu GitHub użyte w tym przepływie pracy. Nie musisz czytać o nich teraz. Wystarczy wiedzieć, że są tu na ich temat informacje i można odwołać się do tej sekcji, jeśli trzeba będzie zweryfikować jakąś definicję.

| Nazwa | Opis |
|-----------|-------------|
|rozwidlenie|Zwykle pojęcie to jest używane w formie rzeczownika i oznacza kopię głównego repozytorium w serwisie GitHub. W praktyce rozwidlenie stanowi po prostu kolejne repozytorium. Jego cechą charakterystyczną jest to, że serwis GitHub zachowuje połączenie z repozytorium głównym/nadrzędnym. Pojęcie to jest czasami używane w formie czasownika, np. w komunikacie „You must fork the repository first” („Musisz najpierw utworzyć rozwidlenie repozytorium”).|
|połączenie zdalne|Nazwane połączenie z repozytorium zdalnym, np. połączenie zdalne „pierwotne” lub „nadrzędne”. W usłudze Git takie połączenia są nazywane połączeniami zdalnymi, ponieważ służą do odwoływania się do repozytorium hostowanego na innym komputerze. W tym przepływie połączenie zdalne jest zawsze połączeniem z repozytorium w serwisie GitHub.|
|połączenie pierwotne|Nazwa przypisana do połączenia między repozytorium lokalnym a repozytorium, z którego zostało ono sklonowane. W tym przepływie połączenie pierwotne stanowi połączenie z rozwidleniem. Czasami służy jako krótka nazwa samego repozytorium origin, jak w przypadku komunikatu „Remember to push your changes to origin” (Pamiętaj, aby przekazać zmiany do repozytorium origin).|
|połączenie nadrzędne|Tak jak połączenie zdalne pierwotne połączenie nadrzędne jest nazwanym połączeniem z innym repozytorium. W tym przepływie pracy połączenie nadrzędne stanowi połączenie między repozytorium lokalnym i repozytorium głównym, z którego zostało utworzone rozwidlenie. Czasami służy jako krótka nazwa samego repozytorium upstream, jak w przypadku komunikatu „Remember to pull the changes from upstream” (Pamiętaj, aby ściągać zmiany z repozytorium upstream).|

## <a name="workflow"></a>Przepływ pracy

>[!IMPORTANT]
> Należy wykonać czynności w sekcji [Konfiguracja](get-started-setup-github.md), jeśli jeszcze nie zostały wykonane. Ta sekcja zawiera instrukcje konfigurowania konta w usłudze GitHub, instalowania powłoki Git Bash oraz edytora języka Markdown, tworzenia rozwidlenia oraz konfigurowania repozytorium lokalnego. Jeśli nie znasz pojęć dotyczących usług Git i GitHub, takich jak repozytorium lub gałąź, przejrzyj najpierw artykuł [Git and GitHub fundamentals](git-github-fundamentals.md) (Podstawy usług Git i GitHub).

W tym przepływie pracy zmiany odbywają się w powtarzających się cyklach. Zaczynając od lokalnego repozytorium urządzenia, są przesyłane z powrotem do rozwidlenia w serwisie GitHub, do repozytorium głównego serwisu GitHub i znowu z powrotem lokalnie podczas wdrażania zmian innych współautorów.

### <a name="use-github-flow"></a>Stosowanie przepływu usługi GitHub

Jak pamiętamy z artykułu [Git and GitHub fundamentals](git-github-fundamentals.md#git) (Podstawy usług Git i GitHub), repozytorium w usłudze Git zawiera gałąź główną oraz dodatkowe gałęzie pracy w toku, które nie zostały zintegrowane z gałęzią główną. Gdy wprowadzasz zestaw logicznie powiązanych zmian, najlepszym rozwiązaniem jest utworzenie *gałęzi roboczej* do zarządzania zmianami przy użyciu przepływu pracy. Nazywamy ją tutaj gałęzią roboczą, gdyż jest to przestrzeń robocza do iterowania/aktualizowania zmian, aż będzie je można znowu zintegrować z gałęzią główną.

Wyizolowanie powiązanych zmian do określonej gałęzi umożliwia kontrolowanie i wprowadzanie tych zmian niezależnie oraz przeznaczanie ich na określony czas wydania w cyklu publikowania. W praktyce w zależności od rodzaju wykonywanych prac może dojść do tego, że w repozytorium będzie kilka gałęzi roboczych. Praca nad wieloma gałęziami równocześnie nie należy do rzadkości, a wtedy każda z nich reprezentuje inny projekt.

>[!TIP]
>Wprowadzanie zmian w gałęzi głównej *nie jest* dobrym rozwiązaniem. Wyobraźmy sobie, że użyliśmy gałęzi głównej, aby wprowadzić serię zmian w celu wydania funkcji w określonym momencie. Dokonaliśmy zmian i czekamy na ich wydanie. Tymczasem pojawiło się nagłe żądanie wprowadzenia poprawki, więc wprowadziliśmy zmianę do pliku w gałęzi głównej, po czym opublikowaliśmy zmianę. W tym przykładzie opublikowaliśmy nieumyślnie zarówno poprawkę, *jak i* zmiany zachowane do wydania określonego dnia.

Teraz utworzymy nową gałąź roboczą w lokalnym repozytorium, aby przechwycić proponowane zmiany. Każdy klient usługi Git jest inny, dlatego należy korzystać z pomocy dotyczącej preferowanego klienta. Omówienie procesu można zobaczyć w przewodniku usługi GitHub w artykule [GitHub flow](https://guides.github.com/introduction/flow/) (Przepływ usługi GitHub).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Kolejne kroki

Gotowe. Tworzenie zawartości w witrynie docs.microsoft.com zostało zakończone.

- Aby dowiedzieć się więcej o języku Markdown, składni jego rozszerzeń itd., przejdź do sekcji „Writing essentials” (Podstawy pisania).
