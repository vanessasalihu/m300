
## 13.05.2025

Projektidee gefunden


## 20.05.2025

Begonnen zu arbeiten.

Zuerst habe ich eine AWS Instanz erstellt

1.	EC2 Instanz erstellen
Ubuntu 22.04 LTS
Ports 22 (SSH) und 80 (HTTP) in der Security Group geöffnet


2. Habe ich mich mit der EC2 Instanz verbunden 

ssh -i /mnt/c/Users/salih/.ssh/key-300.pem ubuntu@52.86.197.92


3. System auf den neusten Stand bringen 

sudo apt update && sudo apt upgrade -y
sudo apt install nginx -y


4. Node.js & npm installieren (Version 20)

curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs


5. React Projekt erstellt

npx create-react-app weathernow-frontend
cd weathernow-frontend



6. Wetterfunktion in React einbauen

Datei src/App.js angepasst mit Eingabefeld, API-Aufruf, Anzeige
OpenWeatherMap API-Key eingefügt


7.	Projekt für Produktion bauen


npm run build


8. React-Build mit Nginx ausliefern

sudo rm -rf /var/www/html/*
sudo cp -r build/* /var/www/html/


9. Nginx konfigurieren 

sudo nano /etc/nginx/sites-available/default
folgenden Inhalt eingefügt: 


    server {
    listen 80;
    server_name _;

    root /var/www/html;
    index index.html;

    location / {
        try_files $uri /index.html;
    }
}


sudo nginx -t
sudo systemctl reload nginx

10. dann habe ich es im Browser getestet

Bis jetzt alles erledigt:

•	Öffentliche Website läuft auf EC2-Instanz
•	Nginx liefert React-Frontend aus
•	Wetterdaten werden über OpenWeatherMap API angezeigt





