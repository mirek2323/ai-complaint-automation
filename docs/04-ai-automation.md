\# Automatyzacja AI w procesie obsługi reklamacji



\##  Cel wykorzystania AI



Celem zastosowania AI w systemie jest automatyzacja tych elementów procesu, które operują na danych nieustrukturyzowanych i nie mogą być skutecznie obsłużone przez klasyczne reguły.



AI nie jest wykorzystywane jako główny mechanizm decyzyjny, lecz jako narzędzie wspierające.



\-------------------------------------------------------------





\##  Gdzie używamy AI



\### 1. Parsowanie maila



Problem:

\- email zawiera dane w formie nieustrukturyzowanej

\- różne języki, różne formaty



Rozwiązanie:

\- model AI wyciąga dane:

&#x20; - numer zamówienia

&#x20; - opis reklamacji

&#x20; - język

&#x20; - załączniki



\--------------------------------------------------------------------------





\### 2. Klasyfikacja reklamacji



AI przypisuje reklamację do kategorii:

\- wizualna

\- materiałowa

\- logistyczna



\--------------------------------------------------------------------------





\##  Gdzie NIE używamy AI



AI nie jest używane do:

\- walidacji danych

\- podejmowania decyzji biznesowych

\- integracji systemów



&#x20;Powód:

AI jest probabilistyczne i może popełniać błędy



\------------------------------------------------------------------------





\##  Podejście hybrydowe (AI + reguły)



System łączy AI z klasycznymi regułami biznesowymi.



Przykład:

\- AI klasyfikuje reklamację jako „materiałowa”

\- reguła wykrywa słowo „transport” → zmiana na „logistyczna”



\------------------------------------------------------------------------





\##  Decision Engine



Decision Engine wykorzystuje wynik AI (confidence score):



\- jeśli confidence > 80% → proces automatyczny

\- jeśli confidence < 80% → przekazanie do człowieka



\-------------------------------------------------------------------------





\##  Ryzyka



\- błędna klasyfikacja

\- brak danych wejściowych

\- zmiany w danych (model drift)



\------------------------------------------------------------------------





\##  Mitigacja



\- human-in-the-loop (człowiek w procesie)

\- monitoring wyników AI

\- możliwość korekty decyzji



\--------------------------------------------------------------------------





\##  Kluczowa zasada



AI wykorzystywane jest tylko tam, gdzie klasyczne podejście zawodzi.

