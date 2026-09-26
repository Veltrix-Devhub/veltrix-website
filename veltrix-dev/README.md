# Veltrix Dev Website

## Schnellstart
Öffne `index.html` lokal im Browser.

## Anpassen
Suche in `index.html` nach `DEINCODE` und ersetze es durch deinen Discord-Invite-Code.
Passe Script-Namen, Texte und Team-Mitglieder ebenfalls direkt dort an.

## Hosting auf demselben VPS wie FiveM (empfohlen: Nginx)
Website-Dateien z.B. nach `/var/www/veltrix` kopieren und deine Domain per DNS auf die VPS-IP zeigen lassen.

Beispiel Nginx-Konfiguration:

```nginx
server {
    listen 80;
    server_name veltrix.example www.veltrix.example;
    root /var/www/veltrix;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

Danach Nginx neu laden. Für HTTPS empfiehlt sich Let's Encrypt/Certbot oder alternativ Caddy, das HTTPS automatisch verwalten kann.

FiveM kann parallel weiter auf seinem eigenen Port (typisch 30120) laufen. Die Website sollte nicht als FiveM-Resource gehostet werden.
