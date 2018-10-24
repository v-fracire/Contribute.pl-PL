---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084622"
---
# <a name="docs-pr-validation-service"></a><span data-ttu-id="c3532-101">Usługa walidacji żądania ściągnięcia dokumentów</span><span class="sxs-lookup"><span data-stu-id="c3532-101">Docs PR validation service</span></span>

<span data-ttu-id="c3532-102">Usługa walidacji żądania ściągnięcia dokumentów to aplikacja usługi GitHub, która uruchamia reguły walidacji dla plików w żądaniu ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="c3532-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="c3532-103">Włączenie usługi walidacji w repozytorium spowoduje następujące zachowanie:</span><span class="sxs-lookup"><span data-stu-id="c3532-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="c3532-104">Przesyłasz żądanie ściągnięcia.</span><span class="sxs-lookup"><span data-stu-id="c3532-104">You submit a PR.</span></span>
1. <span data-ttu-id="c3532-105">W komentarzu w usłudze GitHub wskazującym stan żądania ściągnięcia jest wyświetlany stan testów włączonych w repozytorium.</span><span class="sxs-lookup"><span data-stu-id="c3532-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="c3532-106">W tym przykładzie są włączone tylko dwa testy: „Zatwierdzanie walidacji” i „OpenPublishing.Build”:</span><span class="sxs-lookup"><span data-stu-id="c3532-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![niektóre testy nie powiodły się](media/validation-failed.png)

   <span data-ttu-id="c3532-108">Kompilacja może przebiec pomyślnie nawet wtedy, gdy zatwierdzenie walidacji się nie powiedzie.</span><span class="sxs-lookup"><span data-stu-id="c3532-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="c3532-109">Kliknij pozycję **Szczegóły**, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="c3532-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="c3532-110">Na stronie szczegółów są dostępne wszystkie testy walidacji zakończone niepowodzeniem wraz z informacjami o sposobie rozwiązania problemów:</span><span class="sxs-lookup"><span data-stu-id="c3532-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![komunikat walidacji](media/validation-details.png)

<span data-ttu-id="c3532-112">Listę walidacji dostępnych obecnie w usłudze można znaleźć w spisie treści tego artykułu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="c3532-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>