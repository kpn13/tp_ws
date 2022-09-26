# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: Boliandra" 

## Quel est la version du protocole utilisé par le serveur ?
 HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
 GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
 Host: webhook.site
 User-Agent: curl/7.55.1
 Accept: */*
 x-student: Boliandra

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Command: curl -v --header "x-student: Boliandra"
Nous pouvons voir qu'un certificat de type TLSv1.3 / TLS_AES_256_GCM_SHA 384 est utilisé et que ce certificat utilisé est valide pour notre demande.

## Quel est le code de la réponse ? Que signifie-t-il ?

- SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
- ALPN, server did not agree to a protocol
- Server certificate:
- subject: CN=webhook.site
- start date: Jul 30 22:07:27 2022 GMT
- expire date: Oct 28 22:07:26 2022 GMT
- subjectAltName: host "webhook.site" matched cert's "webhook.site"
- issuer: C=US; O=Let's Encrypt; CN=R3
- SSL certificate verify ok.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

- HTTP/1.1 200 OK
- Server: nginx
- Content-Type: text/plain; charset=UTF-8
- Vary: Accept-Encoding
- X-Request-Id: 2b2a5726-6bb1-4504-9a93-1b2dt235a8c9
- X-Token-Id: d4ec90aa-8173-19rt-8414-6fb832ea2a26
- Cache-Control: no-cache, private
- Date: Thu, 22 Sep 2022 12:39:51 GMT

Server - contains information about how the serverhandles requests
Content-Type - Indicates the resource`s media type
X-Request-Id and X-Token-Id - Custom header
Date - general hesder containing the date and time the message was sent
Cache-Control - a general  header specifying rules for caching in both requests and responses

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

Command: curl -d '{"x-student": "Boliandra"}' -H "content-Type: application/json" -X POST https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26
- Server: nginx
- Content-Type: text/plain; charset=UTF-8
- Transfer-Encoding: chunked
- Vary: Accept-Encoding
- X-Request-Id: af84d8af-7a40-417b-a97b-1354ee2504d9
- X-Token-Id: s3ti17bba-8173-48dd-8414-6fb832ea2a26
- Cache-Control: no-cache, private
- Date: Thu, 22 Sep 2022 13:03:47 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

Command: curl -u "login: Boliandra" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -v

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6

Command: curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6
Response:
{"@context":"\/contexts\/Book","@id":"\/books\/07dd4786-aaa7-4d08-a467-076b76f1d1b6","@type":"https:\/\/schema.org\/Book","id":"07dd4786-aaa7-4d08-a467-076b76f1d1b6","isbn":"9791891164452","title":"Cupiditate a eum natus officia laudantium recusandae aliquam.","description":"Qui vitae enim et explicabo possimus nesciunt voluptatibus. Officia fugit iste et et. Totam repellendus provident voluptatem.","author":"Percival Toy","publicationDate":"2020-01-25T00:00:00+00:00","reviews":[{"@id":"\/reviews\/2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","@type":"https:\/\/schema.org\/Review","id":"2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","body":"Qui voluptatem beatae quia accusamus et libero. Officia voluptatibus qui molestias temporibus."},{"@id":"\/reviews\/dc276e75-d6af-430d-8e50-1a4a15cd39bd","@type":"https:\/\/schema.org\/Review","id":"dc276e75-d6af-430d-8e50-1a4a15cd39bd","body":"Voluptatum vero ab ducimus sapiente consequatur explicabo. Occaecati repellat nobis doloremque enim est ipsam atque. Nihil autem expedita aut et molestiae aut sequi. Vitae quo explicabo ut corporis sapiente minima ut. Aut quae nam in ut officiis dolorum ut."},{"@id":"\/reviews\/8cf8e5d4-c4cd-48ab-abbe-868d74137647","@type":"https:\/\/schema.org\/Review","id":"8cf8e5d4-c4cd-48ab-abbe-868d74137647","body":"Earum non qui fugit consequuntur magnam. Ut sed fuga culpa quibusdam doloribus eum quis. Aut modi porro nulla quaerat. Veniam quidem in aut voluptatem. Eum laudantium aut amet debitis ut."},{"@id":"\/reviews\/25f8d916-9692-4783-8dbe-5042fa4e9bff","@type":"https:\/\/schema.org\/Review","id":"25f8d916-9692-4783-8dbe-5042fa4e9bff","body":"Natus autem est ut sunt laboriosam ex quos. Temporibus facere error voluptate odio. Dolores est aut aliquam. Commodi occaecati itaque impedit vitae nihil officia beatae."}]}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Command: curl -X PATCH https://demo.api-platform.com/top_books/1
Response:
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
L'erreur HTTP 405 indique que le navigateur Web a demandé l'accès à l'une de vos pages et que votre serveur Web a reconnu cette demande. Cependant, le serveur a rejeté la méthode HTTP spécifique qu'il utilise. Par conséquent, votre navigateur Web ne peut pas accéder à la page Web demandée.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Command: curl https://demo.api-platform.com/top_books/1
Response:
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
Command: curl https://demo.api-platform.com/top_books/9999
Response:
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
