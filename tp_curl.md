# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl -verbose --header "x-student: OSAMA ALLABWANI" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

## Quel est la version du protocole utilisé par le serveur ?

HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

Host: webhook.site -> Le IP/Domain de serveur
User-Agent: curl/7.83.1 -> Le nom d'application client
Accept: */* -> donne la liste des types de contenue que la client peut comprendre. Ici on accepte tous
Referer: rbose -> l'addresse de la page dont on fait la requête (utile pour l'analyse, logging, caching, etc)
x-student: OSAMA ALLABWANI -> custom header requis par l'excersise

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

On peut trouver "schannel: disabled automatic use of client certificate" qui dit qu'on a pas utilisé le certificat de client

## Quel est le code de la réponse ? Que signifie-t-il ?

le code est 200 et il signifie que la requête HTTP a bien passé sans erreur

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

Server: nginx -> le type de serveur
Content-Type: text/plain; charset=UTF-8 -> le type de contenue du corp de la réponse et le character set qu'il utilise (UTF8, ASCI, etc). Ici c'est du texte UTF8
Transfer-Encoding: chunked -> le type de codage utilisé pour transferer le corp de réponse. Ici c'est chunked, le serveur envoie la réponse dans des chunks de données
Vary: Accept-Encoding -> Le header montre le compotement du serveur par rapport à caching le reprosentation du ressource requis
X-Request-Id: 98355ae3-4bea-4601-ac10-962cf3283e36 -> le ID de requête generer par le serveur
X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 -> le ID de token d'authentification
Cache-Control: no-cache, private -> est-ce que la réponse a été envoyé de la cache ou non. Ici, non
Date: Thu, 29 Sep 2022 14:08:25 GMT -> la date de réponse

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl -verbose -H "x-student: OSAMA ALLABWANI" -H "Content-Type: text/plain; charset=UTF-8" -d 'Test' https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête :
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> Referer: rbose
> x-student: OSAMA ALLABWANI
> Content-Type: text/plain; charset=UTF-8
> Content-Length: 6

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: fe68b502-5ac0-4b09-ba8c-d2f171dfc4b7
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:38:34 GMT


Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl -verbose -H "x-student: OSAMA ALLABWANI" -H "Content-Type: application/json" -d "{\"Code\": \"Test\"}" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête :
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> Referer: rbose
> x-student: OSAMA ALLABWANI
> Content-Type: application/json
> Content-Length: 16

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: a6593e4c-24f7-4527-8690-9b301b1355d2
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:42:18 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

curl -verbose -H "x-student: OSAMA ALLABWANI" -u "osama:password" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête :
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic b3NhbWE6cGFzc3dvcmQ=
> User-Agent: curl/7.83.1
> Accept: */*
> Referer: rbose
> x-student: OSAMA ALLABWANI

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 8c5c01af-85dc-4256-a3f1-f2e49b4a94e6
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:45:13 GMT


curl -verbose -H "x-student: OSAMA ALLABWANI" -H "Authorization: Basic b3NhbWE6cGFzc3dvcmQ=" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête :
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> Referer: rbose
> x-student: OSAMA ALLABWANI
> Authorization: Basic b3NhbWE6cGFzc3dvcmQ=

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e9d6bc1a-bb81-49b0-a5e1-a13a139699b2
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:48:08 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


curl -X GET -verbose -H "x-student: OSAMA ALLABWANI" https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6


< HTTP/1.1 404 Not Found
< Date: Thu, 29 Sep 2022 14:50:35 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 120
< Connection: keep-alive
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< Status: 404 Not Found
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=xEJZ0icYpl036k4MBmwrono%2FsBxb%2FN9jozXoy%2F2RcVJLroFnUgGc5svs0OeBnf7DwVM8Ct2%2FavN4RrayVztFQY9%2FGdP3senGHT7v4h6vYzc6q7XJfI0eTpI6ZozlPgGSYDU%2FUhWeMFM%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 752588322dec993f-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl -X PATCH -verbose -H "x-student: OSAMA ALLABWANI" https://demo.api-platform.com/top_books/1

< HTTP/1.1 405 Method Not Allowed
< Date: Thu, 29 Sep 2022 14:52:35 GMT
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Connection: keep-alive
< Allow: GET
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Status: 405 Method Not Allowed
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=Nc5vlkyN%2BQWCluepJznMNlq1wxGXizyLnRccJTTLT9%2B48ZdV%2BvqFfbUisK6tD%2Flwdx5BqzelM8cUblQ1cBAHAzewZb0CMvqgfvm1l8kUVQ3G7vMlsqGRSk8Xj90GWHJnGyhu8C%2Fv5gM%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 75258b22c850927a-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
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

Le code est 405 et il signifie que la ressource ne supporte pas cette le méthode PATCH qu'on utilise

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl -verbose -H "x-student: OSAMA ALLABWANI" https://demo.api-platform.com/top_books/1

< HTTP/1.1 200 OK
< Date: Thu, 29 Sep 2022 14:56:33 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 183
< Connection: keep-alive
< Cache-Control: no-cache, private
< Etag: "06a23177dff31429d2a7390117fe1b2d"
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Vary: Accept
< Vary: Content-Type
< Vary: Authorization
< Vary: Origin
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=RK%2FnfJuT6QhpWRpVN9wRLnNQKu1XcpeTJMC74riK2pARenuTXlHgQk9zAxdzE4OZqaHL05dVV8y04bItibAUtB5k1z8nPVMJEMEWA67zELIudEb5l8G0VjW7S2As5Kzl%2FgFBwZQaBQo%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 752590f40f5fbb53-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

curl -verbose -H "x-student: OSAMA ALLABWANI" https://demo.api-platform.com/top_books/9999

< HTTP/1.1 404 Not Found
< Date: Thu, 29 Sep 2022 14:58:19 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 120
< Connection: keep-alive
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Status: 404 Not Found
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=YinAujNNqGD3touKAf25O7oz%2BtXykVyOJFSrOvE3hLNBX3hNxOolRjcYP8IHKjBrbtQP%2B6gcU0FoAVSa%2FcSsZsc5fplB3YI5Cilwbyc%2BUC1sSoSJHA3%2BnvXcZ0GAAg%2FF6ynXPmJqg6g%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 752593879cc4bb5c-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

le code est 404 et il signifie que le ressource qu'on cherche n'existe pas

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

curl -verbose -H "x-student: OSAMA ALLABWANI" https://google.fr

< HTTP/1.1 301 Moved Permanently
< Location: https://www.google.fr/
< Content-Type: text/html; charset=UTF-8
< Date: Thu, 29 Sep 2022 14:59:38 GMT
< Expires: Thu, 29 Sep 2022 14:59:38 GMT
< Cache-Control: private, max-age=2592000
< Server: gws
< Content-Length: 219
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
< Set-Cookie: CONSENT=PENDING+569; expires=Sat, 28-Sep-2024 14:59:38 GMT; path=/; domain=.google.fr; Secure
< P3P: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

le code est 301. Ici le serveur nous redirecte au URL https://www.google.fr/

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

On peut utiliser le URL: https://www.google.fr/ à la place de https://google.fr. Par ça on evite le redirection est on trouve la réponse qu'on attend.
curl -verbose -H "x-student: OSAMA ALLABWANI" https://www.google.fr

Aussi, on peut utiliser l'option -L pour dire à curl de suivre les redirections jusqu'à la fin et nous donner la réponse finale.
curl -verbose -H "x-student: OSAMA ALLABWANI" https://google.fr -L