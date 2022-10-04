# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
Commande : 
        curl -v --header x-student:RETY https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Réponse serveur:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 99924c17-364f-4120-824b-5a58404e78c8
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:30:30 GMT
< 


## Quel est la version du protocole utilisé par le serveur ?
La version du protocole HTTP utilisé est la version 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Requête :
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.82.0
> Accept: */*
> x-student:RETY
> 

Le header GET permet d'acceder à la ressource
Le header Host donne le site sur lequel on essaye de se connecter
Le header User-Agent est notre moyen d'accès au site
Le header Accept permet de connaitre quel type de contenu l'utilisateur peut interpreter
Le header x-student est le header que l'on a rajouté dans le but de communiquer notre nom

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.

On a la date d'optention et de fin du certificat SSL, 
le fournisseur et ceux qui ont délivrés le certificat

## Quel est le code de la réponse ? Que signifie-t-il ?
On obtient un code 200 signifiant que c'est bien passé
## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK 

HTTP/1.1 : version du serveur
200      : code de retour
OK       : signification du code de retour

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
il faut utiliser le --data

Commande exécutée :
curl -v --header x-student:RETY --data "Bonjour" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 

requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.82.0
> Accept: */*
> x-student:RETY
> Content-Length: 7
> Content-Type: application/x-www-form-urlencoded

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e61b7c6d-4d30-4f8b-9829-a2fe64cc5d2f
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:04:01 GMT


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

Requête : curl --header x-student:RETY -H "Content-Type: application/json" -v -X POST -d '{"login":"pet","password":"ouaf"}' https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 

Requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.82.0
> Accept: */*
> x-student:RETY
> Content-Type: application/json
> Content-Length: 33

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: f2686cf3-602e-4a14-ae33-bb898a3bf1f4
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:24:47 GMT
## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
Première méthode :
curl -v --header x-student:RETY -u "login:password" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 

Requête :
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> Authorization: Basic bG9naW46cGFzc3dvcmQ=
> User-Agent: curl/7.82.0
> Accept: */*
> x-student:RETY

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e5394f27-c2d6-4f74-a4e4-35270bce59b8
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:31:24 GMT


Deuxièe méthode :
curl -v --header x-student:RETY -u "login:password" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"

Requête :
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.82.0
> Accept: */*
> x-student:RETY
> Authorization: Basic bG9naW46cGFzc3dvcmQ

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 15eac991-a3f6-460c-97fb-085fc8a76e40
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:32:23 GMT
## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

Ne fontionne pas, on obtient une erreur
## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Réponse :

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8" />
    <meta name="robots" content="noindex,nofollow,noarchive" />
    <title>An Error Occurred: Method Not Allowed</title>
    <style>body { background-color: #fff; color: #222; font: 16px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; margin: 0; }
.container { margin: 30px; max-width: 600px; }
h1 { color: #dc3545; font-size: 24px; }
h2 { font-size: 18px; }</style>
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
</html>


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
