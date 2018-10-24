---
title: Nagłówki języka Markdown
description: W tym artykule opisano nagłówki języka Markdown.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084560"
---
# <a name="markdown-headings"></a><span data-ttu-id="6c2cb-103">Nagłówki języka Markdown</span><span class="sxs-lookup"><span data-stu-id="6c2cb-103">Markdown headings</span></span>

<span data-ttu-id="6c2cb-104">Poniżej przedstawiono wymagania walidacji dotyczące nagłówków w plikach Markdown platformy OPS.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="6c2cb-105">H1</span><span class="sxs-lookup"><span data-stu-id="6c2cb-105">H1</span></span>

<span data-ttu-id="6c2cb-106">Element `H1` oznacza pierwszy nagłówek w pliku Markdown.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="6c2cb-107">Po opublikowaniu zawartości w witrynie docs.microsoft.com nagłówek H1 jest wyświetlany przy użyciu dużej czcionki u góry strony.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="6c2cb-108">Aby utworzyć nagłówek H1, na początku wiersza wpisz jeden znak kratki (`#`), odstęp i tekst nagłówka.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="6c2cb-109">Na przykład ten artykuł ma następujący nagłówek H1:</span><span class="sxs-lookup"><span data-stu-id="6c2cb-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="6c2cb-110">Nagłówków H1 dotyczą następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="6c2cb-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="6c2cb-111">Plik musi zawierać nagłówek H1.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="6c2cb-112">Może istnieć tylko jeden nagłówek H1.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-112">There can only be one H1.</span></span>
- <span data-ttu-id="6c2cb-113">Nagłówek H1 musi mieć zawartość.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="6c2cb-114">Między znakiem `#` i zawartością nagłówka H1 musi być odstęp.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="6c2cb-115">Nagłówek H1 bez odstępu nie jest renderowany na opublikowanej stronie jako nagłówek.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="6c2cb-116">Nagłówek H1 musi być pierwszym elementem w pliku po nagłówku metadanych YML.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="6c2cb-117">Między końcem nagłówka YML i nagłówkiem H1 nie może być żadnej zawartości, takiej jak tekst lub obrazy.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="6c2cb-118">Nie należy używać elementu HTML nagłówków pierwszego poziomu (`<h1>`).</span><span class="sxs-lookup"><span data-stu-id="6c2cb-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="6c2cb-119">Należy używać składni języka Markdown (`# `).</span><span class="sxs-lookup"><span data-stu-id="6c2cb-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="6c2cb-120">Nagłówek H1 nie może być dłuższy niż 100 znaków.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="6c2cb-121">To są wytyczne dotyczące stylu.</span><span class="sxs-lookup"><span data-stu-id="6c2cb-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="6c2cb-122">H2–H6</span><span class="sxs-lookup"><span data-stu-id="6c2cb-122">H2 - H6</span></span>

<span data-ttu-id="6c2cb-123">Na platformie OPS są dozwolone nagłówki od H2 (`## `) do H6 (`###### `).</span><span class="sxs-lookup"><span data-stu-id="6c2cb-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="6c2cb-124">Nagłówki należy tworzyć przy użyciu nagłówków języka Markdown, a nie języka HTML (`<h2>` - `<h6>`).</span><span class="sxs-lookup"><span data-stu-id="6c2cb-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
