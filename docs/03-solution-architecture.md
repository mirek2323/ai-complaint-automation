\# Architektura rozwiązania – Automatyzacja obsługi reklamacji





&#x20;Cel systemu





Celem systemu jest automatyzacja procesu obsługi reklamacji poprzez eliminację pracy manualnej, integrację systemów oraz selektywne wykorzystanie sztucznej inteligencji.







\## Główny przepływ procesu (flow)



1\. Klient wysyła email z reklamacją

2\. System odbiera email poprzez Microsoft Graph API (webhook)

3\. Backend (.NET / Azure Functions) rozpoczyna przetwarzanie

4\. Email trafia do modułu AI (parsowanie)

5\. System wyciąga dane:

&#x20;  - numer zamówienia

&#x20;  - opis reklamacji

&#x20;  - język

&#x20;  - załączniki (np. zdjęcia)

6\. AI klasyfikuje reklamację (np. wizualna, materiał, logistyka)

7\. System pobiera dane z SAP:

&#x20;  - batch

&#x20;  - operator

&#x20;  - dane produkcyjne

8\. Decision Engine analizuje przypadek:

&#x20;  - confidence > 80% → automatyczna obsługa

&#x20;  - confidence < 80% → przekazanie do człowieka

9\. System tworzy ticket w JIRA

10\. Generowana jest odpowiedź do klienta (AI + template)

11\. Odpowiedź zostaje wysłana

12\. Dane zapisywane są w bazie (logi, metryki)









\## Komponenty systemu



\### 1. Email Ingestion – Microsoft Graph API

\- webhook reagujący na nowe maile

\- przetwarzanie w czasie rzeczywistym



&#x20;Dlaczego:

\- brak opóźnień

\- eliminacja polling



\-----------------------------------------------------------------------------------------------------





\### 2. Backend – .NET / Azure Functions



\- centralna logika systemu

\- orkiestracja procesu



&#x20;Dlaczego:

\- serverless = skalowalność

\- dobra integracja z systemami enterprise



\------------------------------------------------------------------------------------------------------





\### 3. Moduł AI – Azure OpenAI



\#### Funkcje:

\- parsowanie maila (extract danych)

\- klasyfikacja reklamacji



&#x20;Dlaczego:

\- dane nieustrukturyzowane

\- różne języki i formaty



&#x20;Alternatywa:

\- regex → nie skalowalne



\-----------------------------------------------------------------------------------------------------





\### 4. Decision Engine



\#### Logika:

\- jeśli confidence > 80% → automatyczne przetwarzanie

\- jeśli < 80% → człowiek





&#x20;Dlaczego:

\- AI nie jest w 100% dokładne

\- potrzebna kontrola jakości



\-----------------------------------------------------------------------------------------------------







\### 5. Integracja SAP



\- REST API do pobierania danych produkcyjnych



&#x20;Dlaczego:

\- większość decyzji opiera się na danych z SAP





\----------------------------------------------------------------------------------------------





\### 6. Integracja JIRA



\- automatyczne tworzenie ticketów



&#x20;Dlaczego:

\- eliminacja ręcznej pracy



\------------------------------------------------------------------------------------------------





\### 7. Response Generator



\- generowanie odpowiedzi do klienta (AI + template)



&#x20;Dlaczego:

\- skrócenie czasu odpowiedzi



\-----------------------------------------------------------------------------------------





\### 8. Storage



\#### PostgreSQL:

\- logi

\- statusy

\- metryki



\#### Azure Blob Storage:

\- zdjęcia i załączniki



&#x20;Dlaczego:

\- separacja danych



\----------------------------------------------------------------------------------------------







\-----     Kluczowa decyzja architektoniczna   ---------------



System nie jest systemem AI, lecz systemem integracyjnym wspieranym przez AI.



AI wykorzystywane jest tylko tam, gdzie klasyczne podejście nie działa.



\----------------------------------------------------------------------------------





\------  Wartość biznesowa ---------



\- skrócenie czasu obsługi (2 dni → minuty)

\- eliminacja pracy manualnej

\- spójność danych

\- możliwość raportowania

\- skalowalność systemu

