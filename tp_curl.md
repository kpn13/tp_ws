# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

$ curl --header "x-student: SABRA" -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN: offers h2
* ALPN: offers http/1.1
*  CAfile: C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
*  CApath: none
} [5 bytes data]
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
} [512 bytes data]
* TLSv1.3 (IN), TLS handshake, Server hello (2):
{ [122 bytes data]
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
{ [10 bytes data]
* TLSv1.3 (IN), TLS handshake, Certificate (11):
{ [4082 bytes data]
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
{ [264 bytes data]
* TLSv1.3 (IN), TLS handshake, Finished (20):
{ [52 bytes data]
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
} [1 bytes data]
* TLSv1.3 (OUT), TLS handshake, Finished (20):
} [52 bytes data]
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN: server did not agree on a protocol. Uses default.
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
} [5 bytes data]
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.84.0
> Accept: */*
> x-student: SABRA
>
{ [5 bytes data]
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
{ [249 bytes data]
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
{ [249 bytes data]
* old SSL session ID is stale, removing
{ [5 bytes data]
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: f8aedac3-c064-4200-81bd-ab1d2a114229
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:17:48 GMT
<
{ [5 bytes data]
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host webhook.site left intact"

## Quel est la version du protocole utilisé par le serveur ?

HTTP/1.1. Donc 1.1.

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1        La méthode du protocol, le protocol et sa version.
> Host: webhook.site                                        Le nom du domaine du serveur à qui on a envoyé la requête.
> User-Agent: curl/7.84.0                                   Identification du navigateur qui a généré la requête.
> Accept: */*                                               Indique le type de contenu accepter.
> x-student: SABRA                                          Le custom header envoyer dans la requête.

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384

## Quel est le code de la réponse ? Que signifie-t-il ?

200. Il signifie que la requete est accepter.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< HTTP/1.1 200 OK                                       Le protocol et sa version, le code de la réponse.
< Server: nginx                                         Le nom du serveur qui a prix la requête.
< Content-Type: text/plain; charset=UTF-8               Le type de contenu, ici c'est plaintext.
< Transfer-Encoding: chunked                            Le type d'encoding utiliser pour transferer le "payload body" au utilisateur.
< Vary: Accept-Encoding                                 Décris les partis du message du requête qui influence le contenu de la réponse. Accept-Encoding permet au cache de servir different versions cached de la page.
< X-Request-Id: f8aedac3-c064-4200-81bd-ab1d2a114229    L'identifiant de la requête.
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26      L'identifiant du token.
< Cache-Control: no-cache, private                      Indique au cache du serveur s’il doit recharger la page à chaque reprise ou suivant un délai précis.
< Date: Thu, 29 Sep 2022 14:17:48 GMT                   La date du reponse.


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

$ curl --header "Content-Type: text/plain" -d "Hello World!" "https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    12    0     0  100    12      0     15 --:--:-- --:--:-- --:--:--    15

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

$ curl -H "Content-Type: application/json" -d '{"CourseID": 1, "Name": "Middleware"}' "https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    37    0     0  100    37      0     45 --:--:-- --:--:-- --:--:--    45

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

Methode 1:

$ curl -u "login:password" "https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0

---------------------------------------------------------------------------------------------------------------------------------------------------------------

Methode 2:

$ curl -H "Authorization: Basic bG9naW46cGFzc3dvcmQ" "https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:--  0:00:01 --:--:--     0

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

$ curl -X GET https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   120  100   120    0     0    438      0 --:--:-- --:--:-- --:--:--   439{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

Donc la réponse est 404 NOT FOUND.

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

$ curl -X PATCH https://demo.api-platform.com/top_books/1
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   825    0   825    0     0   3023      0 --:--:-- --:--:-- --:--:--  3033<!DOCTYPE html>
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

Donc la réponse est 405 Method Not Allowed.

## Quel est le code HTTP reçu ? Quel est sa signification ?

Le code HTTP reçu est 405, c'est-à-dire que la méthode utilisée est connue, mais n'est pas permis ou n'est pas supporté.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

$ curl https://demo.api-platform.com/top_books/1
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   183  100   183    0     0    994      0 --:--:-- --:--:-- --:--:--  1000{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

Comme on a reçu de data, donc la réponse est 200 OK.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

$ curl https://demo.api-platform.com/top_books/9999
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   120  100   120    0     0    783      0 --:--:-- --:--:-- --:--:--   789{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

Comme c'est Not Found, donc la réponse est 404 NOT FOUND.

## Quel est le code HTTP ? Que signifie-t-il ?

Le code est 404, c'est-à-dire que le serveur n'arrive pas à trouver ressource demandée.

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

$ curl https://google.fr
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   219  100   219    0     0   1251      0 --:--:-- --:--:-- --:--:--  1258<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

Donc la réponse est 301 Moved Permanently.

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code est 301, c'est-à-dire que la ressource demandée a été déplacée définitivement à l'URL référencé dans le header.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

1: Fait attention et vérifie que l'URL est valide avant l'utiliser dans des requêtes.
2: Utiliser l'option -L pour forcer curl à faire la redirection à l'URL référencé.