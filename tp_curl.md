# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: AKLI" -v
HTTP/1.1 200 OK


## Quel est la version du protocole utilisé par le serveur ?
HTTP 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
Host: webhook.site
User-Agent: curl/7.80.0
Accept: */*
x-student: AKLI

GET est la méthode qui nous permet de récuperer la ressource d4ec90aa-8173-48dd-8414-6fb832ea2a26
HTTP/1.1 nous indique la version du protocole
Host est l'adresse url qui contient notre ressource


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.



## Quel est le code de la réponse ? Que signifie-t-il ?
200: succée de la requête

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
HTTP/1.1 200 OK
< Server: nginx // type du serveur
< Content-Type: text/plain; charset=UTF-8 // type de conteunu et d'encodage
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 84e6c732-9960-4c81-9753-0eaa9ffdf4f5 // ID de la requête
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private // nous dit que l'on ne peut pas utiliser le cache
< Date: Thu, 29 Sep 2022 14:09:43 GM // date et heure de la requête


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: AKLI" -H "Content-Type: text/plain" -v -X POST --data "ceci est du texte"
 la requete:
 POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.80.0
> Accept: */*
> x-student: AKLI
> Content-Type: text/plain
> Content-Length: 17

la réponse:
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: ca7c7f48-7716-427d-993f-ad590fdffdfc
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:36:28 GMT


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: AKLI" -H "Content-Type: application/json" -v -X POST --data "{nom : AKLI}"

la requete:
POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.80.0
> Accept: */*
> x-student: AKLI
> Content-Type: application/json
> Content-Length: 12

la réponse:
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 7659add8-38a1-46bd-9bef-9f442fc34865
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:40:19 GMT



## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois
méthode 1:
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: AKLI" -H "Authorization: Basic sijqsjdcnbqij" -v

la requete
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.80.0
> Accept: */*
> x-student: AKLI
> Authorization: Basic sijqsjdcnbqij

la réponses
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 30b8cbc0-2f93-4d32-aa42-8d8d109fb892
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:45:45 GMT

méthode 2
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: AKLI" -u "allo:hello" -v

la requete
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic YWxsbzpoZWxsbw==
> User-Agent: curl/7.80.0
> Accept: */*
> x-student: AKLI

la response
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 14ffbd46-3d6b-407b-8d4d-890a8b0e11fa
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:48:37 GMT


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
curl -X PATCH https://demo.api-platform.com/top_books/1

la response:

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
405 la méthode n'est pas autorisée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}



## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}


## Quel est le code HTTP ? Que signifie-t-il ?
404 la ressource est introuvable

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
301 Moved indique que la ressource a définitivement été déplacée à l'URL contenue dans l'en-tête Location

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
on ajoute -L à la fin de la requete pour suivre la direction indiqué par location
on rajoute www à l'url 
