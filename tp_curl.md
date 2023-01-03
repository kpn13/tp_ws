Reponses TP1 -- Safae CHOUKRI -- TP GR3


# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl -v --header "x-student:choukri" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

## Quel est la version du protocole utilisé par le serveur ?
 http/1.1


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:choukri

-GET est la requete d'access
-host :  url site

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

SSL connection using TLSv1.3
SSL certificate verify ok.

## Quel est le code de la réponse ? Que signifie-t-il ?

le code de la réponse est 200 ==> succès

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 932e6b81-7553-4bb4-b408-e7ffaf8c46e2
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:02:44 GMT
 
1-la requete
2-le type serveur
3-le type de contenu
4-encodage
6-id de la requete
7-id du token
8-paramètre du cache
9- date de reponse


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl -v --header "x-student:choukri"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 "Content-Type: text/plain" POST --data "j'ai faim"

> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:choukri
> Content-Length: 9
> Content-Type: application/x-www-form-urlencoded

 upload completely sent off: 9 out of 9 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 641cd42c-a6a2-48a0-ae07-7a06ae7f91ed
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:25:08 GMT




## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl -v --header "x-student:choukri"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 "Content-Type: application/json" POST -d '{"name":"burger","mdp":"king"}'

> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:choukri
> Content-Length: 30
> Content-Type: application/x-www-form-urlencoded
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
< X-Request-Id: 6be052e2-7be8-41a1-8cbb-d044c715f2bb
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:39:51 GMT
< 



## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

1ere requete :  curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student:choukri" -H "Authorization: Basic mcdo" -v

> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:choukri
> Authorization: Basic mcdo
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
< X-Request-Id: e8cf6b3d-d8f8-49c8-a8e1-0dfdfad55358
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:55:11 GMT


2eme requete : curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student:choukri" -u "mcdo:frites" -v

 GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> Authorization: Basic bWNkbzpmcml0ZXM=
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:choukri


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
erreur
## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

execution de la commande avec PATCH  :  curl -X PATCH https://demo.api-platform.com/top_books/1

Reponse :
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




## Quel est le code HTTP reçu ? Quel est sa signification ?

Code HTTP reçu : 405 method not allowed, donc on ne peut pas utiliser la méthode PATCH pour cette requête

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

Not found ==> code HTTP 404

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

301 moved ==> la ressource a été déplacée

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

1-utiliser www.google.fr
2- utiliser l'option -L pour suivre les redirections
