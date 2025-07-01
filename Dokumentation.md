### Dokumentation


Als erstes habe ich meine EC2 Instanz erstellt im AWS

1.	EC2 Instanz erstellen
Ubuntu 22.04 LTS
Ports 22 (SSH) und 80 (HTTP) in der Security Group geöffnet


![Bild](EC2Instanz.png)


2. Dann habe ich der Instanz eine fixe IP zugewiesen

![Bild](ElasticIP.png)


3. Danach habe ich mich via SSH auf meine Instanz verbunden

<pre> ssh -i ~/.ssh/key-300.pem ubuntu@52.86.197.92 
</pre>


![Bild](sshRemote.png)

4. Danach habe ich meinen Server vorbereitet und Nginx als Webserver installiert 

<pre>sudo apt update && sudo apt upgrade -y
sudo apt install nginx -y
</pre>

5. Als nächstes habe ich Node.js installiert,mit dem ich den serverseitigen Code in JavaScript ausführen kann. Dies brauche ich später für meine REST-API im Backend und für die Verbindung zu meiner MySQL-Datenbank zur Speicherug meiner Login Daten. 

    Dazu habe ich noch npm installiert. Das ist der Paketmanager von Node.js.
    Ich brauche ihn für folgende Pakete:
  - express (API Server)
  - bcrypt (fürs Passwort Hashing)
  - mysql2 (für die Verbindung zur RDS-Datenbank)

<pre>
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
</pre>


6. Danach habe ich mit dem Dienst Aurora und RDS in AWS eine Datenbank erstellt 

![Bild](RDS.png)

Dabei habe ich direkt einen user ,,admin" mit Passwort und die DB ,,weathernow" erstellt

Danach habe ich mich folgendermassen von meiner EC2 Instanz aus auf meine DB connectet mit meinem Endpoint der RDS:

<pre> mysql -h weathernow-db.cqqr9mkqilvl.us-east-1.rds.amazonaws.com -u admin -p
</pre>

Dort drin habe ich dann die Tabelle Users erstellt, in der beim Registrieren, die Daten gespeichert werden.

<pre>
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  email VARCHAR(255) NOT NULL,
  password VARCHAR(255) NOT NULL
);
</pre>








