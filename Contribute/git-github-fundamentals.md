---
title: Git i GitHub — podstawy dla witryny Docs
description: Ten artykuł zawiera omówienie usługi GitHub, repozytorium GitHub, sposobu organizowania zawartości oraz konwencji nazewnictwa używanych dla witryny docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 5f7f90b69953e23833906202c739d2168b139d7e
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469491"
---
# <a name="git-and-github-essentials-for-docs"></a>Git i GitHub — podstawy dla witryny Docs

## <a name="overview"></a>Omówienie

Jako współautor zawartości witryny Docs będziesz wchodzić w interakcje z wieloma narzędziami i procesami. Będziesz pracować nad tym samym projektem równolegle z innymi współautorami — być może nad dokładnie tą samą zawartością, a nawet w tym samym czasie. Wszystko to jest możliwe dzięki usłudze Git i oprogramowaniu GitHub.

Usługa Git to system kontroli wersji typu open source. Umożliwia współpracę tego typu w ramach projektu dzięki *rozproszonej kontroli wersji* plików znajdujących się w *repozytoriach*. Usługa Git pozwala na integrowanie strumieni pracy wykonywanej przez różnych współautorów wraz z upływem czasu dla danego repozytorium.

GitHub to internetowa usługa hostingowa repozytoriów Git, takich jak używane do przechowywania zawartości witryny [docs.microsoft.com](https://docs.microsoft.com). Dla każdego projektu w usłudze GitHub hostowane jest główne repozytorium, z poziomu którego współautorzy mogą wykonywać kopie na potrzeby własnej pracy.

## <a name="git"></a>Git

Jeśli znasz systemy scentralizowanej kontroli wersji (takie jak Team Foundation Server, SharePoint lub Visual SourceSafe), zauważysz, że usługa Git oferuje unikatowy przepływ pracy związany ze współtworzeniem oraz terminologię do obsługi modelu rozproszonego. Na przykład nie można używać funkcji blokowania plików, która jest zwykle skojarzona z operacjami zaewidencjonowania i wyewidencjonowania. Usługa Git faktycznie zajmuje się zmianami na jeszcze większym poziomie szczegółowości: porównuje pliki bajt po bajcie.

Usługa Git używa również struktury warstwowej do przechowywania zawartości projektu i zarządzania nią:

- *Repozytorium* — (w języku angielskim określane również jako *repo*) najwyższy poziom magazynu. Repozytorium zawiera co najmniej jedną gałąź.
- *Gałąź* — jednostka magazynu, która zawiera pliki i foldery tworzące zestaw zawartości projektu. Gałęzie rozdzielają strumienie pracy (zwykle określane jako wersje). Tworzone elementy są zawsze przygotowywane i dostosowywane pod kątem określonej gałęzi. Wszystkie repozytoria zawierają gałąź domyślną (przeważnie zwaną „główną”) oraz co najmniej jedną gałąź przeznaczoną do scalenia z powrotem z główną gałęzią. Gałąź główna służy jako bieżąca wersja i pojedyncze wiarygodne źródło dla konkretnego projektu. Jest to poziom nadrzędny, z którego tworzone są wszystkie inne gałęzie w repozytorium.

Współautorzy używają usługi Git do aktualizowania repozytoriów i manipulowania nimi lokalnie oraz na poziomie usługi GitHub:

- W środowisku lokalnym za pośrednictwem narzędzi, takich jak konsola Bash usługi Git, która obsługuje polecenia usługi Git służące do zarządzania repozytoriami lokalnymi i komunikowania się z repozytoriami GitHub.
- W witrynie [www.github.com](https://www.github.com), która umożliwia integrowanie usługi Git w celu uzgadniania elementów tworzonych przez współautorów i przekazywanych z powrotem do głównego repozytorium

## <a name="github"></a>GitHub

> [!NOTE]
> Mimo że wskazówki dotyczące witryny Docs opierają się na użyciu usługi GitHub, niektóre zespoły używają usługi Visual Studio Team Services do hostowania repozytoriów usługi Git. Klient programu Visual Studio Team Explorer oferuje graficzny interfejs użytkownika na potrzeby interakcji z repozytoriami usługi Team Services, co jest alternatywą do korzystania z poleceń usługi Git w wierszu polecenia.
> </br>
> Ponadto wiele poniższych wytycznych opracowano jako najlepsze rozwiązania na podstawie lat doświadczenia w hostowaniu zawartości usług platformy Azure w usłudze GitHub. Mogą być one wymagane w przypadku niektórych repozytoriów witryny Docs.

Wszystkie przepływy rozpoczynają się i kończą na poziomie usługi GitHub, w której przechowywane jest główne repozytorium wszystkich projektów witryny Docs. Kopie tworzone przez współautorów do własnego użytku są dystrybuowane na wiele komputerów. Te kopie są ostatecznie uzgadniane z głównym repozytorium projektu w usłudze GitHub.

### <a name="directory-organization"></a>Organizacja katalogów

Jak wspomniano wcześniej, domyślna/główna gałąź projektu działa jak bieżąca wersja zawartości projektu. Zawartość głównej gałęzi — i gałęzi utworzonych na jej podstawie — jest luźno powiązana z organizacją artykułów na odpowiednich stronach witryny Docs. Podkatalogi są używane do oddzielania podobnej zawartości (takiej jak usługi), zawartości multimedialnej (takiej jak pliki obrazów) i plików dołączanych, które umożliwiają wielokrotne użycie zawartości.

Zwykle katalog główny `articles` znajduje się poza katalogiem głównym repozytorium. Katalog articles zawiera zbiór podkatalogów. Artykuły w podkatalogach są sformatowane jako pliki Markdown z rozszerzeniem *.md*. Niektóre repozytoria, które obsługują wiele usług, takie jak repozytorium [https://github.com/microsoft/Azure-Docs](https://github.com/microsoft/Azure-Docs), korzystają z ogólnego podkatalogu `/articles`. Inne mogą używać nazwy powiązanej z usługą, takiej jak repozytorium [https://github.com/microsoft/IntuneDocs](https://github.com/microsoft/IntuneDocs), które korzysta z katalogu `/IntuneDocs`.

W katalogu głównym tego katalogu można znaleźć ogólne artykuły dotyczące usługi lub produktu jako całości. Przeważnie można potem przejść do innego zestawu podkatalogów odpowiadających funkcjom/usługom lub typowym scenariuszom. Na przykład artykuły typu „maszyna wirtualna” platformy Azure znajdują się w podkatalogu `/virtual-machines`, artykuły typu „poznawanie i eksplorowanie” dotyczące usługi Intune — w podkatalogu `/understand-explore`.

### <a name="media-subdirectory"></a>Podkatalog plików multimedialnych

Każdy katalog artykułów zawiera podkatalog `/media` przeznaczony na odpowiednie pliki multimedialne. Pliki multimedialne zawierają obrazy używane przez artykuły z odwołaniami do obrazów.

### <a name="includes-subdirectory"></a>Podkatalog dołączania

Każda zawartość do wielokrotnego użytku udostępniana w co najmniej dwóch artykułach jest umieszczana w podkatalogu `/includes` katalogu poza głównym katalogiem `articles`. W pliku Markdown, w którym używany jest dołączony plik, odpowiednie rozszerzenie „include” języka znaczników Markdown jest umieszczane w lokalizacji, w której ma nastąpić odwołanie do tego pliku.

Dodatkowe wytyczne można znaleźć w części [Jak używać języka Markdown: operacje dołączania](how-to-write-use-markdown.md#includes).

### <a name="markdown-file-template"></a>Szablon pliku markdown

Dla wygody katalog główny każdego repozytorium zwykle zawiera plik szablonu Markdown o nazwie `template.md`. Z tego pliku szablonu można korzystać jak z „pliku startowego”, gdy konieczne jest utworzenie nowego artykułu do przesłania do repozytorium. Plik zawiera:

- **Nagłówek metadanych** u góry, który jest oddzielony dwiema liniami złożonymi z 3 łączników. Zawiera różne tagi używane do śledzenia informacji dotyczących konkretnego artykułu. Metadane artykułu dają dostęp do pewnych funkcji, takich jak przypisanie autora, przypisanie współautora, ścieżka nawigacyjna i opisy artykułu. Zawiera również optymalizacje SEO i procesy raportowania używane przez firmę Microsoft do oceny wydajności zawartości. Dlatego metadane są takie ważne.
- **Sekcję metadanych** opisującą różne tagi i wartości metadanych. Jeśli nie masz pewności co do wartości do użycia w sekcji metadanych, możesz pozostawić je puste lub dodać do nich komentarz z hasztagiem (#) na początku. Wartości te zostaną przejrzane/uzupełnione przez recenzenta żądania ściągnięcia w repozytorium.
- Różne **przykłady użycia języka znaczników Markdown** w celu formatowania elementów artykułu.
- Ogólne **instrukcje stosowania rozszerzeń języka znaczników Markdown**, których można używać w przypadku różnych typów alertów.
- Przykłady **osadzania wideo** przy użyciu elementu iframe.
- Ogólne **instrukcje stosowania rozszerzeń witryny docs.microsoft.com**, których można używać na potrzeby kontrolek specjalnych, takich jak przyciski i selektory.

## <a name="pull-requests"></a>Żądania ściągnięcia

*Żądanie ściągnięcia* oferuje współautorowi wygodny sposób proponowania zestawu zmian do zastosowania w gałęzi domyślnej. Te zmiany (znane również jako *zatwierdzenia*) są przechowywane w gałęzi współautora, dzięki czemu usługa GitHub może najpierw utworzyć model wpływu *scalania* ich z gałęzią domyślną. Żądanie ściągnięcia jest również mechanizmem przekazywania współautorowi opinii z procesu kompilacji/weryfikacji od recenzenta żądania ściągnięcia. Umożliwia to rozwiązywanie potencjalnych problemów i udzielanie odpowiedzi na ewentualne pytania przed scaleniem zmian z główną gałęzią.

Istnieją dwa sposoby dodawania swojego wkładu przez żądanie ściągnięcia — zależnie od rozmiaru zmian, które chce się zaproponować. Zostaną one omówione później, w sekcjach tego przewodnika dotyczących [przepływu pracy w usłudze GitHub](how-to-write-workflows-major.md).

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
