# Projektidee Modul 300

## Grundbeschrieb

Ich baue eine Wetterplattform, auf der sich Nutzer anmelden. Mit ihrem Login können sie dann ihre Lieblingsorte speichern und das aktuelle Wetter und die 7-Tage Vorhersage abrufen. Die Daten werden von einer externen Wetter API geholt. 
Die Website besteht aus einem Frontend (Website), einer REST-API und mehreren Cloud Diensten. 

Technologie:

HTML und CSS für das Frontent (Benutzeroberfläche)

- Wetteranzeige für aktuellen Standort oder gesuchte Stadt
- 7 Tage Vorhersage mit Symbolen und Temperaturen
- Favoritenliste der Städte
- Benutzerregistrierung und Login mit typescript

Hosting:
- Deployment auf AWS S3
- Verteilung über Cloud Front


Datenbank: 

MySQL Service 

Gespeichert werden:

- Benutzer IDs
- Liste von Lieblingsorte pro Benutzer


Authentifizierung

- Login mit E-Mail & Passwort 



Monitoring und Logs:

- mit AWS CLoud Watch
    - Logs für REST-API und Fehler
    - fürs Erstellen von Dashboards
