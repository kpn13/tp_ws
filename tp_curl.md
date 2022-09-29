# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
Commande: curl -H "x-student:loubet" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Requête: 
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:loubet

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: dc7cfb84-4a1b-449f-a547-05e5fd7aac4f
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:33:33 GMT

## Quel est la version du protocole utilisé par le serveur ?
HTTP 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Headers: GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
GET: Méthode appliquée à la requête
/d4ec90aa-8173-48dd-8414-6fb832ea2a26: URI
HTTP/1.1: Version du protocole utilisé

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
on peut trouver le cryptage utilisé (TLS1.3) et la méthode de cryptage (AES_256_GCM_SHA_384)
on peut également trouve la date de mise en place du certificat ainsi que sa date d'expiration, mais aussi l'autorité de confiance qui l'a délivré, et enfin, sa validité

## Quel est le code de la réponse ? Que signifie-t-il ?
200: Succès de la requête

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
Headers: HTTP/1.1 200 OK
HTTP/1.1: Version du protocole utilisé
200: Code de la réponse
OK: Signification du code de la réponse

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
Commande: curl -H "x-student:loubet" -v -X POST --data "sending raw text" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Requête: 
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:loubet
> Content-Length: 16
> Content-Type: application/x-www-form-urlencoded

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 3f9bf317-e8c3-4a38-b4ec-ef85565f00cd
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:38:24 GMT

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
Commande: curl -v -H "x-student:loubet" -X POST https://webhook
.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Content-type:application/json
" -d "{"login":"my-login", "password":"my-password"}"

Requête:
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:loubet
> Content-type:application/json
> Content-Length: 38

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 0fc327db-851d-4ae1-85b6-6f805c27d38b
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:46:29 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
Méthode 1:
Commande: curl -H "x-student:loubet" -u "login:password" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Requête:
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic bG9naW46cGFzc3dvcmQ=
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:loubet

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 2b90659a-c8b7-4604-bdcb-88fd392c1fb5
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:49:32 GMT

Méthode 2:
Commande: curl -H "x-student:loubet" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Authorization: Basic bG9naW46cGFzc3dvcmQ="

Requête:
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:loubet
> Authorization: Basic bG9naW46cGFzc3dvcmQ=

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: f4cc228a-4467-40b2-9779-7a1c07039010
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:55:06 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
Ne fonctionne pas, erreur 404


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Réponse:
< HTTP/2 405
< date: Thu, 29 Sep 2022 14:58:12 GMT
< content-type: text/html; charset=UTF-8
< allow: GET
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< status: 405 Method Not Allowed
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=sKwxPHlv7uSKhOjY1PwmMnJxrefmjTQ6OD01iYnOEBAQusuhMZthCgQ25QcatCoYt0DGa%2FzFGbCnpZFTp4gY%2B2oSi%2BtCRLzV6Lt8dFivE5TN97KpuPE0u%2FUE00vno4%2FDwisTVZpbe4M%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 7525935aa93c91fc-FRA
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
405: Method Not Allowed

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Réponse:
< HTTP/2 200
< date: Thu, 29 Sep 2022 15:00:06 GMT
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
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=x4AmQ79uLgk9el0e51oiHEXY2mZGp6ANAQOHF%2FXfbRDFWOhlFaupd86%2Fi7HWBoMXXqCXaTj%2BUHil4v0VfppVM7y8ZGmMuBGBxI1mVCJFJiDwqBrI0ZCszFvStllpXR4JHcJAP7KQX4Q%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75259625283d5a01-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
* Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
Réponse:
< HTTP/2 404
< date: Thu, 29 Sep 2022 15:01:13 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=ptB7sge0K34NFVytCnM%2BA3cTj0x6RFtIFWHbwVb6YGrC8ojxYhxvApSmaiwf9gC5tmwEpvToBgI49k4dCSt6d3CIeTPEB%2F8ffwy36deVr56vKc%2F2egYS2R7xsHOzsaT02ofL%2FplKGqc%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 752597c8ae8c3746-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
* Connection #0 to host demo.api-platform.com left intact
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
404: Not Found

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
Réponse:
< HTTP/2 301
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Thu, 29 Sep 2022 15:02:40 GMT
< expires: Thu, 29 Sep 2022 15:02:40 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+522; expires=Sat, 28-Sep-2024 15:02:40 GMT; path=/; domain=.google.fr; Secure
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
301: Moved Permanently
Redirection de l'URL permanente

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Solution 1: ajouter l'option -L à la commande curl
Solution 2: Utiliser la nouvelle URL dans la commande curl