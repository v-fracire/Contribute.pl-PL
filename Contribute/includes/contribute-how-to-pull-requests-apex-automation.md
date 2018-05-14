Automatyzacja komentarza umożliwia użytkownikom mającym poziom uprawnień do odczytu (użytkownikom, którzy nie mają uprawnień do zapisu w repozytorium) wykonanie akcji na poziomie uprawnień do zapisu dzięki przypisaniu odpowiedniej etykiety do żądania ściągnięcia. Jeśli pracujesz w repozytorium, w którym zaimplementowano automatyzację komentarza, użyj komentarzy z hasztagami wymienionych w poniższej tabeli, aby przypisać etykiety, etykiety zmiany lub zamknąć żądanie ściągnięcia. Pracownicy firmy Microsoft również zostaną powiadomieni pocztą e-mail o sprawdzeniu i zaakceptowaniu żądań ściągnięcia publicznego repozytorium zawsze, gdy dla artykułów Twojego autorstwa zostaną zaproponowane zmiany.


| Komentarz z hasztagiem | Jaką pełni funkcję | Dostępność repozytorium |
| --- | --- | --- |
| #sign-off |Gdy autor artykułu wpisze komentarz **#sign-off** w strumieniu komentarza, zostanie przypisana etykieta **gotowe do scalenia**. Ta etykieta umożliwia recenzentom w repozytorium dowiedzenie się, kiedy żądanie ściągnięcia jest gotowe do przeglądu/scalenia. |Publiczne i prywatne |
| #sign-off |Jeśli współautor, który *nie* jest wymienionym autorem, spróbuje zaakceptować publiczne żądanie ściągnięcia za pomocą komentarza **#sign-off**, zostanie napisany komunikat do żądania ściągnięcia wskazujący, że tylko autor może przypisać etykietę. |Publiczne |
| #hold-off |Autorzy mogą wpisać **#hold-off** w komentarzu do żądania ściągnięcia, aby usunąć etykietę **gotowe do scalenia** — w przypadku zmiany zdania lub popełnienia błędu. W prywatnym repozytorium powoduje to przypisanie etykiety **nie scalaj**. |Publiczne i prywatne |
| #please-close |Autorzy mogą wpisać **#please-close** w strumieniu komentarza, aby zamknąć żądanie ściągnięcia, jeśli postanowią nie scalać zmian. |Publiczne |
