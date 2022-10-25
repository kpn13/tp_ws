# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

j'ai utiliser la requette suivante : curl --header "x-student:Damene" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v

j'ai obtenue la reponse suivante :
*   Trying 46.4.105.116:443...
* TCP_NODELAY set
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
* successfully set certificate verify locations:
*   CAfile: /etc/ssl/certs/ca-certificates.crt
  CApath: /etc/ssl/certs
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:Damene
>
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4ff166f7-736e-4331-b710-6216b8f0b7b3
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:30:40 GMT
<
* Connection #0 to host webhook.site left intact

## Quel est la version du protocole utilisé par le serveur ?
la version http 1.1 est utiliser

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
on utilise le header suivvant : --header "x-student:Damene"
on on envoie le type de header et notre nom

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

On peut trouver les infos suivantes dans la reponse de la requet : 

successfully set certificate verify locations:
*   CAfile: /etc/ssl/certs/ca-certificates.crt
    CApath: /etc/ssl/certs
SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
SSL certificate verify ok.
old SSL session ID is stale, removing

on peut trouver qui a emis le certifica , la maniere de conection et sa validiter

## Quel est le code de la réponse ? Que signifie-t-il ?

code de la reponse : 
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4ff166f7-736e-4331-b710-6216b8f0b7b3
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:30:40 GMT
<

on a un code 200 se qui signifie que la requette est bonne


## Quels headers recevez vous dans la response ? Quels sont leur sens ?

GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:Damene

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:Damene" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -d "randomtesttextbrut" -v

*   Trying 46.4.105.116:443...
* TCP_NODELAY set
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
* successfully set certificate verify locations:
*   CAfile: /etc/ssl/certs/ca-certificates.crt
  CApath: /etc/ssl/certs
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:Damene
> Content-Length: 18
> Content-Type: application/x-www-form-urlencoded
>
* upload completely sent off: 18 out of 18 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 2008eccb-77b3-4251-b891-c55fac0bd11a
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:22:14 GMT
<
* Connection #0 to host webhook.site left intact

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -v --header "x-student: damene" -X POST https://webhook.site/d4ec90aa-8173-48dd -8414-6fb832ea2a26 -H 'Content-type: application/json' -d '{"login":"my_login", "password":"my_password"}'


< HTTP/1.1 200 OK < Server: nginx < Content-Type: text/plain; charset=UTF-8 < Transfer-Encoding: chunked < Vary: Accept-Encoding < X-Request-Id: 603f3cc0-1107-4c78-8de7-d43a0986a6b3 < X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 < Cache-Control: no-cache, private < Date: Thu, 29 Sep 2022 14:41:31 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
command 1 : curl -v --header "x-student: damene" -u "login:password "https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26


< HTTP/1.1 200 OK < Server: nginx < Content-Type: text/plain; charset=UTF-8 < Transfer-Encoding: chunked < Vary: Accept-Encoding < X-Request-Id: b61c3518-565b-4a00-9fc3-87728a6ff89e < X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 < Cache-Control: no-cache, private < Date: Thu, 29 Sep 2022 14:48:05 GMT

command 2 : curl -v --header "x-student: damene" -u "login:password" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"

< HTTP/1.1 200 OK < Server: nginx < Content-Type: text/plain; charset=UTF-8 < Transfer-Encoding: chunked < Vary: Accept-Encoding < X-Request-Id: 61c07f8f-8ab4-44e6-8093-118ef4de8366 < X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 < Cache-Control: no-cache, private < Date: Thu, 29 Sep 2022 14:53:33 GMT


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

cela ne fonctionne pas

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
curl --header "x-student: damene" -X PATCH https://demo.api-platform.com/top_books/1

<head>
    <meta charset="UTF-8" />
    <meta name="robots" content="noindex,nofollow,noarchive" />
    <title>An Error Occurred: Method Not Allowed</title>
    <style>body { background-color: #fff; color: #222; font: 16px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; margin: 0; }
.container { margin: 30px; max-width: 600px; }
h1 { color: #dc3545; font-size: 24px; }
h2 { font-size: 18px; }</style>
</head>

    <p>
        Something is broken. Please let us know what you were doing when this error occurred.
        We will fix it as soon as possible. Sorry for any inconvenience caused.
    </p></div>
</body>


## Quel est le code HTTP reçu ? Quel est sa signification ?
j'ai pas de code erreur mais j'ai recus sa comme erreur:  An Error Occurred: Method Not Allowed
<p>
        Something is broken. Please let us know what you were doing when this error occurred.
        We will fix it as soon as possible. Sorry for any inconvenience caused.
</p>

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
code erreur : 404 Not Found
cela signifie que qu'il a rien trouver

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
< HTTP/2 301 
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Tue, 25 Oct 2022 14:14:31 GMT
< expires: Tue, 25 Oct 2022 14:14:31 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+234; expires=Thu, 24-Oct-2024 14:14:31 GMT; path=/; domain=.google.fr; Secure
< p3p: CP="This is not a P3P policy! See g.co/p3phelp for more info."        
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>
* Connection #0 to host google.fr left intact

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
j'ai recus le code 301

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Pour Obtenir une bonne reponse on peut ajouter un -L a la fin 
je n'ai pas trouver d'autre solution