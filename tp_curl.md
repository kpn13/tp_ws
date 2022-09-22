??? d'ici jusqu'à ???FIN des lignes ont pu être insérées/effacées
# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -vH "x-student:EVERARD" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

réponse complète de la commande :

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
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:EVERARD
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
< X-Request-Id: 3cb67d37-90bc-409e-a14c-78d8424ef506
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:37:03 GMT
< 
* Connection #0 to host webhook.site left intact



Nous pouvons la décomposer en requête/réponse comme suivant

requête:

> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:EVERARD

réponse:

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: f6f1c5be-00ac-4207-9e9e-da06caad0e7d
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:13:42 GMT

## Quel est la version du protocole utilisé par le serveur ?
Le protocole utilisé est le protocole HTTP et la version utilisé est 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Les headers que l'on envoie dans la requête sont:
- GET: l'action a effectué avec le protocole HTTP 1.1
- Host: le nom de domaine du serveur auquel on se connecte
- User-Agent: Le nom du client qui envoie la requête
- Accept: indique le type de contenu que le client est capable de comprendre (type MIME)
- x-student: header que l'on a rajouté afin de reconnaitre la personne qui se connecte

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

Nous pouvons voir que le certificat SSL utilise la version 1.3 du protocole TLS

## Quel est le code de la réponse ? Que signifie-t-il ?

Le code de la réponse est 200 ce qui indique le succès de la requête

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
Les headers que l'on recoit dans la réponse sont:
- le protocole utilisé, sa version et le code de retour
- Server: le nom du logiciel qu'utilise le serveur
- Content-Type: le format de la réponse
- Transfert-Encoding: type d'encodage utilisé par le serveur dans la réponse
- Vary: détermine comment les en-têtes de requêtes futures sont associés pour décider si une réponse en cache peut être réutilisée plutôt que de solliciter à nouveau le serveur d'origine.
- X-Request-Id: l'identifiant (généré aléatoirement) du client qui envoie la requête
- X-Token-Id: 
- Cache-Control:
- Date: la date 

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

commande: curl -vH "x-student:EVERARD" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -d "Hello World"

requête:
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:EVERARD
> Content-Length: 11
> Content-Type: application/x-www-form-urlencoded
> 

réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 585a6af7-3b9b-473b-b1d7-5adaff480c16
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 13:22:54 GMT
< 



## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

commande: curl -vH "x-student:EVERARD" -H "Content-Type: Application/JSON" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -d "{"msg": "Hello World"}"

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

réponse:

{"@context":"\/contexts\/Book","@id":"\/books\/07dd4786-aaa7-4d08-a467-076b76f1d1b6","@type":"https:\/\/schema.org\/Book","id":"07dd4786-aaa7-4d08-a467-076b76f1d1b6","isbn":"9791891164452","title":"Cupiditate a eum natus officia laudantium recusandae aliquam.","description":"Qui vitae enim et explicabo possimus nesciunt voluptatibus. Officia fugit iste et et. Totam repellendus provident voluptatem.","author":"Percival Toy","publicationDate":"2020-01-25T00:00:00+00:00","reviews":[{"@id":"\/reviews\/2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","@type":"https:\/\/schema.org\/Review","id":"2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","body":"Qui voluptatem beatae quia accusamus et libero. Officia voluptatibus qui molestias temporibus."},{"@id":"\/reviews\/dc276e75-d6af-430d-8e50-1a4a15cd39bd","@type":"https:\/\/schema.org\/Review","id":"dc276e75-d6af-430d-8e50-1a4a15cd39bd","body":"Voluptatum vero ab ducimus sapiente consequatur explicabo. Occaecati repellat nobis doloremque enim est ipsam atque. Nihil autem expedita aut et mo* Connection #0 to host demo.api-platform.com left intact
lestiae aut sequi. Vitae quo explicabo ut corporis sapiente minima ut. Aut quae nam in ut officiis dolorum ut."},{"@id":"\/reviews\/8cf8e5d4-c4cd-48ab-abbe-868d74137647","@type":"https:\/\/schema.org\/Review","id":"8cf8e5d4-c4cd-48ab-abbe-868d74137647","body":"Earum non qui fugit consequuntur magnam. Ut sed fuga culpa quibusdam doloribus eum quis. Aut modi porro nulla quaerat. Veniam quidem in aut voluptatem. Eum laudantium aut amet debitis ut."},{"@id":"\/reviews\/25f8d916-9692-4783-8dbe-5042fa4e9bff","@type":"https:\/\/schema.org\/Review","id":"25f8d916-9692-4783-8dbe-5042fa4e9bff","body":"Natus autem est ut sunt laboriosam ex quos. Temporibus facere error voluptate odio. Dolores est aut aliquam. Commodi occaecati itaque impedit vitae nihil officia beatae."}]}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

commande: curl -X PATCH https://demo.api-platform.com/top_books/1

réponse:
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

Le code HTTP reçu est 405, ce qui signifie que nous n'avons pas la permission d'effectuer des modifications

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

réponse:
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

réponse:
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

Le code HTTP est 404, il signifie que le document n'as pas été trouvé

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

réponse:
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code HTTP est 301, il indique une redirection

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
