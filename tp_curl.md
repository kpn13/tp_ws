# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

command  : curl -v -H MULLER https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26
request  : 
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.64.0
> Accept: */*
> x-student: muller

response :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: b01ca976-5905-40d4-829d-4ac252b397db
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:06:41 GMT

## Quel est la version du protocole utilisé par le serveur ?

HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

GET : Méthode appliquée à la requête
/d4ec90aa-8173-48dd-8414-6fb832ea2a26 : URI
HTTP/1.1 : version du protocole utilisé

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

on peut trouver le cryptage utilisé (TLS1.3) et la méthode de cryptage (AES_256_GCM_SHA_384)
on peut également trouve la date de mise en place du certificat ainsi que sa date d'expiration, mais aussi l'autorité de confiance qui l'a délivré, et enfin, sa validité

## Quel est le code de la réponse ? Que signifie-t-il ?

code de réponse : 200
cela signifie que tout s'est bien passé

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

HTTP/1.1 : version du protocole utilisé
200 : code de retour
OK : signification du code de retour

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

command  : curl -v --header "x-student: muller" --data "bonjour monde" https://webhook.site/d4e
c90aa-8173-48dd-8414-6fb832ea2a26

request  : 
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.64.0
> Accept: */*
> x-student: muller
> Content-Length: 13
> Content-Type: application/x-www-form-urlencoded

response : 
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: a3ef1023-7621-443b-b7c9-172678ac8843
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:37:54 GMT

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

command  : 
curl -v --header "x-student: muller" -X POST https://webhook.site/d4ec90aa-8173-48dd
-8414-6fb832ea2a26 -H 'Content-type: application/json' -d '{"login":"my_login", "password":"my_password"}'

request  : 
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.64.0
> Accept: */*
> x-student: muller
> Content-type: application/json
> Content-Length: 46

response :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 603f3cc0-1107-4c78-8de7-d43a0986a6b3
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:41:31 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

command 1 : curl -v --header "x-student: muller" -u "login:password" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26                        

request 1 :
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> Authorization: Basic bG9naW46cGFzc3dvcmQ=
> User-Agent: curl/7.64.0
> Accept: */*
> x-student: muller

response 1 :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: b61c3518-565b-4a00-9fc3-87728a6ff89e
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:48:05 GMT

command 2  : curl -v --header "x-student: muller" -u "login:password" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"

request 2  :
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.64.0
> Accept: */*
> x-student: muller
> Authorization: Basic bG9naW46cGFzc3dvcmQ

response 2 :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 61c07f8f-8ab4-44e6-8093-118ef4de8366
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:53:33 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

ne fonctionne pas

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

command : curl --header "x-student: muller" -X PATCH https://demo.api-platform.com/top_books/1

response : 
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

le code reçu est 405
il signifie que la méthode PATCH n'est pas authorisée (Method not allowed)

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

response :
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

response :
< HTTP/2 404
< date: Thu, 29 Sep 2022 14:58:42 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=uZ1JEaZ3QKWXNcb49WCeZl8vaGBZg6Zudi9TLowTW3n22Pyuf7hFkKBF42sMoLwMQL39gLsa2NzQx6rQD7JLUBGn%2BKlSF%2FSLgEnOnUfwo66Dmd%2BglDztHEN40WEJg%2B36FJiwOqOjWdY%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 752594155c1783ac-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

## Quel est le code HTTP ? Que signifie-t-il ?

code : 404
signification : not found

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

< HTTP/2 301
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Thu, 29 Sep 2022 15:00:27 GMT
< expires: Thu, 29 Sep 2022 15:00:27 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+212; expires=Sat, 28-Sep-2024 15:00:27 GMT; path=/; domain=.google.fr; Secure
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

code : 301 (Moved Permanently)
indique une redirection d'URL permanente


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Solution 1 : ajouter l'option -L en fin de requête (on obtient un code 200)