## Open Banking Payment 

Über das Projekt
Dieses Projekt zeigt eine modellierte Architektur für eine Open-Banking-Payment-App mit UML-Diagrammen und API-Spezifikation. Ziel ist es, eine Fintech-Lösung für sichere Zahlungsabwicklung und Bankkontenverwaltung über Open-Banking-APIs zu visualisieren und zu dokumentieren.

## **Use-Case-Diagramm für Open Banking Payment**

### **Beschreibung**  
Das Use-Case-Diagramm zeigt die wichtigsten Interaktionen, die ein Nutzer in der Payment-App durchführen kann. Es gibt einen Überblick darüber, welche Funktionen das System bereitstellt und welche Aktionen ein Nutzer ausführen kann.

### **UML-Diagramm**
![Use-Case-Diagramm](http://www.plantuml.com/plantuml/png/PT6zJiCm40Vm_PxYbDq3_LXGLRMK3GcGW8NjI2-9bUGIdS-L2EBDklN5I4HKBB5O_jk_EzloBXYfnRO1yzOmlWLs1ng7Uq-bKjkYmwUU1Uz8QYybFjDdos80b5kdc3r66rWpf33LAe1oRYJbs2kRhTltVOPVW1W3vnJ6dOTEhCCJQosNSr-m_3OutFn3mKYEI1yQ_zGYLUzKDL5Af1YAoxdIgrgcwbL90jNcEmadrePYWIG3-_BgLwb_yNd5Mh6tuFRHAXRpXHyywtZMNB26Ru3fqUZSThfy6XPfMAPX1UF2F5_ZBMush4MdHrRRRW5sBCVfFtu0)  


### **Haupt-Use-Cases und ihre Beschreibung**
| **Use-Case**                  | **Beschreibung** |
|--------------------------------|----------------|
| **Konto verknüpfen** (`UC1`)   | Der Nutzer authentifiziert sich über OAuth2 und verbindet sein Bankkonto mit der Payment-App. |
| **Kontostand abrufen** (`UC2`) | Der Nutzer kann den aktuellen Kontostand seines verknüpften Kontos abrufen. |
| **Zahlung ausführen** (`UC3`)  | Der Nutzer kann eine neue Zahlung an einen Empfänger senden. |
| **Transaktionsverlauf anzeigen** (`UC4`) | Der Nutzer kann eine Liste seiner bisherigen Transaktionen einsehen. |
| **Sicherheits-Authentifizierung** (`UC5`) | Stellt sicher, dass der Nutzer sich korrekt authentifiziert, bevor sensible Aktionen (z. B. Zahlungen) durchgeführt werden können. |


### **Beziehungen zwischen den Use-Cases**
- **Der Nutzer kann verschiedene Aktionen ausführen**, wie z. B. **Konto verknüpfen, Kontostand abrufen, Zahlung ausführen und Transaktionsverlauf einsehen**.  
- **Die Sicherheits-Authentifizierung (`UC5`) ist eine Voraussetzung für die Zahlung (`UC3`)**, um sicherzustellen, dass der Nutzer autorisiert ist.  
- **Die Payment-App verwaltet die Interaktion mit der Open-Banking-API**, um die gewünschten Funktionen bereitzustellen.  

### **Warum ist dieses Use-Case-Diagramm wichtig?**
- Es visualisiert die **wichtigsten Funktionen** der Payment-App.  
- Es zeigt, wie **der Nutzer mit dem System interagiert**.  
- Es hilft Entwicklern und Analysten, **die Anforderungen an die App besser zu verstehen**.  
- Es verdeutlicht, dass **Sicherheits-Authentifizierung eine zentrale Rolle spielt**.  


## **Sequenzdiagramm für Open Banking Payment**

### **Beschreibung**
Dieses Sequenzdiagramm zeigt den Ablauf einer Zahlung über eine Open-Banking-API. Dabei interagieren vier Hauptakteure:
1. **Nutzer** – Der Endbenutzer, der sich authentifiziert, seinen Kontostand abruft und eine Zahlung ausführt.
2. **Payment-App** – Eine Fintech-Anwendung, die als Schnittstelle zur Open-Banking-API dient.
3. **Open Banking API** – Eine standardisierte API, über die Banken an das Open-Banking-Ökosystem angebunden sind.
4. **Bankensystem** – Das Backend der jeweiligen Bank, das Anfragen zur Kontostandsabfrage und Zahlungsdurchführung verarbeitet.


### **Ablauf des Sequenzdiagramms**
1. **Authentifizierung via OAuth2:**  
   - Der Nutzer startet die Anmeldung in der Payment-App.
   - Die App fordert über die Open-Banking-API eine OAuth2-Authentifizierung an.
   - Der Nutzer loggt sich bei seiner Bank ein und gibt die Berechtigungen frei.
   - Die API gibt ein OAuth2-Token zurück, das für weitere API-Anfragen genutzt wird.

2. **Kontostand abrufen:**  
   - Der Nutzer fordert über die App seinen Kontostand an.
   - Die App sendet eine Anfrage an die Open-Banking-API (`GET /accounts`).
   - Die API fragt die Kontoinformationen beim Bankensystem ab und sendet die Daten zurück.
   - Die App zeigt dem Nutzer seinen aktuellen Kontostand an.

3. **Zahlung initiieren:**  
   - Der Nutzer gibt eine neue Zahlung mit Empfänger und Betrag in der App ein.
   - Die App sendet die Zahlungsdetails an die Open-Banking-API (`POST /payments`).
   - Die API leitet die Zahlung an das Bankensystem weiter.
   - Das Bankensystem verarbeitet die Zahlung und sendet den Status zurück.
   - Die App zeigt dem Nutzer die Zahlungsbestätigung an.

### **Diagramm**
![Sequenzdiagramm](https://www.plantuml.com/plantuml/png/VPB1QXin48RlUeeXXv90JQ57WqiSCAMqn8Rab9jsTrOU8essqgWGFqyU8pU_MAMr5TYDoKcizEd_v_-rjr5qaEIi4XABi1sGuKxpCx61dNvno08BUC2_2VdGaJP1EwUKRiK7k4zomA26B44j3JgpL-TBY_KmN86EaDSfCB5OxtuLggnJgW38yIKAkaACDvHQhM2TP8yirDE1CAGiyeyqRClsTrYjr6aeMFmerajOiqFR5MoCYgpoTZdDbijwxQEcvjw73WEhp1Ny9Bk4FzuGGuC4-NIS2Z2SM4ljljfNWmsnzSOWmnTuIb78kI9liC6pT1tqFCgZpxdX-DPWS2I2biVKlpsBpmcu0zs4r2D_p3g1-81aPcb_RXxXcsvRdrWYN6VzazrD3LdYd6Me5E2qa6Vawgd6l8kgDuATbWnOmXx3B58zdmSQPthlzFBS9VIJtjlI5Z494OQBeUynOINh6yFrnWtzyPKDXgzmXnAqkPbKiTi-v2w6yhD-saKLRb2dliZCIwX4pDQI8XnIEBwrpnSUk88DHZc-2fdyCQzYhlPUnorobvpz3m00)

### **Warum ist dieses Diagramm wichtig?**
- Es visualisiert die **Interaktion zwischen Nutzer, App, API und Bank**.
- Es zeigt die **zentrale Rolle von OAuth2** für sichere Authentifizierung.
- Es verdeutlicht die **API-Aufrufe**, die für Open Banking unerlässlich sind.
- Es hilft Entwicklern und Analysten, **die Systemabläufe zu verstehen und zu optimieren**.

__Klassendiagramm__


## **Klassendiagramm für Open Banking Payment**

### **Beschreibung**
Das Klassendiagramm modelliert die wichtigsten Datenstrukturen und deren Beziehungen in der Open-Banking-Payment-App. Es zeigt, wie Nutzer, Konten, Transaktionen und die API-Kommunikation organisiert sind.


### **UML-Diagramm**
![Klassendiagramm](http://www.plantuml.com/plantuml/png/ZLB1JW8n4BttAoPxOgEGUDqO0iIO44qaGJzWh0CqjBEadHgL-EzkGt6xUF54vysyUOytEmk2NgApIenOWgS3CIoGzuQtiC9FHommXWUB8H2_6TnwT4ufdG1u2UJXg02kOlTQtZMm5jyn4yBegAp9eR4bW5gtaIKqy6Y2tCvFvLHzdxTd18x5z533l2ANTLVkXxL5rjJ0lMrH4Y8UEQ0Mq_9P-Bc72l42XUC5SsW2NJ9MQ7ZIvc28fPmAWX93YT07wIYKGnxL3IpQrX9oRoBtrkJVZQQJ3yD63FQyWVmr_16l4sbBajDSd28PrPdHYwMhprVB77UK7R4OZKBfogEwjBuXqRkyCAJMu89f8dqi_tPuVYGlIGogcmh6OwYuWhnKvT-YLPv8NIGrcKn__qy37ELBL36U-fVXDk3ZHW3ZHiqwyz7P7m00)  


### **Hauptklassen & deren Funktionen**
| **Klasse**        | **Beschreibung** |
|-------------------|----------------|
| `User`           | Repräsentiert den Nutzer der Payment-App. Jeder Nutzer kann mehrere Bankkonten besitzen. |
| `Account`        | Stellt ein Bankkonto dar. Enthält Informationen wie IBAN, Bankname und Kontostand. Ein Konto kann mehrere Transaktionen enthalten. |
| `Transaction`    | Speichert eine einzelne Zahlung oder Buchung. Enthält Betrag, Empfänger und Status der Transaktion. |
| `PaymentService` | Schnittstelle zwischen der App und der Open-Banking-API. Verantwortlich für die Initiierung von Zahlungen und das Abrufen von Kontoständen. |
| `BankAPI`        | Stellt die Verbindung zum Bankensystem her und ermöglicht Authentifizierung, Kontenabfragen und Zahlungsabwicklung. |


### **Beziehungen zwischen den Klassen**
- **Ein `User` kann mehrere `Accounts` besitzen** → (1:n Beziehung).
- **Ein `Account` kann mehrere `Transactions` enthalten** → (1:n Beziehung).
- **Die `Transaction`-Klasse ruft Methoden des `PaymentService` auf**, um Zahlungen auszuführen.
- **Der `PaymentService` kommuniziert mit der `BankAPI`**, um Daten von der Bank abzurufen oder Zahlungen zu übermitteln.


### **Warum ist dieses Klassendiagramm wichtig?**
- Es zeigt die **Datenstruktur hinter einer Open-Banking-Payment-App**.  
- Es verdeutlicht die **Zusammenhänge zwischen Nutzer, Konto und Transaktionen**.  
- Es hilft Entwicklern, **die Systemarchitektur schnell zu verstehen**.  
- Es unterstützt die Planung und Erweiterung der API-Integration.


## **BPMN-Diagramm: Zahlung via Open Banking API**

### **Beschreibung**
Das BPMN-Diagramm visualisiert den **Geschäftsprozess zur Durchführung einer Zahlung über eine Open-Banking-API**. Es zeigt Schritt für Schritt, wie eine Zahlung initiiert, validiert und verarbeitet wird, einschließlich aller wesentlichen Entscheidungen und Fehlerbehandlungen.

---

### **BPMN-Diagramm**
![BPMN Zahlungsprozess](<https://www.plantuml.com/plantuml/png/NP4nSl8m58HxdMAhVw3uBs0N0OQ4IGecJPfqp_6phB7yy4ZF59o7Oz3vOh45U0ZbQlRRNKchg1IqRxrHfvwnRjGTdGvdZQKZ6wXjCtnJxNknaGfFVMLCOaosx_N40TOLYjUsguQps57_muOra0KxoKssxZeSoRlIST1xL6vSXSMMb0ND8GHkz6K9hKUv-A2b0H8NMKgU8P1WGzByNt--vvDb4kZ2SAaKM_vfKZ0mHUzOXeiTSUnwhQbWUSg_umN7wRREFcm3RlqdVZYFi_LcOXyPYpqxMJuZRrnx3Xc-nDw7S9od95XALvc_4TaLQzcNOqMYXuiV2ndfgN9pfQ8UEcDMevW-xXS0>)

---

### **Prozessschritte im Detail**
| Schritt | Beschreibung |
|---------|--------------|
| **Zahlungsdetails eingeben** | Der Nutzer gibt Empfänger und Betrag der Zahlung ein. |
| **Zahlungsdetails validieren** | Die App prüft die eingegebenen Daten auf Vollständigkeit und Korrektheit (z. B. IBAN-Format). |
| **OAuth2-Authentifizierung prüfen** | Die App prüft, ob der Nutzer über einen gültigen OAuth2-Token verfügt. |
| **Zahlung an Bank senden** | Die Zahlungsdaten werden über die Open-Banking-API an das Bankensystem weitergeleitet. |
| **Bank prüft Guthaben** | Die Bank kontrolliert, ob ausreichend Guthaben vorhanden ist. |
| **Zahlung durchführen** *(Erfolgsfall)* | Bei ausreichendem Guthaben wird die Zahlung ausgeführt. |
| **Zahlungsbestätigung an Nutzer senden** *(Erfolgsfall)* | Der Nutzer erhält eine Bestätigung der erfolgreichen Zahlung. |

---

### **Mögliche Fehlerfälle**
- **Ungültige Zahlungsdaten** → Fehlermeldung an Nutzer: „Zahlungsdaten ungültig“.
- **OAuth2-Authentifizierung fehlgeschlagen** → Fehlermeldung an Nutzer: „Authentifizierung fehlgeschlagen“.
- **Nicht genug Guthaben** → Fehlermeldung an Nutzer: „Nicht genug Guthaben“.


### **Warum ist dieses BPMN-Diagramm wichtig?**
- **Klarheit über den Zahlungsprozess** für Analysten, Entwickler und Stakeholder.  
- Schnelle **Identifikation von Fehlerstellen** und **Optimierungspotenzialen** im Prozess.  
- **Basis für Anforderungen** bei der Implementierung einer Open-Banking-Schnittstelle.









