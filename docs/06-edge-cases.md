&#x20;                       Edge Cases – scenariusze wyjątkowe

&#x20;



\-------------        Wprowadzenie     ------------





System musi obsługiwać nie tylko standardowy przepływ, ale również sytuacje wyjątkowe, które mogą wystąpić w rzeczywistym środowisku.



Poniżej przedstawiono kluczowe edge cases oraz sposób ich obsługi.



\---------------------------------------------------







\##  Brak numeru zamówienia



Problem:

\- brak możliwości identyfikacji reklamacji w SAP



Rozwiązanie:

\- oznaczenie zgłoszenia jako "incomplete"

\- przekazanie do manualnej obsługi



\----------------------------------------------------------------------







\##  Niska pewność klasyfikacji (AI)



Problem:

\- model AI nie jest pewny wyniku



Rozwiązanie:

\- jeśli confidence < 80% → przekazanie do człowieka

\- zapis przypadku do dalszej analizy



\-----------------------------------------------------------------------





\##  SAP niedostępny



Problem:

\- brak możliwości pobrania danych produkcyjnych



Rozwiązanie:

\- zastosowanie retry mechanizmu

\- użycie kolejki (queue) do ponownego przetwarzania



\-------------------------------------------------------------------------







\##  Duplikaty zgłoszeń



Problem:

\- klient wysyła kilka razy ten sam email



Rozwiązanie:

\- identyfikacja poprzez hash treści

\- deduplikacja zgłoszeń



\-------------------------------------------------------------------------







\##  Spam / niepoprawne zgłoszenia



Problem:

\- część email nie dotyczy reklamacji



Rozwiązanie:

\- filtracja (AI + reguły)

\- odrzucenie lub oznaczenie jako spam



\--------------------------------------------------------------------------







\##  Brak załączników (np. zdjęć)



Problem:

\- brak materiału do analizy reklamacji



Rozwiązanie:

\- oznaczenie jako niekompletne

\- prośba o uzupełnienie danych



\---------------------------------------------------------------------







\## Błędne dane wejściowe



Problem:

\- niepoprawny numer zamówienia lub dane



Rozwiązanie:

\- walidacja danych

\- fallback do manualnej obsługi



\----------------------------------------------------------------------









\-------------   Wniosek  --------------



Uwzględnienie edge cases pozwala na zwiększenie stabilności systemu oraz przygotowanie go na rzeczywiste warunki operacyjne.

