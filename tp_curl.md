# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe
Nouvelle url : https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501
Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:DODEMAN" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Requête :
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN

Réponse :
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9b7dd6eb-f2bb-4c1e-85b9-f9f0bcb5fa9b
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:19:46 GMT
<
* Connection #0 to host webhook.site left intact

## Quel est la version du protocole utilisé par le serveur ?
HTTP/1.1 

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Header envoyés :
< x-student:DODEMAN -> les header à apporter avec la réponse 
< -v -> apporte beaucoup d'informations 

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
On peut trouver qu'il se connecte en utilisant TLSv1.3 
On peut trouver son certificat et qu'il est vérifié 

## Quel est le code de la réponse ? Que signifie-t-il ?
Le code est 200 OK. Il signifie que la requête est réussie. 

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
Status Line : 
< HTTP/1.1 200 OK 
< Date: Tue, 04 Oct 2022 14:19:46 GMT

Response header :
< Server: nginx

Entity header : 
< Content-Type: text/plain; charset=UTF-8

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:DODEMAN" -v --data "texte_brut" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN
> Content-Length: 10
> Content-Type: application/x-www-form-urlencoded

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: c5b8af76-7ebb-4bad-84cd-d4483a3f6fc5
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:47:51 GMT
<
* Connection #0 to host webhook.site left intact

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 --data "{"Hello" : "World"}" -H 'Content-Type: application/json' -H "x-student:DODEMAN" -v

Requête : 
> POST /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> Content-Type: application/json
> x-student:DODEMAN
> Content-Length: 15

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: c1d6baf6-80f1-406e-a74d-6fb984d7e2bc
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 14:39:11 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

Methode 1 : 
curl -v -H "x-student:DODEMAN" -u "utilisateur:MotDePasse" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501

Requête :
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> Authorization: Basic dXRpbGlzYXRldXI6TW90RGVQYXNzZQ==
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 23d05b22-afd4-4e91-bafc-ed924753f188
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 14:42:11 GMT

Methode 2 :
curl https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -v -H "x-student:DODEMAN" -H "Authorization: autorisation délivrée"

Requête :
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN
> Authorization: autorisation délivrée

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 39449701-1986-4d0f-86ca-118af0938b96
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 14:44:19 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
404 | This page could not be found

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
curl --header "x-student:DODEMAN" -X PATCH https://demo.api-platform.com/top_books/1

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
Le code reçu est 405, ça signifie que la méthode PATCH n'est pas authorisée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Réponse : 
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
Réponse :
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
Aucun code HTTP reçu

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
Réponse :
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
Le code reçu est 301, ça signifie une redirection d'url permanente 

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Solution 1 : curl -L https://google.fr -v

Solution 2 : curl -v https://www.google.com/
