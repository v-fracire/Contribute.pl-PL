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
# <a name="docs-pr-validation-service"></a>Usługa walidacji żądania ściągnięcia dokumentów

Usługa walidacji żądania ściągnięcia dokumentów to aplikacja usługi GitHub, która uruchamia reguły walidacji dla plików w żądaniu ściągnięcia.

Włączenie usługi walidacji w repozytorium spowoduje następujące zachowanie:

1. Przesyłasz żądanie ściągnięcia.
1. W komentarzu w usłudze GitHub wskazującym stan żądania ściągnięcia jest wyświetlany stan testów włączonych w repozytorium. W tym przykładzie są włączone tylko dwa testy: „Zatwierdzanie walidacji” i „OpenPublishing.Build”:

   ![niektóre testy nie powiodły się](media/validation-failed.png)

   Kompilacja może przebiec pomyślnie nawet wtedy, gdy zatwierdzenie walidacji się nie powiedzie.

1. Kliknij pozycję **Szczegóły**, aby uzyskać więcej informacji.
1. Na stronie szczegółów są dostępne wszystkie testy walidacji zakończone niepowodzeniem wraz z informacjami o sposobie rozwiązania problemów:

   ![komunikat walidacji](media/validation-details.png)

Listę walidacji dostępnych obecnie w usłudze można znaleźć w spisie treści tego artykułu po lewej stronie.