\# TO-BE Event Storming – Docelowy proces obsługi reklamacji



&#x20;Opis ogólny



Docelowy proces obsługi reklamacji zakłada automatyzację oraz integrację systemów (Email, AI, SAP, JIRA).



Proces oparty jest o architekturę event-driven, w której system przejmuje większość działań, a człowiek wchodzi tylko w przypadku niepewności decyzji.







&#x20;Eventy (co się wydarza)



\- Email odebrany

\- Dane wyciągnięte z maila

\- Reklamacja sklasyfikowana (AI)

\- Dane z SAP pobrane

\- Reklamacja zwalidowana

\- Ticket JIRA utworzony

\- Odpowiedź wygenerowana

\- Odpowiedź wysłana







\##  Komendy (co wywołuje akcję)



\- Parsuj email

\- Wyciągnij dane

\- Skategoryzuj reklamację

\- Pobierz dane z SAP

\- Zwaliduj reklamację

\- Utwórz ticket w JIRA

\- Wygeneruj odpowiedź

\- Wyślij odpowiedź







&#x20;Aktorzy



\- System – zarządza przepływem procesu

\- AI Service – odpowiada za parsing i klasyfikację

\- SAP API – dostarcza dane produkcyjne

\- JIRA API – tworzy i zarządza ticketami







&#x20;Kluczowy element – Decision Engine



Decision Engine decyduje o dalszym przebiegu procesu na podstawie poziomu pewności (confidence score) modelu AI.



\- jeśli confidence > 80% → proces przebiega automatycznie

\- jeśli confidence < 80% → przypadek trafia do człowieka







&#x20;Ulepszenia względem AS-IS



\- Automatyzacja procesu (brak ręcznego wprowadzania danych)

\- Integracja systemów (SAP, JIRA)

\- Spójna klasyfikacja reklamacji (AI)

\- Skrócenie czasu odpowiedzi (z dni do minut)

\- Eliminacja bottlenecków

\- Możliwość zbierania danych i metryk







\--------    Wniosek  --------



Proces jest zautomatyzowany, skalowalny i oparty o integracje systemowe. AI wspiera tylko te elementy, które wymagają analizy danych nieustrukturyzowanych.

