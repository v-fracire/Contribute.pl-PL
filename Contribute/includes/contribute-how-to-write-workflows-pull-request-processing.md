## <a name="pull-request-processing"></a>Przetwarzanie żądania ściągnięcia

W poprzedniej sekcji omówiono proces przesyłania proponowanych zmian przez umieszczenie ich w pakiecie w nowym żądaniu ściągnięcia dodawanym do kolejki żądań ściągnięcia repozytorium docelowego. Żądanie ściągnięcia włącza model współpracy usługi GitHub przez zażądanie ściągnięcia zmian z gałęzi roboczej i scalenia ich z inną gałęzią. W większości przypadków ta inna gałąź to gałąź domyślna lub gałąź główna w repozytorium głównym.

### <a name="validation"></a>Weryfikacja

Zanim żądanie ściągnięcia będzie mogło zostać scalone z gałęzią docelową, może być konieczne jego przejście przez jeden lub więcej procesów weryfikowania żądań ściągnięcia. Procesy weryfikowania mogą się różnić zależnie od zakresu proponowanych zmian i reguły repozytorium docelowego. Po przesłaniu żądania ściągnięcia mogą zostać przeprowadzone następujące testy:

- **Możliwość scalania:** najpierw przeprowadzany jest test linii bazowej dotyczący możliwości scalania w usłudze GitHub w celu sprawdzenia, czy proponowane zmiany w gałęzi powodują konflikt z gałęzią docelową. Jeśli żądanie ściągnięcia nie przejdzie pomyślnie tego testu, będzie konieczne usunięcie zawartości powodującej konflikt scalania, aby można było kontynuować przetwarzanie.
- **Umowa licencyjna udziału:** jeśli współtworzysz zawartość w repozytorium publicznym i nie jesteś pracownikiem firmy Microsoft, przy pierwszej próbie przesłania żądania ściągnięcia do tego repozytorium może być konieczne wypełnienie krótkiej umowy licencyjnej udziału. Żądanie ściągnięcia zostanie przetworzone po wykonaniu kroku z umową licencyjną udziału.
- **Tworzenie etykiet:** do żądania ściągnięcia są automatycznie stosowane etykiety, które wskazują stan żądania przekazywanego w ramach przepływu pracy weryfikacji. Na przykład do nowych żądań ściągnięcia może być automatycznie stosowana etykieta wskazująca brak możliwości scalenia z powodu nieukończonego procesu weryfikacji, przeglądu i akceptacji.
- **Weryfikacja i kompilacja**: zautomatyzowane kontrole sprawdzają, czy zmiany przeszły testy weryfikacyjne. Testy weryfikacyjne mogą zwracać ostrzeżenia lub błędy, które wymagają wprowadzenia zmian w co najmniej jednym pliku w żądaniu ściągnięcia przed scaleniem. Wyniki testów weryfikacyjnych są dodawane do żądania ściągnięcia jako komentarz, który możesz przejrzeć, i mogą zostać wysłane pocztą e-mail.
- **Przygotowywanie:** strony artykułów, których dotyczą zmiany, mogą zostać automatycznie wdrożone w środowisku przygotowawczym na potrzeby przeglądu po pomyślnej weryfikacji i kompilacji. Adresy URL podglądu są udostępniane w komentarzu do żądania ściągnięcia.
- **Automatyczne scalanie:** żądanie ściągnięcia może zostać automatycznie scalone, jeśli pomyślnie przejdzie testy weryfikacyjne i spełni określone kryteria. W takim przypadku nie trzeba podejmować żadnych dalszych akcji.

### <a name="review-and-sign-off"></a>Przegląd i akceptacja

Po zakończeniu całego procesu przetwarzania żądania ściągnięcia przejrzyj wyniki (komentarze do żądania, adresy URL podglądu itp.), aby ustalić, czy przed jego zaakceptowaniem lub scaleniem należy wprowadzić dodatkowe zmiany w jego plikach. Jeśli żądanie ściągnięcia zostało przejrzane przez recenzenta, mógł on dodać komentarze z informacją o problemach do rozwiązania lub pytaniami wymagającymi odpowiedzi przed scaleniem.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Po rozwiązaniu problemów i zaakceptowaniu żądania ściągnięcia zmiany są scalane z powrotem z gałęzią nadrzędną, a żądanie ściągnięcia jest zamykane.

### <a name="publishing"></a>Publikowanie

Żądanie ściągnięcia musi zostać scalone przez recenzenta żądania, aby zmiany mogły zostać uwzględnione w następnym zaplanowanym przebiegu publikowania. Żądania ściągnięcia są zwykle przeglądane/scalane w takiej kolejności, w jakiej zostały przesłane. Jeśli żądanie ściągnięcia wymaga scalenia w ramach określonego przebiegu publikowania, skontaktuj się wcześniej z recenzentem żądania, aby upewnić się, że scalanie zostanie przeprowadzone przed publikowaniem.

Zatwierdzone i scalone zmiany są pobierane w ramach procesu publikowania w witrynie docs.microsoft.com. Czas publikowania różni się w zależności od zespołu zarządzającego repozytorium, w którym wprowadzasz zmiany. Artykuły opublikowane na poniższych stronach są zwykle wdrażane od poniedziałku do piątku ok. 10:30 i 15:30 czasu pacyficznego:

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

Artykuły mogą zostać wyświetlone online do 45 minut po opublikowaniu. Po opublikowaniu artykułu możesz sprawdzić zmiany, używając odpowiedniego adresu URL: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
