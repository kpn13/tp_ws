# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
Commande:

curl --header "x-student:PEUCHLESTRADE" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Obtenu:

- Trying 46.4.105.116:443...
- Connected to webhook.site (46.4.105.116) port 443 (#0)
- schannel: disabled automatic use of client certificate
- ALPN: offers http/1.1
- ALPN: server did not agree on a protocol. Uses default.
  > GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
  > Host: webhook.site
  > User-Agent: curl/7.83.1
  > Accept: _/_
  > x-student:PEUCHLESTRADE
- Mark bundle as not supporting multiuse
  < HTTP/1.1 200 OK
  < Server: nginx
  < Content-Type: text/plain; charset=UTF-8
  < Transfer-Encoding: chunked
  < Vary: Accept-Encoding
  < X-Request-Id: bea33b63-1514-4371-a4fa-48264ea60d45
  < X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
  < Cache-Control: no-cache, private
  < Date: Tue, 04 Oct 2022 14:21:34 GMT
  <
- Connection #0 to host webhook.site left intact

## Quel est la version du protocole utilisé par le serveur ?
La version du protocole HTTP utilisée par le serveur est 1.1.

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
On envoit les headers GET (c'est la méthode appliquée à la requête), /d4ec90aa-8173-48dd-8414-6fb832ea2a26 (c'est l'URI) et HTTP/1.1 (qui est la version du protocole utilisé).

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
On peut trouver le type du cryptage, avec quelle méthode il a été réalisé, sa date d'émission et sa date d'expiration, ainsi que l'autorité de confiance qui l'a délivré.

## Quel est le code de la réponse ? Que signifie-t-il ?
Le code de la réponse reçue est "200", cela signifie que tout s'est bien passé.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

On reçoit la version du protocole utilisé (HTTP.1.1), le code de retour (200) ainsi que la signification du code de retour (OK).

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

Commande :
curl -v --header "x-student:PEUCHLESTRADE" --data "data" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Obtenu:

Requête:

> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: _/_
> x-student:PEUCHLESTRADE
> Content-Length: 4
> Content-Type: application/x-www-form-urlencoded

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 1e4380d0-b98e-456d-b09a-7cc0009b2899
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:59:10 GMT
<

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

Commande:
curl -v --header "x-student:PEUCHLESTRADE" -X POST https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H 'Content-type: application/json' -d '{"login":"my_login", "password":"my_password"}'

Obtenu:

Requête:

> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: _/_
> x-student:PEUCHLESTRADE
> Content-Length: 17
> Content-Type: application/x-www-form-urlencoded

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9de6f5f1-d005-482c-9cbd-6c56fd49ed11
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:10:28 GMT
<

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois

Méthode 1:

Commande:
curl -v --header "x-student:PEUCHLESTRADE" -u "login:password" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Obtenu:

Requête:

> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> Authorization: Basic bG9naW46cGFzc3dvcmQ=
> User-Agent: curl/7.83.1
> Accept: _/_
> x-student:PEUCHLESTRADE

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: fd01ad7a-256e-4b9a-b60d-adfa93c072bf
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:13:01 GMT
<

Méthode 2:

Commande :
curl -v --header "x-student:PEUCHLESTRADE" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"

Obtenu:

Requête:

> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: _/_
> x-student:PEUCHLESTRADE
> Authorization: Basic bG9naW46cGFzc3dvcmQ

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 0a526eef-75e1-47a4-a550-470b8db802e8
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:14:24 GMT

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6

Commande:
curl -v --header "x-student:PEUCHLESTRADE" -X GET https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6

Obtenu:

Requête:

> GET /books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 HTTP/1.1
> Host: demo.api-platform.com
> User-Agent: curl/7.83.1
> Accept: _/_
> x-student:PEUCHLESTRADE

Réponse:
< HTTP/1.1 404 Not Found
< Date: Tue, 04 Oct 2022 15:18:07 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 120
< Connection: keep-alive
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< Permissions-Policy: browsing-topics=()
< Status: 404 Not Found
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=t4XWwZfQlKAEquck%2FibHr5nWUAfL4Jjs3MOOIkfY8q%2FDpwmlGXvRPonqbzakyhAN7StmdDqyPnuPIxZZAYqG7DlK0rHSfctsJnhBIivp3qp1495XXC4Rc2vS4EyQ9A7Nyz9fe1msbTU%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 754ee366fcabbbcb-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}\* Connection #0 to host demo.api-platform.com left intact

## Exécuter la commande suivante avec la méthode PATCH puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Commande:
curl -v --header "x-student:PEUCHLESTRADE" -X PATCH https://demo.api-platform.com/top_books/1

Obtenu:

Requête:

> PATCH /top*books/1 HTTP/1.1
> Host: demo.api-platform.com
> User-Agent: curl/7.83.1
> Accept: */\_
> x-student:PEUCHLESTRADE

Réponse:
< HTTP/1.1 405 Method Not Allowed
< Date: Tue, 04 Oct 2022 15:19:52 GMT
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Connection: keep-alive
< Allow: GET
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Permissions-Policy: browsing-topics=()
< Status: 405 Method Not Allowed
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=e1g7wzABJ62TtYlTcNHCtslqO3drfB75Y0Y093zhd2X6HhrAB5j8M8SPF3OFX4qs4AIR6Ap%2FsDGQu54EQqXLOda%2BVHTjM7ZBbNo%2Bh5BWyViKf%2BfpXTDp%2BYQolUvWkmhIWVAb1kVO6Zs%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 754ee5f879ffbb4a-FRA
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
</html>* Connection #0 to host demo.api-platform.com left intact

## Quel est le code HTTP reçu ? Quel est sa signification ?
Le code HTTP reçu est "405 Method Not Allowed". Les erreurs HTTP 405 sont causées lorsqu'une méthode HTTP n'est pas autorisée par un serveur web pour une URL demandée.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Réponse:
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

Réponse:
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
Le code HTTP reçu est "404 Not Found". Dans le World Wide Web, l’erreur 404 signale que la ressource demandée, généralement une page Web, n'a pas été trouvée.

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

Réponse :

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
Le code HTTP reçu est "301 Moved Permanently". HTTP 301 Moved Permanently est un code de réponse HTTP qui est utilisé pour une redirection d'URL permanente, c'est-à-dire, pour indiquer que les liens actuels ou les enregistrements qui utilisent l'URL pour lesquels il a été recu doivent être modifiés.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Commande 1:
curl -v -L --post301 https://www.google.fr

On peut dire à Curl de ne pas changer la méthode de requête POST pour GET.

Commande 2:
curl -iL --max-redirs 1 https://www.google.fr

Ici on limite le nombre maximum de redirection que peut réaliser Curl.
