# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 


Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
La commande curl : ```curl --header "x-student: Megi_Balliu" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26```

La reponse : Il n'y a pas de reponse. Cette commande est juste censé ajouter un header avec notre nom, pour nous identifier. Le fait qu'il n'y ait pas d'erreur signifie que ca c'est bien passé.

## Quel est la version du protocole utilisé par le serveur ?
La commande : ```curl -v  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26```
Reponse : La version du protocole utilisé par le serveur est : HTTP/1.1
``
    * ALPN: offers http/1.1    
``
## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

``
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
    > Host: webhook.site
    > User-Agent: curl/7.83.1
    > Accept: */* 
``
Ce sont les headers que l'on envoie dans la requete. Ces headers contiennent plus d'informations sur le client, ou au sujet de ce qu'on cherche (avec GET)

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Vu que je travaille actuellement sous Windows, on ne me donne pas des informations par rapport au certeficat SSL. Mais normalement la commande pour trouver ces informations c'est 
`` curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v -i ``
Et la reponse que moi j'ai avec cette commande c'est : 
`` 
*   Trying 46.4.105.116:443...
    * Connected to webhook.site (46.4.105.116) port 443 (#0)
    * schannel: disabled automatic use of client certificate
    * ALPN: offers http/1.1
    * ALPN: server did not agree on a protocol. Uses default.
    > GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
    > Host: webhook.site
    > User-Agent: curl/7.83.1
    > Accept: */*
    >
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
    < X-Request-Id: 8e0e2c04-aeef-4452-a06a-8da9fd52529c
    X-Request-Id: 8e0e2c04-aeef-4452-a06a-8da9fd52529c
    < X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
    X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
    < Cache-Control: no-cache, private
    Cache-Control: no-cache, private
    < Date: Thu, 06 Oct 2022 12:19:17 GMT
    Date: Thu, 06 Oct 2022 12:19:17 GMT

    <
    * Connection #0 to host webhook.site left intact
``

## Quel est le code de la réponse ? Que signifie-t-il ?

200 OK - la famille de 200 dans la reponse c'est facon de te dire que tout c'est bien passé avec la requete que tu viens d'envoyer.


## Quels headers recevez vous dans la response ? Quels sont leur sens ?
``
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9b33d89a-2936-4e07-91dd-b613094809f0
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 12:34:34 GMT
<
* Connection #0 to host webhook.site left intact 
``

Date - header qui montre quand le message est envoyé 
Content-type :  indique au client le type de contenu réellement renvoyé
Cache-Control : un header qui va dire ce qu'on doit "catch" dans la reponse et dans la requete

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
la requete : ``curl -d "Megi Balliu 1ere année de master" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe ``

la reponse : Il n'y a pas de reponse, donc a priori c'est que ca a marché.

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

 ``curl -d "{'nom': 'balliu', 'prenom': 'megi'}" -H "Content-Type: application/json" -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501``

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

1ere Methode : 
    la commande : 
        ``curl -u megi:password https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501``
    Pas de reponse
    
    Si on rajoute -v a la fin de la commande on a :
    la requete : GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
    la reponse : HTTP/1.1 200 OK


2eme methode : 
    la commande : 
        ``curl -u megi:password https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "megi:password" -v``
    la requete : GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
    la reponse : HTTP/1.1 200 OK

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

La commande : ``curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6``

La reponse : {"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

La commande : ``curl -X PATCH https://demo.api-platform.com/top_books/1``

La reponse : 
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
Le code HTTP recu cest 405 qui fait partie des erreurs coté client. Plus precisement 405 cest que la methode n'est pas disponible. Par conséquent, le navigateur Web ne peut pas accéder à la page Web.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
Reponse ``{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}``

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
Reponse : ``{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}``

## Quel est le code HTTP ? Que signifie-t-il ?
Reponse : ``HTTP/1.1 404 Not Found``
Code reponse HTTP 404, ca veut dire que c'est introuvable ou que ca n'existe pas

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
La reponse : ``<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>``


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
Le code reponse HTTP recu c'est 301 qui fait partie de la famille des 300(redirect). Plus precisement 301 c'est un redirect definitive, indique que la ressource a définitivement été déplacée


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
Une solution c'est d'utiliser correctement le slash en fin de ligne. Si on a pas de regles de réécriture il existent possiblement 8 version d'une page. Pour resoudre ce probleme, faut ajouter des regles de réécriture au fichier .htaccess. Vu que les regles ne sont pas toujours ecrit correctement ca peut entrainer des problemes

Une autre solution est de mettre en place un acces direct aux ressources non HTML. 
Toutes les ressources non HTML doivent etre accessibles directement avant d'etre affichées a l'utilisateur. Il peut etre utile de conserver les images de notre page de renvoi dans la base de données plutot que d'avoir recours a des liens qui amenent vers des images stock.
