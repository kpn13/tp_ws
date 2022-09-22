# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

J'effectue la commande suivante: 

curl -i -H "student: ANTOINE" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26


Je reçois cette réponse, le code 200 m'indique que la requête s'est bien déroulée. 

HTTP/1.1 200 OK
Server: nginx
Content-Type: text/plain; charset=UTF-8
Transfer-Encoding: chunked
Vary: Accept-Encoding
X-Request-Id: d46106c7-5f9b-477e-a699-3fc966bab234
X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
Cache-Control: no-cache, private
Date: Thu, 22 Sep 2022 12:09:57 GMT

## Quel est la version du protocole utilisé par le serveur ?

On voit que le serveur utilise la version du protocole HTTP.

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

En utilisant l'option -v de curl, il est possible d'obtenir plus d'informations au sujet de la requête.

Ici, on voit que les headers sont :

> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> student: ANTOINE


Le premier indique la méthode de protocole utilisée. En l'occurence il s'agit de la méthode GET du protocole HTTP.
Il indique aussi la version du protocole => 1.1

Le second indique le nom de l'hôte du serveur à qui nous envoyons la requête.

Le troisième donne une sorte d'identifiant de la personne qui envoie la requête. Par défaut avec curl l'user agent est: "curl/<version de curl>"

Le quatrième indique quels types (MIME) de contenus le client pourra prendre en charge. Ici, '*/*' signifie que tous les formats sont acceptés dans la réponse.

L'entête peut aussi contenir des headers 'customisés' qui sont directement créés par la personne qui émet la requête (par exemple ici le header 'student').


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

Nous pouvons obtenir ces informations à propos du certificat SSL du serveur :

* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.

On peut voir les dates de début et de fin du certificat actif. Nous pouvons bien évidemment voir si le certificat est bon ou non. 


## Quel est le code de la réponse ? Que signifie-t-il ?

HTTP/1.1 200 OK

Le code de la réponse est : 200 OK. Ce code HTTP indique que la requête n'a rencontré aucun problème durant son exécution.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

Voici les headers de la réponse:

< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Server: nginx
Server: nginx
< Content-Type: text/plain; charset=UTF-8
Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
Transfer-Encoding: chunked
< Vary: Accept-Encoding
Vary: Accept-Encoding
< X-Request-Id: 3f06fe95-301c-4544-9b5f-71a7a32330c4
X-Request-Id: 3f06fe95-301c-4544-9b5f-71a7a32330c4
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:15:23 GMT
Date: Thu, 22 Sep 2022 12:15:23 GMT

Le premier header indique le protocole utilisé et sa version => HTTP/1.1
Le protocle étant HTTP, nous recevons aussi le code HTTP indiquant comment la requête s'est déroulée.

L'header 'Server' donne des infos sur le serveur qui s'occupe de la requête.

L'header 'Content-Type' donne le type MIME du contenu renvoyé dans la réponse.

L'header 'Transfer-Encoding' donne le type d'encodage utilisé par le serveur pour envoyer la réponse.

L'header 'Vary' indique comment les en-têtes de requêtes futures sont associés pour décider si une réponse en cache peut être réutilisée plutôt que de solliciter à nouveau le serveur d'origine.

L'header 'X-Request-Id' donne l'id lié à la requête.

L'header 'X-Token-Id'  / 

L'header 'Cache-Control' contient des instructions concernant la mise en cache des informations de la réponse par les navigateurs.

L'header 'Date' indique la date.

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl -i -v -H "student: ANTOINE" -d "Bonjour monsieur"  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
* successfully set certificate verify locations:
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
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
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> student: ANTOINE
> Content-Length: 16
> Content-Type: application/x-www-form-urlencoded
> 
* upload completely sent off: 16 out of 16 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Server: nginx
Server: nginx
< Content-Type: text/plain; charset=UTF-8
Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
Transfer-Encoding: chunked
< Vary: Accept-Encoding
Vary: Accept-Encoding
< X-Request-Id: c1925a89-05e9-4493-b596-22ff815c3981
X-Request-Id: c1925a89-05e9-4493-b596-22ff815c3981
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:50:15 GMT
Date: Thu, 22 Sep 2022 12:50:15 GMT

< 
* Connection #0 to host webhook.site left intact


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl -i -v -H "student: ANTOINE" -H "Content-Type: application/json" -d "{"bonjour": "monsieur"}"  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* ALPN, offering h2
* ALPN, offering http/1.1
* successfully set certificate verify locations:
*  CAfile: /etc/ssl/certs/ca-certificates.crt
*  CApath: /etc/ssl/certs
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
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> student: ANTOINE
> Content-Type: application/json
> Content-Length: 19
> 
* upload completely sent off: 19 out of 19 bytes
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Server: nginx
Server: nginx
< Content-Type: text/plain; charset=UTF-8
Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
Transfer-Encoding: chunked
< Vary: Accept-Encoding
Vary: Accept-Encoding
< X-Request-Id: 9d8e0b52-a4f8-437b-a129-922aae34c422
X-Request-Id: 9d8e0b52-a4f8-437b-a129-922aae34c422
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 13:02:58 GMT
Date: Thu, 22 Sep 2022 13:02:58 GMT

< 
* Connection #0 to host webhook.site left intact


## Faire un appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

:/

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

Voici la réponse (au format JSON) : 

{"@context":"\/contexts\/Book","@id":"\/books\/07dd4786-aaa7-4d08-a467-076b76f1d1b6","@type":"https:\/\/schema.org\/Book","id":"07dd4786-aaa7-4d08-a467-076b76f1d1b6","isbn":"9791891164452","title":"Cupiditate a eum natus officia laudantium recusandae aliquam.","description":"Qui vitae enim et explicabo possimus nesciunt voluptatibus. Officia fugit iste et et. Totam repellendus provident voluptatem.","author":"Percival Toy","publicationDate":"2020-01-25T00:00:00+00:00","reviews":[{"@id":"\/reviews\/2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","@type":"https:\/\/schema.org\/Review","id":"2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","body":"Qui voluptatem beatae quia accusamus et libero. Officia voluptatibus qui molestias temporibus."},{"@id":"\/reviews\/dc276e75-d6af-430d-8e50-1a4a15cd39bd","@type":"https:\/\/schema.org\/Review","id":"dc276e75-d6af-430d-8e50-1a4a15cd39bd","body":"Voluptatum vero ab ducimus sapiente consequatur explicabo. Occaecati repellat nobis doloremque enim est ipsam atque. Nihil autem expedita aut et molestiae aut sequi. Vitae quo explicabo ut corporis sapiente minima ut. Aut quae nam in ut officiis dolorum ut."},{"@id":"\/reviews\/8cf8e5d4-c4cd-48ab-abbe-868d74137647","@type":"https:\/\/schema.org\/Review","id":"8cf8e5d4-c4cd-48ab-abbe-868d74137647","body":"Earum non qui fugit consequuntur magnam. Ut sed fuga culpa quibusdam doloribus eum quis. Aut modi porro nulla quaerat. Veniam quidem in aut voluptatem. Eum laudantium aut amet debitis ut."},{"@id":"\/reviews\/25f8d916-9692-4783-8dbe-5042fa4e9bff","@type":"https:\/\/schema.org\/Review","id":"25f8d916-9692-4783-8dbe-5042fa4e9bff","body":"Natus autem est ut sunt laboriosam ex quos. Temporibus facere error voluptate odio. Dolores est aut aliquam. Commodi occaecati itaque impedit vitae nihil officia beatae."}]}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Voici la réponse réceptionnée: 

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

Elle indique que le serveur ne nous permet pas d'utiliser la méthode PATH (code 403 => forbidden)

## Quel est le code HTTP reçu ? Quel est sa signification ?

Le code reçu est 403. Il indique une erreur du côté client. En l'occurrence, ce code indique que nous avons essayé d'accéder à une ressource à laquelle nous n'avons pas l'accès.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

Voilà la réponse :

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

Voici la réponse :

HTTP/2 404 
date: Thu, 22 Sep 2022 13:12:33 GMT
content-type: application/ld+json; charset=utf-8
content-length: 120
cache-control: no-cache, private
link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
status: 404 Not Found
x-content-type-options: nosniff
x-frame-options: deny
via: 1.1 google
cf-cache-status: DYNAMIC
report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=znWHIjwuNut2sboHsyKqduCrgiZefEhY0VXLgnCt62KFuNPgayYSIAL3VYzbM4rwH9yRlunFG1Drme7ekRqgyX38iovxfuqUGp9%2F4aLgISWXPwicoNf%2F2ULNFbNFbyrzn%2FOwpGeErzw%3D"}],"group":"cf-nel","max_age":604800}
nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
server: cloudflare
cf-ray: 74eb4af6fc04599b-MXP
alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

Le code HTTP est 404. Ce code indique une erreur côté client. En l'occurrence, il indique que nous avons essayé d'accéder à une ressource qui n'existe pas ou plus. 

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code reçu est 301. Il indique une redirection de la ressource. Nous avons essayé d'accéder à une ressource qui a été déplacée. On peut expliquer cette réponse par le fait qui nous n'avons pas mis 'www' dans notre requête.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.


