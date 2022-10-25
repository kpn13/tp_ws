# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 

**Requete** : 
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:RachdiChemseddine
> 


**Reponse** : 
< HTTP/1.1 410 Gone
< Server: nginx
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Cache-Control: no-cache, private
< date: Thu, 29 Sep 2022 15:23:09 GMT
< 
<!DOCTYPE html>
<html>
<head>
    <title>Error: Too many requests, please create a new URL/token - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">410 Too many requests, please create a new URL/token</p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>



## Quel est la version du protocole utilisé par le serveur ?
HTTP 1.1



## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:RachdiChemseddine


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384



## Quel est le code de la réponse ? Que signifie-t-il ?

**Code** : 410
**Signification** : l'accès à la ressource n'est plus disponible sur le serveur.



## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9d9d1b1c-c66c-4f91-9617-6ffce9158b42
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:50:34 GMT


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl -X POST -H "Content-Type: text/plain" "TextBrute" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

**Requete** : 

> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Type: text/plain
> 


**Reponse** : 

< HTTP/1.1 410 Gone
< Server: nginx
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Cache-Control: no-cache, private
< date: Thu, 29 Sep 2022 15:27:02 GMT
< 
<!DOCTYPE html>
<html>
<head>
    <title>Error: Too many requests, please create a new URL/token - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">410 Too many requests, please create a new URL/token</p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>



## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -X POST -H 'Content-Type: application/json' --data '{"username":"chems","password":"123"}' -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

**Requete** : 

> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Type: application/json
> Content-Length: 37
> 

**Reponse** :
< HTTP/1.1 410 Gone
< Server: nginx
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Cache-Control: no-cache, private
< date: Thu, 29 Sep 2022 15:28:55 GMT
< 
<!DOCTYPE html>
<html>
<head>
    <title>Error: Too many requests, please create a new URL/token - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">410 Too many requests, please create a new URL/token</p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>




## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

curl -X POST -u "chems:123" -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Authorization:Basic 123"

**Requete** : 

> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic Y2hlbXM6MTIz
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:RachdiChemseddine


**Reponse** : 
< HTTP/1.1 410 Gone
< Server: nginx
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Cache-Control: no-cache, private
< date: Thu, 29 Sep 2022 15:30:55 GMT
< 
<!DOCTYPE html>
<html>
<head>
    <title>Error: Too many requests, please create a new URL/token - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">410 Too many requests, please create a new URL/token</p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6:  

**reponse** :
< HTTP/2 404 
< date: Thu, 29 Sep 2022 15:32:16 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=JM9pIh0jnfqqmd%2F%2F0YKvnZyc4ENxJWkq6uDqzht5Rj82RD6IT16SZKFTBCn%2FmU1%2FyFRQ0wJ3iQW648y6YDeoEppArUUb%2BfZTtMsbLGBm1ihEP9BhzRbA9bB1OCD%2Bt0MriF5iZ5DJb1s%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 7525c545ba4bbbf7-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 
* Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}



## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

**reponse** : 
< date: Thu, 06 Oct 2022 14:32:18 GMT
< content-type: text/html; charset=UTF-8
< allow: GET
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 405 Method Not Allowed
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=sAg8I6lB3ORvW%2BCT3bKHQk44XqLQx%2FTaEG3MQV3RctjziZV8SAon5Mq8EsthhDBUj37XeJmwtoZo6iBXknLcfmUCCS%2F1wZD%2BEhFtAEOtyTWgUVzxD5eMFTsNIgFbWSDQ02ILfG2dP50%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 755f1b0bda905995-MXP
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
* Connection #0 to host demo.api-platform.com left intact
</html>  



## Quel est le code HTTP reçu ? Quel est sa signification ?

**code** : 405
**Signification** : Method not allowed (la méthode HTTP n'est pas autorisée par le serveur)



## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

**reponse** :
< HTTP/2 200 
< date: Fri, 30 Sep 2022 11:27:06 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 183
< cache-control: no-cache, private
< etag: "06a23177dff31429d2a7390117fe1b2d"
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< vary: Accept
< vary: Content-Type
< vary: Authorization
< vary: Origin
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=m2iNRGXyfqKufUMbV3SVtzmxwzCJCp4OMysEBHkLZ%2FpbertFQG5gIT3sZMvuxv56WS%2Fs3zHdz405UbmM%2BY5JsWiVVaOjyK6Tfw5BKJBbjegyl4StlFhwBbE3kyEb57Ek67h4Otwiulg%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 752c9b7e4a62927d-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 
* Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

**reponse** :
< HTTP/2 404 
< date: Fri, 30 Sep 2022 11:27:39 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=2iV33fmWFcmE5LovAR%2F%2B5Acz99uJUNfJ6v%2FhxoCSmji8y87y5P0RtQBWktivSFdeqpLIbMgnqifbGi13onUDUEr%2F6JyYroqnMnC7VWLIa1wAQNeDR7Ek%2F55e9dKrzVncaiTJ55QIUIY%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 752c9c519db2374c-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 
* Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}



## Quel est le code HTTP ? Que signifie-t-il ?

**Code** : 404
**Signification** : page not found.



## Exécuter la requête suivante et copier la réponse : curl https://google.fr

**reponse** :
< HTTP/2 301 
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Fri, 30 Sep 2022 11:28:11 GMT
< expires: Fri, 30 Sep 2022 11:28:11 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+241; expires=Sun, 29-Sep-2024 11:28:11 GMT; path=/; domain=.google.fr; Secure
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

**Code** : 301
**Signification** : indique que le contenu de la page n'est plus disponible à l'URL renseignée



## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

**solutions** :  
*1* curl -L https://google.fr
*2* curl https://www.google.com/