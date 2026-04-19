\# System automatyzacji obsługi reklamacji (AI)







\##  Opis projektu



Projekt przedstawia propozycję automatyzacji procesu obsługi reklamacji w firmie produkcyjnej Metalpol.



Obecny proces (AS-IS) jest w pełni manualny, oparty na pracy człowieka oraz wykorzystaniu Excela jako głównego narzędzia stare troche ;)

Brakuje integracji między systemami (SAP, JIRA), co prowadzi do opóźnień, błędów oraz braku skalowalności.



Celem projektu jest zaprojektowanie rozwiązania (TO-BE), które eliminuje manualne bottlenecki poprzez integrację systemów oraz selektywne wykorzystanie AI.











\##  Cele rozwiązania



\- Automatyzacja obsługi reklamacji

\- Eliminacja ręcznego wprowadzania danych

\- Integracja systemów (SAP, JIRA)

\- Skrócenie czasu odpowiedzi (z dni do minut)

\- Zapewnienie spójności klasyfikacji reklamacji

\- Umożliwienie raportowania i analizy danych



\-------------------------------------------------------------





\##  Zakres projektu



Projekt obejmuje:



\- analizę procesu AS-IS

\- zaprojektowanie procesu TO-BE

\- architekturę rozwiązania

\- wykorzystanie AI

\- analizę trade-offów

\- identyfikację edge cases



\-----------------------------------------------------------





\##  Struktura dokumentacji



\-  \[AS-IS Event Storming](docs/01-as-is-event-storming.md)

\-  \[TO-BE Event Storming](docs/02-to-be-event-storming.md)

\-  \[Architektura rozwiązania](docs/03-solution-architecture.md)

\-  \[Automatyzacja AI](docs/04-ai-automation.md)

\-  \[Trade-offy](docs/05-tradeoffs.md)

\-  \[Edge cases](docs/06-edge-cases.md)



\-----------------------------------------------------------







\##  Architektura rozwiązania (skrót)



System oparty jest o architekturę event-driven:



1\. Email przychodzi do systemu

2\. Backend rozpoczyna przetwarzanie (webhook)

3\. AI parsuje i klasyfikuje dane

4\. System pobiera dane z SAP

5\. Decision Engine podejmuje decyzję

6\. Tworzony jest ticket w JIRA

7\. Generowana jest odpowiedź do klienta



\--------------------------------------------------------------







\##  Wykorzystanie AI



AI wykorzystywane jest wyłącznie w obszarach:



\- parsowanie nieustrukturyzowanych danych (email)

\- klasyfikacja reklamacji



Nie jest używane do:

\- podejmowania decyzji biznesowych

\- walidacji danych



&#x20;zastosowano podejście hybrydowe (AI + reguły)



\---------------------------------------------------------------







\##  Kluczowe decyzje



\- architektura event-driven → skalowalność

\- serverless → elastyczność i koszt

\- AI tylko tam, gdzie potrzebne

\- decision engine → kontrola jakości



\-------------------------------------------------------------







\##  Obsługa wyjątków



System uwzględnia sytuacje takie jak:



\- brak danych (np. numeru zamówienia)

\- błędy AI (niski confidence)

\- niedostępność SAP

\- duplikaty zgłoszeń

\- spam



\---------------------------------------------------------------







\##  Wartość biznesowa



\- skrócenie czasu obsługi reklamacji

\- eliminacja pracy manualnej

\- zwiększenie skalowalności

\- poprawa jakości danych

\- dostęp do metryk i raportów



\-------------------------------------------------------------------





\##  Diagramy



\-  \[AS-IS Diagram](miro/as-is-diagram.pdf)

\-  \[TO-BE Diagram](miro/to-be-diagram.pdf)



\--------------------------------------------------------------







\##  Kluczowy wniosek



Największą wartością rozwiązania nie jest samo AI, lecz wprowadzenie spójnego, zautomatyzowanego pipelines danych oraz integracji systemów.

