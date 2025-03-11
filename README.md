## Open Banking Payment - Sequenzdiagramm

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

