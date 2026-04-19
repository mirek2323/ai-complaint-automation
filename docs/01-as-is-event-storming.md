\# AS-IS Event Storming – Obecny proces obsługi reklamacji



\##  Opis ogólny



Obecny proces obsługi reklamacji w firmie jest w pełni manualny i opiera się głównie na pracy człowieka oraz wykorzystaniu Excela jako głównego narzędzia.



Brakuje integracji pomiędzy systemami (SAP, JIRA), co powoduje opóźnienia, błędy oraz brak skalowalności.



\---



\##  Eventy (co się wydarza)



\- Email otrzymany od klienta

\- Dane ręcznie wprowadzone do Excela

\- Reklamacja sklasyfikowana (subiektywna decyzja człowieka)

\- SAP sprawdzony ręcznie

\- Ticket JIRA utworzony

\- Odpowiedź wysłana do klienta

\- Ticket korekty utworzony



\---



\##  Komendy (co wywołuje akcję)



\- Odbierz email

\- Wprowadź dane do Excela

\- Skategoryzuj reklamację

\- Sprawdź SAP

\- Utwórz ticket w JIRA

\- Wyślij odpowiedź

\- Utwórz korektę



\---



\##  Aktorzy



\- Klient – wysyła zgłoszenie reklamacyjne

\- Specjalista serwisowy – ręcznie obsługuje cały proces



\---



\##  Problemy w obecnym procesie



\- Praca ręczna (wąskie gardło)

\- Brak integracji systemów (SAP, JIRA)

\- Excel jako główne narzędzie operacyjne

\- Niespójna kategoryzacja reklamacji (subiektywna)

\- Brak metryk i raportowania dla CEO

\- Opóźnienia w obsłudze (średnio \~2 dni)

\- Część emaili trafia do spamu lub jest przetwarzana z opóźnieniem



\---



\##  Wniosek



Proces nie jest wspierany przez spójny system informatyczny, lecz opiera się na manualnym workflow, co ogranicza jego skalowalność, wydajność oraz jakość danych.

