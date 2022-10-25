# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "LACHEHEB"
Le système renvoie le code HTML de la page ayant l'URL passé

## Quel est la version du protocole utilisé par le serveur ?
curl -v https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "x-student: LACHEHEB"
la version : HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
-H "typeContenu: contenu" ==> Utiliser pour indiquer le type de la ressource envoyer
-H "Accept: text/html" ==> Le type de contenu que le client peut traiter
-d "[json data]"

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
SSL utilise TLSv1.3: c'est un protocol destiné à fournir une meilleure sécurité et à améliorer les pérformances


## Quel est le code de la réponse ? Que signifie-t-il ?
<!DOCTYPE html>
<html>
<head>
    <title>Error:  - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">404 </p>
                        <p class="small">
                    The URL was deleted manually, or expired automatically.

    To avoid URLs expiring automatically, you can
    <a href="/register">upgrade to Webhook.site Pro or Enterprise</a>.
            </p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>
===> signification: le code html de la page ayant l'URL passé en requête.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
HTTP/1.1 200 OK ===> La version du protocol utilisé par le serveur
Server: nginx ===> le nom du serveur
Content-Type: text/plain; charset=UTF-8 ===> type du contenu renvoyé
Vary: Accept-Encoding
X-Request-Id: 03287c3e-eb26-4915-9e00-a6aa67f46c10
X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
Cache-Control: no-cache, private ===> Le Cash de control
Date: Tue, 04 Oct 2022 14:54:03 GMT ===> La date de la requête

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
requête : curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "text: texte brute qui n'a aucun sens" -H"x-student: LACHEHEB"
réponse : le message est bien passé

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
requête : curl -H "Accept: application/json" -H "Content-Type: application/json" -d "{nom:LACHEHEB}" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe
réponse : upload est envoyé completement : 14 bytes sur 14

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

requête : curl --user xxsalouhxx:19 https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "x-student:LACHEHEB"
réponse:
<!DOCTYPE html>
<html>
<head>
    <title>Error: Token not found - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">404 Token not found</p>
                        <p class="small">
                    The URL was deleted manually, or expired automatically.

    To avoid URLs expiring automatically, you can
    <a href="/register">upgrade to Webhook.site Pro or Enterprise</a>.
            </p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>
mslacheheb@vm-etu-mslacheheb:~$ curl -v --user xxsalouhxx:19 https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "x-student:LACHEHEB"
*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
* successfully set certificate verify locations:
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Sep 30 23:06:26 2022 GMT
*  expire date: Dec 29 23:06:25 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
* Server auth using Basic with user 'xxsalouhxx'
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> Authorization: Basic eHhzYWxvdWh4eDoxOQ==
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:LACHEHEB

<!DOCTYPE html>
<html>
<head>
    <title>Error: Token not found - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">404 Token not found</p>
                        <p class="small">
                    The URL was deleted manually, or expired automatically.

    To avoid URLs expiring automatically, you can
    <a href="/register">upgrade to Webhook.site Pro or Enterprise</a>.
            </p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6

réponse : 
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

réponse : 
</head>
<body>
<div class="container">
    <h1>Oops! An Error Occurred</h1>
    <h2>The server returned a "405 Method Not Allowed".</h2>

    <p>
        Something is broken. Please let us know what you were doing when this error occurred.
        We will fix it as soon as possible. Sorry for any inconvenience caused.
    </p>
</div>
</body>
* Connection #0 to host demo.api-platform.com left intact


## Quel est le code HTTP reçu ? Quel est sa signification ?
CODE 405 méthode non allouée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
status: 404 Not Found ==> Page introuvable

## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
CODE 301
Il indique que la réssource a été déplacée dans l'URL contenue dans l'entête location


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
