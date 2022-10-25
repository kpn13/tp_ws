# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "x-student: Abdoulaye"

Requete:
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: Abdoulaye
> 

Reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 059648ed-04ae-4c00-97dd-956ec75b947a
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:29:24 GMT
< 


## Quel est la version du protocole utilisé par le serveur ?
La version du protocole utilisee par le serveur est HTTP/1.1


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Les headers sont :
Host: C'est le serveur qui heberge le service 
User-Agent: C'est le client utilisé pour requeter le serveur
Accept: C'est le statut d'acceptation de la requete 
x-student: C'est la signature qu'on a ajouté a notre requete 


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
On peut savoir si la connexion avec le serveur est securisée ou pas.

## Quel est le code de la réponse ? Que signifie-t-il ?
Le code de la réponse est 200. Ce qui signifie succes.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK
< Server: nginx 
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 059648ed-04ae-4c00-97dd-956ec75b947a
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:29:24 GMT


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl -d "Hello world" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v
Requete:
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Length: 11
> Content-Type: application/x-www-form-urlencoded
> 

Reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: b349bd59-451c-4bd6-9ba0-d5fa9dd293a8
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:38:00 GMT
< 


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:Abdoulaye" -d '{"Nom":"Abdoulaye Ali Bako", "Prenom":"Abdoul Alim"}' -H "Content-Type: application/json" -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -v

Requete:
> POST /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:Abdoulaye
> Content-Type: application/json
> Content-Length: 52
> 

Reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4100ba82-cd7e-4579-98c9-016002fd1b9d
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 14:42:10 GMT
< 


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
curl --header "x-student:Abdoulaye" -u "Nom":"Abdoulaye Ali Bako" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -v

Requete:
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> Authorization: Basic Tm9tOkFiZG91bGF5ZSBBbGkgQmFrbw==
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:Abdoulaye
> 

Reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 29bc51ad-f1cd-45c9-b107-32b493238495
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 14:48:05 GMT
< 




curl --header "x-student:Abdoulaye" -H "Authorization: Basic bG9naW46cGFzc3dvcmQ" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -v 

Requete:
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:Abdoulaye
> Authorization: Basic bG9naW46cGFzc3dvcmQ
> 

Reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: a90f95d3-93c2-4c43-bc36-27dfa8597162
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501




## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6
Requete:
> GET /books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 HTTP/2
> Host: demo.api-platform.com
> user-agent: curl/7.74.0
> accept: */*
> x-student:Abdoulaye

Reponse:
< HTTP/2 404 
< date: Tue, 25 Oct 2022 14:56:44 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=AUMcY23RBzkA0Z%2Fs9W3oMbJdXLT9bUmf9KnpmwIlu0%2FStaSsRiqJs6XQqkNzW5n8N%2BlWer6gNrhXdoFroj8DWDbQdS8sBQzayo7DiQKXIUhw2UVsTDQgVnyYyt2Dq2ugZyfQdU%2BI%2BV0%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fbccf83e32bb8b-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400



## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Requete:
> PATCH /top_books/1 HTTP/2
> Host: demo.api-platform.com
> user-agent: curl/7.74.0
> accept: */*

Reponse:
< HTTP/2 405 
< date: Tue, 25 Oct 2022 15:00:49 GMT
< content-type: text/html; charset=UTF-8
< allow: GET
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 405 Method Not Allowed
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=%2BTPVeW9g%2FslG3PqrWxIPfyVWXTf6sm%2BBc6lsoCp5T5RBlyev4SqUL3FkhNbyq7LFb8PLB9Kbg2XV5Ed4Iuqs%2B7GWTcneydOscCE3gDvu9LsFu3dK09qz2nkTJPDdufW8w8P7J%2BS4Dks%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fbd2f41a3b7a46-DUS
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


## Quel est le code HTTP reçu ? Quel est sa signification ?
Le code recu est: 405. Ce qui signifie que la methode n'est pas disponible.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
< HTTP/2 200 
< date: Tue, 25 Oct 2022 15:10:09 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 183
< cache-control: no-cache, private
< etag: "06a23177dff31429d2a7390117fe1b2d"
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< vary: Accept
< vary: Content-Type
< vary: Authorization
< vary: Origin
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=netzkNxRwBcvSNuEal9fXeRRtRy54OcLyEMdhY75ZroeCWNPouGmDniqymcrocuQomlqokpWhXYsX7ydKm5Tg0JAFqsS9n%2ByY27bkG7MJxsM1XOKpJH%2BOrD4rIVyr3SGkDhd6jUoL3g%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fbe09decaaf92f-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 



## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
< HTTP/2 404 
< date: Tue, 25 Oct 2022 15:11:29 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=SCXxi3oaRWrHb4pGILW3gtqZHpxskR8TtdDk%2FWD6EmtvmR1xGwx3zgDalO2C0eftlNUC02ZehdkQo148CIxhlYUZBWCDohFynwMdJdHV5Tq6GU1neJFIbikPmsHc4uu6GRRbmMHRXuY%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fbe2940e989078-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 


## Quel est le code HTTP ? Que signifie-t-il ?
Le code recu est: 404. Ce qui signifie que la page est introuvable.

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
< HTTP/2 301 
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Tue, 25 Oct 2022 15:13:32 GMT
< expires: Tue, 25 Oct 2022 15:13:32 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+897; expires=Thu, 24-Oct-2024 15:13:32 GMT; path=/; domain=.google.fr; Secure
< p3p: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
< 
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
Le code recu est: 301. Ce qui signifie qu'ily a une redirection definitive de la page.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

