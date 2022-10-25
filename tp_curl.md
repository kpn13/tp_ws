# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
	la requete => curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --header "x-student:El_azhar"
	pas de reponse

## Quel est la version du protocole utilisé par le serveur ?
	la requete => curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --header "x-student:El_azhar" -v
	=> HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
	> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1 => (indique qu'il a récupéré les données /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1)
	> Host: webhook.site =>(spécifie le nom de domaine du serveur)
	> User-Agent: curl/7.79.1 =>(permet aux serveurs et aux pairs du réseau d'identifier l'application permettant aux internautes et aux moteurs de recherche de parcourir le Web)
	> Accept: */* => (indique quels sont les types de contenu que le client sera capable d'interpréter)
	> x-student:El_azhar =>(pour identifier mon appel parmis ceux des autres étudiants)

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
	rien afficher sur les informations à propos du certificat SSL
	(Un certificat SSL est un fichier de données qui lie une clé cryptographique aux informations d'une organisation. Installé sur un serveur afin d'assurer une connexion sécurisée entre le serveur web et le navigateur.)

## Quel est le code de la réponse ? Que signifie-t-il ?
	Le code de statut de réponse HTTP/1.1 200 OK indique la réussite d'une requête.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
	< HTTP/1.1 200 OK
	< Server: nginx =>(Le nom du système (ou sous-système) qui gère les requêtes.)
	< Content-Type: text/plain; charset=UTF-8 =>(indique au client le type MIME (type Multipurpose Internet Mail Extensions, indique la nature et le format d'un document.) de la ressource ou des données.)
	< Transfer-Encoding: chunked =>(la forme de codage utilisée pour transférer en toute sécurité le corps de la charge utile à l'utilisateur. => chunked : Les données sont envoyées dans une série de blocs. )
	< Vary: Accept-Encoding =>(détermine comment les en-têtes de requêtes futures sont associés pour décider si une réponse en cache peut être réutilisée plutôt que de solliciter à nouveau le serveur d'origine.)
	< X-Request-Id: f96fc5f4-fbf5-4ed5-9aa2-47b3260b1974 =>(le serveur a reçu l'identifiant f96fc5f4-fbf5-4ed5-9aa2-47b3260b1974 qui est généré (au hasard) par le client)
	< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5 =>(l'API-jeton du client reçu par le serveur)
	< Cache-Control: no-cache, private =>(contient des directives, dans les requêtes et dans les réponses, pour contrôler la mise en cache dans les navigateurs et caches partagées)
	< Date: Thu, 06 Oct 2022 14:03:13 GMT =>(contient la date et l’heure auxquelles le message a été généré)

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
	curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --header "x-student:El_azhar" -v --data "bonjour"

*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* schannel: ALPN, offering http/1.1
* ALPN, server did not agree to a protocol
> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.79.1
> Accept: */*
> x-student:El_azhar
> Content-Length: 7
> Content-Type: application/x-www-form-urlencoded
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 18e7b857-231f-4dc4-8114-0df3686accaf
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:31:18 GMT
<
* Connection #0 to host webhook.site left intact

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
	curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --header "x-student:El_azhar" -T C:\Users\elazh\Downloads\auteurs.json -v

*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* schannel: ALPN, offering http/1.1
* ALPN, server did not agree to a protocol
> PUT /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.79.1
> Accept: */*
> x-student:El_azhar
> Content-Length: 1752
> Expect: 100-continue
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 100 Continue
* We are completely uploaded and fine
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: ed5cd94a-b0ca-49ab-8f66-e3fb7608e239
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:33:32 GMT
<
* Connection #0 to host webhook.site left intact

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
	Méthode 1 => curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --header "x-student:El_azhar" -v -u "hanae"

Enter host password for user 'hanae':
*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* schannel: ALPN, offering http/1.1
* ALPN, server did not agree to a protocol
* Server auth using Basic with user 'hanae'
> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> Authorization: Basic aGFuYWU6aGFuYWU=
> User-Agent: curl/7.79.1
> Accept: */*
> x-student:El_azhar
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4016e779-a7b1-4906-aa68-7e5aaae50313
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:35:19 GMT
<
* Connection #0 to host webhook.site left intact

	Méthode 2 =>curl https://webhook.site/7d0b0a62-c6ab-407a-a613-67bdf9560dbb --header "x-student:El_azhar" -v -H "Authorization: Bearer hanae"
*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* schannel: ALPN, offering http/1.1
* ALPN, server did not agree to a protocol
> GET /7d0b0a62-c6ab-407a-a613-67bdf9560dbb HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.79.1
> Accept: */*
> x-student:El_azhar
> Authorization: Bearer hanae
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: efae3493-bb4b-4bc9-8bec-b3ceeb43befc
< X-Token-Id: 7d0b0a62-c6ab-407a-a613-67bdf9560dbb
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 15:23:53 GMT
<
* Connection #0 to host webhook.site left intact

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
	curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
	(La méthode PATCH d'une requête HTTP applique des modifications partielles à une ressource.)
	=>curl https://demo.api-platform.com/top_books/1 -X PATCH
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
une erreur HTTP 405, il est causée lorsqu’une méthode HTTP n’est pas autorisée par un serveur web pour une URL demandée. (la methode PATCH)

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
	curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
	curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr
	=>curl https://google.fr
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
un code html qui indique qu'il faut se rederiger vers un autre url
=>Le code Redirection 301, aussi appelé redirection web ou redirection permanente, indique que le contenu d'une page web ou d'un dossier en ligne n'est plus disponible à l'URL renseignée

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
