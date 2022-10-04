# TP curl - comprendre les requêtes et les réponses HTTP
# Name: UONG TRI MINH

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
	- request : curl --header "x-student: UONG" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -I
	- reponse :
HTTP/1.1 200 OK
Server: nginx
Content-Type: text/plain; charset=UTF-8
Vary: Accept-Encoding
X-Request-Id: 2c8e479d-7b79-450f-8200-ad0dd13ee3ad
X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
Cache-Control: no-cache, private
Date: Tue, 04 Oct 2022 14:20:57 GMT

## Quel est la version du protocole utilisé par le serveur ?
HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
x-student: UONG
meaning: addition information for the request. here in header, we added attribute x-student, the value is the name of stutdent

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
request: curl --header "x-student: UONG" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v

Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.


## Quel est le code de la réponse ? Que signifie-t-il ?
code : 200
meaning: success

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK        --> protocol and response's code
< Server: nginx          --> type of web server 
< Content-Type: text/plain; charset=UTF-8  --> type of response and encoding type
< Transfer-Encoding: chunked  --> form of enconding to transfer the body
< Vary: Accept-Encoding
< X-Request-Id: be1a8350-f551-4ec3-bfad-90664d577cfe  --> request id
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe    --> token
< Cache-Control: no-cache, private    --> instruction for caching
< Date: Tue, 04 Oct 2022 14:29:14 GMT    --> time of response


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
command: 
	curl --header "x-student: UONG" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -X POST -H "Content-Type: text/plain" --data "I'm Uong Tri Minh"  -v

request:
	-header : 
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: UONG
> Content-Type: text/plain
> Content-Length: 17

	- body: 'I'm Uong Tri Minh'

response:
	-header:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 5ff29e15-525b-48bf-a92d-e27da23753f4
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:58:14 GMT
	-body: 

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
command: 
	curl --header "x-student: UONG" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -X POST -H "Content-Type: application/json" --data '{"name":"Minh"}'  -v

request:
	-header:
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: UONG
> Content-Type: application/json
> Content-Length: 15

	-body : {"name":"Minh"}

response:
	-header: 
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 415803a3-6f00-44e6-b8a1-8ba73b2c66e2
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:03:31 GMT

	-body:

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

curl --header "x-student: UONG" https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6


response: 
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

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
code : 405
meaning: PATH method is not allowed in this api url

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
code: 404
meaning: resource not foud

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

code: 301
meaning: request is redirected

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
