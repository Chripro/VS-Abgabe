# VS Abgabe
 Abgabe ohne Passwörter

client: React Frontend

server: Go mit Mux Router als Backend und MongoDB Datenbank in Amazon Cloud (normalerweise)

NGINX Einstellungen f�r Lastenverteilung:
in default.config:

upstream www {
        server todo1.systes.net;
        server todo2.systes.net;
}
server {
        listen 80;
        server_name todo.systes.net;
        location / {
          proxy_pass http://www;
        }
}
