# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -H "x-student:QI" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501

## Quel est la version du protocole utilisé par le serveur ?
On utilise curl -v https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:QI"
Et on sait la version est 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Ici les headers dans la requete.
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.79.1
> Accept: */*
> x-student:QI
Le sens est de client a serveur web.

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
On peut voir SSL connection using TLSv1.3


## Quel est le code de la réponse ? Que signifie-t-il ?
le code est 200, ca signifie OK.


## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 255befc3-2119-4aec-8dd7-d64af767cde2
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 16:30:11 GMT

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl -d "hello" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:QI" -v
le requete est POST /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
la reponse est HTTP/1.1 200 OK


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -d '{"name":"QI"}' -H "Content-Type: application/json" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:QI" -v
la requete est POST /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
la reponse est HTTP/1.1 200 OK

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
curl -u qi:ye https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:QI" -v
la requete est GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
la reponse est HTTP/1.1 200 OK

curl https://qi:777@webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:QI" -v
la requete GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
la reponse HTTP/1.1 200 OK


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
la reponse est  HTTP/2 404

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
la reponse est  HTTP/2 405

## Quel est le code HTTP reçu ? Quel est sa signification ?
la premiere, 404: not found
la deuxieme, 405: Method Not Allowed

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
la reponse est HTTP/2 200

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
la reponse est HTTP/2 404

## Quel est le code HTTP ? Que signifie-t-il ?
 404: not found

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
< HTTP/2 301
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Tue, 25 Oct 2022 17:13:46 GMT
< expires: Tue, 25 Oct 2022 17:13:46 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+459; expires=Thu, 24-Oct-2024 17:13:46 GMT; path=/; domain=.google.fr; Secure
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
le code est 301, signifie redirection définitive. 


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
