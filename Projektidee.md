# Projektidee Modul 300

## Grundbeschrieb

Ich baue eine Wetterplattform, auf der sich Nutzer anmelden. Mit ihrem Login können sie dann ihre Lieblingsorte speichern und das aktuelle Wetter abrufen. Die Daten werden von einer externen Wetter API geholt. 
Die Website besteht aus einem Frontend (Website), einer REST-API und mehreren Cloud Diensten. 

## Technologie:

HTML und CSS für das Frontent (Benutzeroberfläche)

- Wetteranzeige für aktuellen Standort 
- Benutzerregistrierung und Login mit typescript

## Hosting:
- Deployment auf AWS S3
- Verteilung über Cloud Front


## Datenbank: 

RDS Datenbank Instanz auf AWS



## Authentifizierung

- Login mit E-Mail & Passwort 



## Monitoring und Logs:

- mit AWS CLoud Watch oder lokal auf der Instanz mit Logs
    - Logs für REST-API und Fehler
    - fürs Erstellen von Dashboards


## Optional, falls Zeit
Gespeichert werden:

- Liste von Lieblingsorte pro Benutzer