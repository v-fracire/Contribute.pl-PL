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
# <a name="markdown-headings"></a>Nagłówki języka Markdown

Poniżej przedstawiono wymagania walidacji dotyczące nagłówków w plikach Markdown platformy OPS.

## <a name="h1"></a>H1

Element `H1` oznacza pierwszy nagłówek w pliku Markdown. Po opublikowaniu zawartości w witrynie docs.microsoft.com nagłówek H1 jest wyświetlany przy użyciu dużej czcionki u góry strony.

Aby utworzyć nagłówek H1, na początku wiersza wpisz jeden znak kratki (`#`), odstęp i tekst nagłówka. Na przykład ten artykuł ma następujący nagłówek H1:

```md
# Markdown headings
```

Nagłówków H1 dotyczą następujące reguły:

- Plik musi zawierać nagłówek H1.
- Może istnieć tylko jeden nagłówek H1.
- Nagłówek H1 musi mieć zawartość.

  ```markdown
  # 
  This is not allowed.
  ```
- Między znakiem `#` i zawartością nagłówka H1 musi być odstęp. Nagłówek H1 bez odstępu nie jest renderowany na opublikowanej stronie jako nagłówek.

  ```markdown
  #This looks bad on the site.
  ```
- Nagłówek H1 musi być pierwszym elementem w pliku po nagłówku metadanych YML. Między końcem nagłówka YML i nagłówkiem H1 nie może być żadnej zawartości, takiej jak tekst lub obrazy.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- Nie należy używać elementu HTML nagłówków pierwszego poziomu (`<h1>`). Należy używać składni języka Markdown (`# `).
- Nagłówek H1 nie może być dłuższy niż 100 znaków. To są wytyczne dotyczące stylu.

## <a name="h2---h6"></a>H2–H6

Na platformie OPS są dozwolone nagłówki od H2 (`## `) do H6 (`###### `). Nagłówki należy tworzyć przy użyciu nagłówków języka Markdown, a nie języka HTML (`<h2>` - `<h6>`).
