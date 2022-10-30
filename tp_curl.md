# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

Requête : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: ALLARD" -v
Réponse : HTTP/1.1 200 OK

## Quel est la version du protocole utilisé par le serveur ?
HTTP 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: ALLARD

GET est la requête d'accés à la ressource d4ec90aa-8173-48dd-8414-6fb832ea2a26
Host: est l'url du site auquel on essaye d'accéder
User-agent: il s'agit du moyen d'accès, ici avec curl (avec une requête sur firefox, on aurait firefox/version
Accept*/* indique le type de contenu que le client sera capable d'intérpréter
x-student est le paramètre que l'on a rajouté qui contient notre nom

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
On a la date d'obtention du certificat, sa date d'expiration, son fournisseur, si il est encore valide (déductible de la date de fin), et l'organisme d'identification du certificat (Let's Encrypt)
## Quel est le code de la réponse ? Que signifie-t-il ?
200, ce qui signifie un succès

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 2b680ea0-fa9b-4fcc-a951-05e5d9485657
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:09:13 GMT

- Résultat de la requête
- Le type de serveur (ici nginx)
- Type de contenu retourné
- L'encodage
- Determine si on peut utiliser le cache
- Id de la requête (idéal pour le bug report)
- X-token-id : convention de header customisé
- Paramètre du cache
- Date de la réponse

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
Requête : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: ALLARD" -H "Content-Type: text/plain" -v -X POST --data "ceci est du texte super stylé"
Réponse :
POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: ALLARD
> Content-Type: text/plain
> Content-Length: 30
> 
* upload completely sent off: 30 out of 30 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 5fc2dd86-7dbd-4322-b589-c5f37f7bab6a
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:35:44 GMT


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

Requête : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: ALLARD" -H "Content-Type: application/json" -v -X POST -d '{"login":"miaou","password":"miaou"}'

Réponse:
POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: ALLARD
> Content-Type: application/json
> Content-Length: 36
> 
* upload completely sent off: 36 out of 36 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 940a9e20-321d-4093-99f5-303d92b78cae
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:38:34 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
Requête 1 : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: ALLARD" -H "Authorization: Basic ziggydongue" -v
Réponse 1 : 

> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: ALLARD
> Authorization: Basic ziggydongue
> 
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 765254dc-53a7-4f15-9d67-96f512d85eba
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:44:22 GMT

Requête 2 : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: ALLARD" -u "ziggy:dongue" -v 
Réponse 2:
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic emlnZ3k6ZG9uZ3Vl
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: ALLARD
> 
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: d301e494-583d-4cae-8428-84b2f55e7cbc
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:46:28 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

// problème technique du serveur

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

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

405 Method not allowed, signifie que l'on ne peut pas utiliser le PATCH dans notre requête

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
404 Not Found, signifie que le livre 9999 n'existe pas

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

301 Moved, indique que la ressource à été déplacée à l'URL contenu en en-tête
## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
- En rajoutant un -L qui permet de suivre les redirection contenu dans "location:"
- En rajoutant "www" dans ce cas précis car le site est https://www.google.fr
