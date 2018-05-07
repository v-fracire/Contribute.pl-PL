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
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="070a8-103">Używanie linków w dokumentacji</span><span class="sxs-lookup"><span data-stu-id="070a8-103">Using links in documentation</span></span>
<span data-ttu-id="070a8-104">W tym artykule opisano, jak używać hiperlinków na stronach hostowanych w witrynie docs.microsoft.com. Linki można łatwo dodawać do znaczników markdown za pomocą kilku różnych konwencji.</span><span class="sxs-lookup"><span data-stu-id="070a8-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com. Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="070a8-105">Linki wskazują użytkownikom zawartość na tej samej stronie, na stronach sąsiednich lub wskazują zewnętrzne witryny i adresy URL.</span><span class="sxs-lookup"><span data-stu-id="070a8-105">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="070a8-106">Zaplecze witryny docs.microsoft.com korzysta z platformy Open Publishing Services (OPS), która implementuje język DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="070a8-106">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="070a8-107">Język DFM jest w wysokim stopniu zgodny z językiem GitHub Flavored Markdown (GFM), a ponadto dodaje dodatkowe funkcjonalności poprzez rozszerzenia języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="070a8-107">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="070a8-108">Wszystkie linki muszą być bezpieczne (`https` zamiast `http`), jeśli tylko element docelowy na to pozwala (a zdecydowana większość powinna).</span><span class="sxs-lookup"><span data-stu-id="070a8-108">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="070a8-109">Tekst linku</span><span class="sxs-lookup"><span data-stu-id="070a8-109">Link text</span></span>

<span data-ttu-id="070a8-110">Wyrazy, które umieścisz w tekście linku, powinny być przyjazne.</span><span class="sxs-lookup"><span data-stu-id="070a8-110">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="070a8-111">Innymi słowy powinny one być normalnymi wyrazami lub tytułem strony, do której prowadzi link.</span><span class="sxs-lookup"><span data-stu-id="070a8-111">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="070a8-112">Nie używaj sformułowania „kliknij tutaj”.</span><span class="sxs-lookup"><span data-stu-id="070a8-112">Do not use "click here."</span></span> <span data-ttu-id="070a8-113">Nie jest ono dobre z punktu widzenia optymalizacji aparatu wyszukiwania, a ponadto nie opisuje odpowiednio miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="070a8-113">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="070a8-114">**Poprawnie:**</span><span class="sxs-lookup"><span data-stu-id="070a8-114">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="070a8-115">**Niepoprawnie:**</span><span class="sxs-lookup"><span data-stu-id="070a8-115">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="070a8-116">Linki z jednego artykułu do innego</span><span class="sxs-lookup"><span data-stu-id="070a8-116">Links from one article to another</span></span>

<span data-ttu-id="070a8-117">Aby utworzyć link w treści artykułu technicznego witryny Docs do innego artykułu technicznego witryny Docs w tym samym zestawie dokumentów, użyj następującej składni linku:</span><span class="sxs-lookup"><span data-stu-id="070a8-117">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="070a8-118">Artykuł w katalogu prowadzący do innego artykułu w tym samym katalogu:</span><span class="sxs-lookup"><span data-stu-id="070a8-118">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="070a8-119">Artykuł prowadzący z podkatalogu do artykułu w katalogu głównym:</span><span class="sxs-lookup"><span data-stu-id="070a8-119">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="070a8-120">Artykuł w katalogu głównym prowadzący do artykułu w podkatalogu:</span><span class="sxs-lookup"><span data-stu-id="070a8-120">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="070a8-121">Artykuł w podkatalogu prowadzący do artykułu w innym podkatalogu:</span><span class="sxs-lookup"><span data-stu-id="070a8-121">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="070a8-122">Artykuł zawierający linki między zestawami dokumentów (nawet jeśli są tym samym repozytorium): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="070a8-122">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>
  
## <a name="links-to-anchors"></a><span data-ttu-id="070a8-123">Linki do kotwic</span><span class="sxs-lookup"><span data-stu-id="070a8-123">Links to anchors</span></span>

<span data-ttu-id="070a8-124">Nie musisz tworzyć kotwic.</span><span class="sxs-lookup"><span data-stu-id="070a8-124">You do not have to create anchors.</span></span> <span data-ttu-id="070a8-125">Są one generowane automatycznie dla wszystkich nagłówków H2 w momencie publikacji.</span><span class="sxs-lookup"><span data-stu-id="070a8-125">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="070a8-126">Musisz tylko utworzyć linki do sekcji H2.</span><span class="sxs-lookup"><span data-stu-id="070a8-126">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="070a8-127">Aby utworzyć link do nagłówka w tym samym artykule:</span><span class="sxs-lookup"><span data-stu-id="070a8-127">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="070a8-128">Aby utworzyć link do kotwicy w innym artykule w tym samym podkatalogu:</span><span class="sxs-lookup"><span data-stu-id="070a8-128">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="070a8-129">Aby utworzyć link do kotwicy w podkatalogu innej usługi:</span><span class="sxs-lookup"><span data-stu-id="070a8-129">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="070a8-130">Linki z plików dołączania</span><span class="sxs-lookup"><span data-stu-id="070a8-130">Links from includes</span></span>

<span data-ttu-id="070a8-131">Pliki dołączania znajdują się w innym katalogu, dlatego należy użyć dłuższych ścieżek względnych.</span><span class="sxs-lookup"><span data-stu-id="070a8-131">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="070a8-132">Aby utworzyć link do artykułu z pliku dołączania, użyj następującego formatu:</span><span class="sxs-lookup"><span data-stu-id="070a8-132">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="070a8-133">Linki w selektorach</span><span class="sxs-lookup"><span data-stu-id="070a8-133">Links in selectors</span></span>

<span data-ttu-id="070a8-134">Jeśli masz selektory, które są osadzone w pliku dołączania — tak jak zespół dokumentacji platformy Azure — użyj następującej struktury linku:</span><span class="sxs-lookup"><span data-stu-id="070a8-134">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="070a8-135">[AZURE.SELECTOR-LIST (Lista_rozwijana1 | Lista_rozwijana2 )]</span><span class="sxs-lookup"><span data-stu-id="070a8-135">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="070a8-136">(Tekst1 | Przykład1 )</span><span class="sxs-lookup"><span data-stu-id="070a8-136">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="070a8-137">(Tekst1 | Przykład2 )</span><span class="sxs-lookup"><span data-stu-id="070a8-137">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="070a8-138">(Tekst2 | Przykład3 )</span><span class="sxs-lookup"><span data-stu-id="070a8-138">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="070a8-139">[(Tekst2 | Przykład4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="070a8-139">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="070a8-140">Linki w stylu odwołania</span><span class="sxs-lookup"><span data-stu-id="070a8-140">Reference-style links</span></span>

<span data-ttu-id="070a8-141">Aby zawartość źródłowa była łatwiejsza do odczytania, możesz użyć linków w stylu odwołania.</span><span class="sxs-lookup"><span data-stu-id="070a8-141">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="070a8-142">Linki w stylu odwołania zastępują składnię linków w tekście składnią uproszczoną, która umożliwia przeniesienie długich adresów URL na koniec artykułu.</span><span class="sxs-lookup"><span data-stu-id="070a8-142">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="070a8-143">Oto przykład ze strony [Daring Fireball](https://daringfireball.net/projects/markdown/):</span><span class="sxs-lookup"><span data-stu-id="070a8-143">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="070a8-144">Tekst wbudowany:</span><span class="sxs-lookup"><span data-stu-id="070a8-144">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="070a8-145">Odwołania do linków na końcu artykułu:</span><span class="sxs-lookup"><span data-stu-id="070a8-145">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="070a8-146">Upewnij się, że po dwukropku (przed linkiem) znajduje się spacja.</span><span class="sxs-lookup"><span data-stu-id="070a8-146">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="070a8-147">Jeśli zapomnisz o wstawieniu spacji, tworząc linki do innych artykułów technicznych, w opublikowanym artykule linki te będą uszkodzone.</span><span class="sxs-lookup"><span data-stu-id="070a8-147">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="070a8-148">Linki do stron, które nie należą do zestawu dokumentacji technicznej</span><span class="sxs-lookup"><span data-stu-id="070a8-148">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="070a8-149">Aby utworzyć link do strony w innej witrynie firmy Microsoft (na przykład do strony cennika, umowy SLA lub czegokolwiek innego, co nie jest artykułem dokumentacji), użyj bezwzględnego adresu URL, ale pomiń ustawienia regionalne.</span><span class="sxs-lookup"><span data-stu-id="070a8-149">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="070a8-150">Należy tak zrobić, aby linki działały w usłudze GitHub i na renderowanej stronie:</span><span class="sxs-lookup"><span data-stu-id="070a8-150">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="070a8-151">Linki do witryn innych firm</span><span class="sxs-lookup"><span data-stu-id="070a8-151">Links to third-party sites</span></span>

<span data-ttu-id="070a8-152">Aby środowisko użytkownika było jak najlepsze, należy zminimalizować odsyłanie do innych witryn.</span><span class="sxs-lookup"><span data-stu-id="070a8-152">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="070a8-153">Z tego powodu linki do witryn innych firm, których czasami potrzebujemy, należy tworzyć, uwzględniając:</span><span class="sxs-lookup"><span data-stu-id="070a8-153">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="070a8-154">**Odpowiedzialność**: utwórz link do zawartości innej firmy, jeśli informacje są informacjami udostępnianymi przez tę firmę.</span><span class="sxs-lookup"><span data-stu-id="070a8-154">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="070a8-155">Na przykład nie jest zadaniem firmy Microsoft informowanie o tym, jak używać narzędzi deweloperskich dla systemu Android — należy to do firmy Google.</span><span class="sxs-lookup"><span data-stu-id="070a8-155">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="070a8-156">W razie potrzeby możemy wyjaśnić, jak używać narzędzi deweloperskich systemu Android *za pomocą* platformy Azure, ale to firma Google powinna opowiedzieć o tym, jak korzystać z jej narzędzi.</span><span class="sxs-lookup"><span data-stu-id="070a8-156">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="070a8-157">**Zatwierdzenie przez kierowników projektów**: zawartość innych firm powinna być zatwierdzana przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="070a8-157">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="070a8-158">Tworząc link do takiej zawartości, potwierdzamy niejako nasze zaufanie do niej oraz zobowiązanie, jeśli użytkownicy wykonają opisane instrukcje.</span><span class="sxs-lookup"><span data-stu-id="070a8-158">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="070a8-159">**Sprawdzanie aktualności**: upewnij się, że informacje innej firmy są nadal aktualne, prawidłowe, odpowiednie, a link się nie zmienił.</span><span class="sxs-lookup"><span data-stu-id="070a8-159">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="070a8-160">**Opuszczanie witryny**: uświadom użytkownikom, że przechodzą do innej witryny.</span><span class="sxs-lookup"><span data-stu-id="070a8-160">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="070a8-161">Jeśli kontekst wyraźnie tego nie stwierdza, dodaj frazę objaśniającą.</span><span class="sxs-lookup"><span data-stu-id="070a8-161">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="070a8-162">Na przykład: „Wymagania wstępne obejmują narzędzia deweloperskie dla systemu Android, które można pobrać z witryny Android Studio”.</span><span class="sxs-lookup"><span data-stu-id="070a8-162">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="070a8-163">**Kolejne kroki**: w sekcji Kolejne kroki możesz dodać link na przykład do bloga MVP.</span><span class="sxs-lookup"><span data-stu-id="070a8-163">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="070a8-164">Pamiętaj jednak, aby upewnić się, że użytkownicy wiedzą, że opuszczają witrynę.</span><span class="sxs-lookup"><span data-stu-id="070a8-164">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="070a8-165">**Kwestie prawne**: odpowiednie informacje prawne znajdują się w sekcji **Linki do witryn innych firm** w stopce **Warunki użytkowania** na każdej stronie witryny ms.com.</span><span class="sxs-lookup"><span data-stu-id="070a8-165">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="070a8-166">Linki do witryn MSDN i TechNet</span><span class="sxs-lookup"><span data-stu-id="070a8-166">Links to MSDN or TechNet</span></span>

<span data-ttu-id="070a8-167">Jeśli musisz utworzyć link do artykułu w witrynie MSDN lub TechNet, użyj pełnego linku do określonego tematu i usuń z niego językowe ustawienia regionalne „en-us”.</span><span class="sxs-lookup"><span data-stu-id="070a8-167">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="070a8-168">Linki do zawartości dokumentacji programu Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="070a8-168">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="070a8-169">Od listopada 2016 r. zawartość dokumentacji programu Azure PowerShell uległa pewnym zmianom.</span><span class="sxs-lookup"><span data-stu-id="070a8-169">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="070a8-170">W przypadku tworzenia linków do tej zawartości z innych artykułów w witrynie docs.microsoft.com zastosuj poniższe wskazówki.</span><span class="sxs-lookup"><span data-stu-id="070a8-170">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="070a8-171">Struktura adresu URL:</span><span class="sxs-lookup"><span data-stu-id="070a8-171">Structure of the URL:</span></span>

* <span data-ttu-id="070a8-172">Dla poleceń cmdlet:</span><span class="sxs-lookup"><span data-stu-id="070a8-172">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="070a8-173">Dla tematów pojęciowych:</span><span class="sxs-lookup"><span data-stu-id="070a8-173">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="070a8-174">Część zawierająca &lt;krótką nazwę&gt; jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="070a8-174">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="070a8-175">Jeśli zostanie pominięta, nastąpi przekierowanie do najnowszej wersji zawartości.</span><span class="sxs-lookup"><span data-stu-id="070a8-175">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="070a8-176">Część zawierająca &lt;nazwę usługi&gt; to jeden z przykładów pokazanych w następujących podstawowych adresach URL:</span><span class="sxs-lookup"><span data-stu-id="070a8-176">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="070a8-177">Zawartość usługi Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/</span><span class="sxs-lookup"><span data-stu-id="070a8-177">Azure PowerShell (AzureRM) content: https://docs.microsoft.com/powershell/azure/</span></span>
- <span data-ttu-id="070a8-178">Zawartość usługi Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_</span><span class="sxs-lookup"><span data-stu-id="070a8-178">Azure PowerShell (ASM) content: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span></span>
- <span data-ttu-id="070a8-179">Zawartość usługi Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active-directory_</span><span class="sxs-lookup"><span data-stu-id="070a8-179">Azure Active Directory (AzureAD) PowerShell content: https://docs.microsoft.com/powershell/azure/_active-directory_</span></span>
- <span data-ttu-id="070a8-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span><span class="sxs-lookup"><span data-stu-id="070a8-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span></span>
- <span data-ttu-id="070a8-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span><span class="sxs-lookup"><span data-stu-id="070a8-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span></span>
- <span data-ttu-id="070a8-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span><span class="sxs-lookup"><span data-stu-id="070a8-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span></span>

<span data-ttu-id="070a8-183">Jeśli użyjesz tych adresów URL, nastąpi przekierowanie do najnowszej wersji zawartości.</span><span class="sxs-lookup"><span data-stu-id="070a8-183">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="070a8-184">Dzięki temu nie trzeba określać krótkiej nazwy (monikera) wersji.</span><span class="sxs-lookup"><span data-stu-id="070a8-184">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="070a8-185">I nie będziesz mieć linków do zawartości koncepcyjnej, które muszą być aktualizowane po zmianie wersji.</span><span class="sxs-lookup"><span data-stu-id="070a8-185">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="070a8-186">Aby utworzyć prawidłowy link, znajdź w przeglądarce stronę, do której chcesz utworzyć ten link, i skopiuj adres URL.</span><span class="sxs-lookup"><span data-stu-id="070a8-186">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="070a8-187">Następnie usuń ciąg „https://docs.microsoft.com” i informacje o ustawieniach regionalnych.</span><span class="sxs-lookup"><span data-stu-id="070a8-187">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="070a8-188">Tworząc link ze spisu treści, musisz użyć pełnego adresu URL bez informacji o ustawieniach regionalnych.</span><span class="sxs-lookup"><span data-stu-id="070a8-188">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="070a8-189">Przykładowy kod języka Markdown:</span><span class="sxs-lookup"><span data-stu-id="070a8-189">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
