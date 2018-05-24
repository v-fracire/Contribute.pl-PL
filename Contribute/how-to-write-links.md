---
title: Jak używać linków w dokumentacji
description: Ten artykuł zawiera instrukcje dotyczące tworzenia linków do zawartości w witrynie docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/29/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1699e57ac6a4dc4c5a1ef099ea183b3cbc6307cd
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2018
---
# <a name="using-links-in-documentation"></a>Używanie linków w dokumentacji
W tym artykule opisano, jak używać hiperlinków na stronach hostowanych w witrynie docs.microsoft.com. Linki można łatwo dodawać do znaczników markdown za pomocą kilku różnych konwencji. Linki wskazują użytkownikom zawartość na tej samej stronie, na stronach sąsiednich lub wskazują zewnętrzne witryny i adresy URL.

Zaplecze witryny docs.microsoft.com korzysta z platformy Open Publishing Services (OPS), która implementuje język DocFX Flavored Markdown (DFM). Język DFM jest w wysokim stopniu zgodny z językiem GitHub Flavored Markdown (GFM), a ponadto dodaje dodatkowe funkcjonalności poprzez rozszerzenia języka Markdown.

> [!IMPORTANT]
> Wszystkie linki muszą być bezpieczne (`https` zamiast `http`), jeśli tylko element docelowy na to pozwala (a zdecydowana większość powinna).

## <a name="link-text"></a>Tekst linku

Wyrazy, które umieścisz w tekście linku, powinny być przyjazne. Innymi słowy powinny one być normalnymi wyrazami lub tytułem strony, do której prowadzi link.

> [!IMPORTANT]
> Nie używaj sformułowania „kliknij tutaj”. Nie jest ono dobre z punktu widzenia optymalizacji aparatu wyszukiwania, a ponadto nie opisuje odpowiednio miejsca docelowego.

**Poprawnie:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Niepoprawnie:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Linki z jednego artykułu do innego

Aby utworzyć link w treści artykułu technicznego witryny Docs do innego artykułu technicznego witryny Docs w tym samym zestawie dokumentów, użyj następującej składni linku:

- Artykuł w katalogu prowadzący do innego artykułu w tym samym katalogu:

  `[link text](article-name.md)`

- Artykuł prowadzący z podkatalogu do artykułu w katalogu głównym:

  `[link text](../article-name.md)`

- Artykuł w katalogu głównym prowadzący do artykułu w podkatalogu:

  `[link text](./directory/article-name.md)`

- Artykuł w podkatalogu prowadzący do artykułu w innym podkatalogu:

  `[link text](../directory/article-name.md)`

- Artykuł zawierający linki między zestawami dokumentów (nawet jeśli są tym samym repozytorium): `[link text](./directory/article-name)`
  
## <a name="links-to-anchors"></a>Linki do kotwic

Nie musisz tworzyć kotwic. Są one generowane automatycznie dla wszystkich nagłówków H2 w momencie publikacji. Musisz tylko utworzyć linki do sekcji H2.

- Aby utworzyć link do nagłówka w tym samym artykule:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Aby utworzyć link do kotwicy w innym artykule w tym samym podkatalogu:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Aby utworzyć link do kotwicy w podkatalogu innej usługi:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Linki z plików dołączania

Pliki dołączania znajdują się w innym katalogu, dlatego należy użyć dłuższych ścieżek względnych. Aby utworzyć link do artykułu z pliku dołączania, użyj następującego formatu:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>Linki w selektorach

Jeśli masz selektory, które są osadzone w pliku dołączania — tak jak zespół dokumentacji platformy Azure — użyj następującej struktury linku:

    > [AZURE.SELECTOR-LIST (Lista_rozwijana1 | Lista_rozwijana2 )]
    - [(Tekst1 | Przykład1 )](../articles/folder/article-name1.md)
    - [(Tekst1 | Przykład2 )](../articles/folder/article-name2.md)
    - [(Tekst2 | Przykład3 )](../articles/folder/article-name3.md)
    - [(Tekst2 | Przykład4 )](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Linki w stylu odwołania

Aby zawartość źródłowa była łatwiejsza do odczytania, możesz użyć linków w stylu odwołania. Linki w stylu odwołania zastępują składnię linków w tekście składnią uproszczoną, która umożliwia przeniesienie długich adresów URL na koniec artykułu. Oto przykład ze strony [Daring Fireball](https://daringfireball.net/projects/markdown/):

Tekst wbudowany:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Odwołania do linków na końcu artykułu:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Upewnij się, że po dwukropku (przed linkiem) znajduje się spacja. Jeśli zapomnisz o wstawieniu spacji, tworząc linki do innych artykułów technicznych, w opublikowanym artykule linki te będą uszkodzone.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Linki do stron, które nie należą do zestawu dokumentacji technicznej

Aby utworzyć link do strony w innej witrynie firmy Microsoft (na przykład do strony cennika, umowy SLA lub czegokolwiek innego, co nie jest artykułem dokumentacji), użyj bezwzględnego adresu URL, ale pomiń ustawienia regionalne. Należy tak zrobić, aby linki działały w usłudze GitHub i na renderowanej stronie:

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Linki do witryn innych firm

Aby środowisko użytkownika było jak najlepsze, należy zminimalizować odsyłanie do innych witryn. Z tego powodu linki do witryn innych firm, których czasami potrzebujemy, należy tworzyć, uwzględniając:

- **Odpowiedzialność**: utwórz link do zawartości innej firmy, jeśli informacje są informacjami udostępnianymi przez tę firmę. Na przykład nie jest zadaniem firmy Microsoft informowanie o tym, jak używać narzędzi deweloperskich dla systemu Android — należy to do firmy Google. W razie potrzeby możemy wyjaśnić, jak używać narzędzi deweloperskich systemu Android *za pomocą* platformy Azure, ale to firma Google powinna opowiedzieć o tym, jak korzystać z jej narzędzi.
- **Zatwierdzenie przez kierowników projektów**: zawartość innych firm powinna być zatwierdzana przez firmę Microsoft. Tworząc link do takiej zawartości, potwierdzamy niejako nasze zaufanie do niej oraz zobowiązanie, jeśli użytkownicy wykonają opisane instrukcje.
- **Sprawdzanie aktualności**: upewnij się, że informacje innej firmy są nadal aktualne, prawidłowe, odpowiednie, a link się nie zmienił.
- **Opuszczanie witryny**: uświadom użytkownikom, że przechodzą do innej witryny. Jeśli kontekst wyraźnie tego nie stwierdza, dodaj frazę objaśniającą. Na przykład: „Wymagania wstępne obejmują narzędzia deweloperskie dla systemu Android, które można pobrać z witryny Android Studio”.
- **Kolejne kroki**: w sekcji Kolejne kroki możesz dodać link na przykład do bloga MVP. Pamiętaj jednak, aby upewnić się, że użytkownicy wiedzą, że opuszczają witrynę.
- **Kwestie prawne**: odpowiednie informacje prawne znajdują się w sekcji **Linki do witryn innych firm** w stopce **Warunki użytkowania** na każdej stronie witryny ms.com.

## <a name="links-to-msdn-or-technet"></a>Linki do witryn MSDN i TechNet

Jeśli musisz utworzyć link do artykułu w witrynie MSDN lub TechNet, użyj pełnego linku do określonego tematu i usuń z niego językowe ustawienia regionalne „en-us”.

## <a name="links-to-azure-powershell-reference-content"></a>Linki do zawartości dokumentacji programu Azure PowerShell

Od listopada 2016 r. zawartość dokumentacji programu Azure PowerShell uległa pewnym zmianom. W przypadku tworzenia linków do tej zawartości z innych artykułów w witrynie docs.microsoft.com zastosuj poniższe wskazówki.

Struktura adresu URL:

* Dla poleceń cmdlet:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* Dla tematów pojęciowych:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

Część zawierająca &lt;krótką nazwę&gt; jest opcjonalna. Jeśli zostanie pominięta, nastąpi przekierowanie do najnowszej wersji zawartości. Część zawierająca &lt;nazwę usługi&gt; to jeden z przykładów pokazanych w następujących podstawowych adresach URL:

- Zawartość usługi Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/
- Zawartość usługi Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_
- Zawartość usługi Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active-directory_
- Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_
- Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_
- Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_

Jeśli użyjesz tych adresów URL, nastąpi przekierowanie do najnowszej wersji zawartości. Dzięki temu nie trzeba określać krótkiej nazwy (monikera) wersji. I nie będziesz mieć linków do zawartości koncepcyjnej, które muszą być aktualizowane po zmianie wersji.

Aby utworzyć prawidłowy link, znajdź w przeglądarce stronę, do której chcesz utworzyć ten link, i skopiuj adres URL.
Następnie usuń ciąg „https://docs.microsoft.com” i informacje o ustawieniach regionalnych.

Tworząc link ze spisu treści, musisz użyć pełnego adresu URL bez informacji o ustawieniach regionalnych.

Przykładowy kod języka Markdown:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
