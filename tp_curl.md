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

Néanmoins, avec une requête demandant une réponse en HTML

curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 -H "Accept: text/html" -v

On obtient la réponse suivante :

> GET /books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 HTTP/2
> Host: demo.api-platform.com
> user-agent: curl/7.82.0
> accept: text/html

< HTTP/2 200 
< date: Tue, 25 Oct 2022 14:00:03 GMT
< content-type: text/html; charset=utf-8
< cache-control: s-maxage=10, stale-while-revalidate
< link: </docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation", </.well-known/mercure>; rel="mercure"
< permissions-policy: browsing-topics=()
< vary: Accept-Encoding
< x-nextjs-cache: STALE
< x-powered-by: Next.js
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=bOBUTSsnEuZn7r8FwJIScyEhs7C3Z84BLr4ay%2BJRv01PIm2AqkTD8NesX90F%2BEoH13uSLqOgudIIQOBR9HXISleVHeWf5pEbC2MOeyCawax6%2BUfsycyMuRUTyKuY0ehP8ZoOXX2G%2B5A%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fb79eb3d133761-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

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

Le code reçu est 405 Method Not Allowed.
Cela correspond à une requête connue par le serveur mais non supportée par la ressource ciblée.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Commande sans le verbose:

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}%

Commande avec le verbose:

> GET /top_books/1 HTTP/2
> Host: demo.api-platform.com
> user-agent: curl/7.82.0
> accept: */*
> 

< HTTP/2 200 
< date: Tue, 25 Oct 2022 14:16:32 GMT
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
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=h4TuEqdosin2LC4kAG4vjUdl8zUaNwkKqGGpES%2BPmyawOvXo4ADPiAUdkHEetQGkPTSfYfh%2BizOWFs9g48tqHS4MT9tswTAdUPOBxhhBaobji9MRPz6s96S%2Bk643zXnCC5LP%2Bq8OsVU%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fb92117d58691b-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

Commande sans le verbose:

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}%

Commande avec le verbose:

> GET /top_books/9999 HTTP/2
> Host: demo.api-platform.com
> user-agent: curl/7.82.0
> accept: */*
> 

< HTTP/2 404 
< date: Tue, 25 Oct 2022 14:19:10 GMT
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
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=gAcfK3l29wMyWe0saYW6Id%2F%2BcfFSrwdjqE7nV3wqpoz8%2FZEnBTB3vgrhtAJIND%2FyT3DayLXC2VVpobX9LV0%2FQf0GocU9iSAxVBkLU%2BZq23DugqXv1if3j6hfsGNC1k0rM2KVRi2vOr8%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fb95f14e969a11-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}%

## Quel est le code HTTP ? Que signifie-t-il ?

Le code HTTP reçu est 404. Cela signifie que le serveur n'a pas trouvé la ressource demandée.
Cela veut probablement dire que le livre 9999 n'existe pas.
## Exécuter la requête suivante et copier la réponse : curl https://google.fr

```HTML
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>
```

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code reçu est 301. Il signifie une redirection définitive vers l'URL indiqué dans l'entête.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

On peut rajouter -L à la requête.
    curl https://google.fr -L

On peut aussi rajouter 'www' à l'URL car c'est ceci qui produit le code 301.
    curl https://www.google.fr/
