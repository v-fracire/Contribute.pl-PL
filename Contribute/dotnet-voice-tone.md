---
title: Wytyczne dotyczące stron czasowników i tonu dla materiałów dodawanych do dokumentacji platformy .NET
description: Poznaj nasze wytyczne dotyczące stron czasowników i tonu, zapoznając się z przykładami naszego stylu i ich porównaniem z przykładami niespełniającymi naszych wytycznych.
ms.date: 11/07/2018
ms.openlocfilehash: cf78bb5d476d35b9b168b619e90e8f372103cb93
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609698"
---
# <a name="voice-and-tone-guidelines"></a>Wytyczne dotyczące stron czasowników i tonu

Twoje dokumenty czyta wielu ludzi, w tym informatycy i deweloperzy. Uczą się z nich platformy .NET i dowiadują, jak korzystać z niej w codziennej pracy. Twoim celem jest przygotowywanie doskonałej dokumentacji, która pomoże czytelnikom w osiągnięciu założonego celu. Nasze wytyczne pomagają w tym. Nasz przewodnik po stylu zawiera następujące rekomendacje:

Czytając ten przewodnik po stylu, można zapoznać się z przykładami dla każdej z nich. Napisaliśmy ten przewodnik zgodnie z naszymi wytycznymi, aby podać przykłady do naśladowania przy tworzeniu dokumentacji dla platformy .NET. Pokazaliśmy także przeciwne przykłady, dzięki którym zobaczysz, jak wyglądają artykuły, gdy nie stosuje się naszych wytycznych.

## <a name="use-a-conversational-tone"></a>Używaj konwersacyjnego tonu

### <a name="appropriate-style"></a>Odpowiedni styl

Chcemy, aby nasza dokumentacja miała konwersacyjny ton. Podczas czytania dowolnego z naszych samouczków lub objaśnień powinno się mieć wrażenie prowadzenia rozmowy z autorem. Treść powinna mieć nieformalny, konwersacyjny charakter i być bogata w informacje. Czytelnicy powinni mieć wrażenie, że słuchają autora objaśniającego im pojęcia.

### <a name="inappropriate-style"></a>Nieodpowiedni styl

Kontrast między stylem konwersacyjnym i stylem znanym z bardziej akademickiego podejścia do tematów technicznych jest wyraźny. Zasoby drugiego rodzaju są bardzo pomocne, ale ich autorzy pisali je z użyciem stylu znacznie różniącego się od tego zastosowanego w naszej dokumentacji. Czytając czasopismo akademickie, daje się zauważyć zupełnie inny ton i zupełnie inny styl pisania. Czytelnik czuje, że czyta suche sprawozdanie dotyczące zupełnie niestrawnego tematu.  

Pierwszy akapit powyżej jest zgodny z naszą rekomendacją co do konwersacyjnego stylu. Drugi jest w stylu bardziej akademickim. Od razu widać różnicę. 

## <a name="write-in-second-person"></a>Pisz w drugiej osobie

### <a name="appropriate-style"></a>Odpowiedni styl

Swoje artykuły pisz tak, jakby była to bezpośrednia rozmowa z czytelnikiem. Często sięgaj po drugą osobę (tak jak ja w tych dwóch zdaniach). Druga osoba nie musi koniecznie oznaczać zwracania się co chwilę per „ty”. Pisz bezpośrednio do czytelnika. Pisz zdania rozkazujące. Mów czytelnikowi, czego Twoim zdaniem powinien się nauczyć.

### <a name="inappropriate-style"></a>Nieodpowiedni styl

Autor może również zdecydować się na stosowanie osoby trzeciej. Stosując takie podejście, musi znaleźć jakiś zaimek lub rzeczownik, z użyciem którego będzie zwracał się do czytelnika. Czytelnicy często uznają taki styl z trzecią osobą za mniej angażujący i mniej przyjemy w czytaniu.

Pierwszy akapit jest zgodny z naszym zalecanym stylem. W drugim używana jest trzecia osoba. Pisz w drugiej osobie. Z pewnością uznasz, że taki tekst znacznie łatwiej się czyta.

## <a name="use-active-voice"></a>Używaj strony czynnej

Pisz swoje artykuły z użyciem strony czynnej. Strona czynna oznacza, że podmiot zdania wykonuje akcję (czasownik) w tym zdaniu. Jest to przeciwieństwo strony biernej, w której zdanie jest ułożone tak, że czynność jest wykonywana względem podmiotu zdania. Porównaj następujące przykłady:

>Kompilator przekształcił kod źródłowy w plik wykonywalny.

>Kod źródłowy został przekształcony w plik wykonywalny przez kompilator.

Pierwsze zdanie używa strony czynnej. Drugie zdanie zostało napisane z użyciem strony biernej. (Te dwa zdania to kolejny przykład każdego ze stylów).

Zalecamy stronę czynną, ponieważ jest znacznie czytelniejsza. Strona bierna może być trudniejsza w czytaniu.

## <a name="target-a-fifth-grade-reading-level"></a>Kieruj swój tekst do osoby czytającej na poziomie piątej klasy

Tę końcową wytyczną dajemy, ponieważ dla wielu z naszych czytelników angielski nie jest językiem macierzystym. Twoje artykuły trafiają do odbiorców z wielu krajów. Weź pod uwagę, że ich słownictwo może być znacznie uboższe od Twojego.

Z drugiej jednak strony wciąż piszesz do profesjonalistów z branży technicznej. Możesz przyjąć, że czytelnicy mają wiedzę z zakresu programowania i opanowali specyficzną dla niego terminologię. Programowanie obiektowe, klasa, obiekt, funkcja i metoda są znanymi terminami. Nie każdy czytelnik Twoich artykułów ma jednak stopień naukowy z informatyki. Jeśli zdecydujesz się używać terminów takich jak „idempotentność”, będzie trzeba je zdefiniować:

>Metoda `Close()` jest idempotentna, czyli że można wywołać ją wielokrotnie, a efekt będzie taki sam jak przy wywołaniu tylko raz.

## <a name="avoid-future-tense"></a>Unikaj czasu przyszłego

W niektórych językach innych niż angielski pojęcie czasu przyszłego nie pokrywa się z tym, co znamy z języka angielskiego. Używanie czasu przyszłego może utrudnić czytanie dokumentów. Dodatkowo przy korzystaniu z czasu przyszłego narzucającym się pytaniem jest „kiedy”. Jeśli powiesz „Znajomość powłoki PowerShell przyda Ci się”, oczywistym pytaniem dla czytelnika będzie, kiedy mu się przyda. Zamiast tego powiedz więc lepiej „Znajomość powłoki PowerShell jest przydatna”.

## <a name="what-is-it---so-what"></a>Co to jest — i co z tego?

Zawsze gdy prezentujesz czytelnikowi jakieś nowe pojęcie, najpierw je zdefiniuj, a dopiero wtedy wyjaśnij, dlaczego jest przydatne. Dla czytelnika ważne jest, aby zrozumiał, czym coś jest, zanim będzie w stanie zrozumieć wynikające z tego korzyści (lub tego wady).
