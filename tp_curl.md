# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

commande : curl -v  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student: soufiane_CHAIEB"
requete : GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5
reponse : HTTP/1.1 200 OK
        < Server: nginx
        < Content-Type: text/plain; charset=UTF-8
        < Transfer-Encoding: chunked
        < Vary: Accept-Encoding
        < X-Request-Id: 6e757534-2439-4cad-a418-8a944c653c30
        < X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
        < Cache-Control: no-cache, private
        < Date: Thu, 06 Oct 2022 14:01:41 GMT

## Quel est la version du protocole utilisé par le serveur ?

version : HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

Host: spécifie le nom de domaine du serveur

User-Agent: une chaine de caracteres envoyée aux serveur et qui lui permet d'identifier l'agent utilisateur(application) et sa version. 

Accept:  indique quels sont les types de contenu.

x-student: HTTP header qui permet de passer des données supplimentaires entre le client et le serveur.
 

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

la version : TLSv1.3

## Quel est le code de la réponse ? Que signifie-t-il ?

200 : tout est bien passé.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< Server: spécifie le nom du logiciel utilisé par le serveur.
< Content-Type: indique au client le type de contenu renvoyé.
< Transfer-Encoding: définit le codage du contenu du message envoyé au client.
< Vary: détermine comment les en-têtes de requêtes futures sont associés pour décider si une réponse en cache peut être réutilisée plutôt que de solliciter à nouveau le serveur d'origine.
< X-Request-Id: permet au client de creer un id unique pour identifier ses requetes.
< X-Token-Id: permet de savoir si le client a été authentifié.
< Cache-Control:contient des directives pour contrôler la mise en cache dans les navigateurs. 
< Date: ontient la date et l'heure du message.


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

requete : curl -X POST -H "Content-Type: text/plain" --data "hello world !" https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -v

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

requete : curl -X POST https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H 'Content-Type: application/json' -d '{"prenom":"soufiane","nom":"chaieb"}' -v



## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

curl --user "soufiane" https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

code réponse : 404 

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

code réponse : 405 Method Not Allowed

## Quel est le code HTTP reçu ? Quel est sa signification ?

405 : indique que la méthode utilisée pour la requête est connue du serveur mais qu'elle n'est pas supportée par la ressource ciblée.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
code réponse : 200 


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

code réponse : 404 

## Quel est le code HTTP ? Que signifie-t-il ?

404 : .ndique qu'un serveur ne peut pas trouver la ressource demandée.

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
< HTTP/2 301 
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Thu, 06 Oct 2022 15:32:56 GMT
< expires: Thu, 06 Oct 2022 15:32:56 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+618; expires=Sat, 05-Oct-2024 15:32:56 GMT; path=/; domain=.google.fr; Secure
< p3p: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

301 : Le serveur web renverra au client qui demande la page, un code de réponse HTTP 301 si la ressource demandée a été définitivement déplacée vers une nouvelle URL. En renvoyant le code de réponse 301, le serveur web redirige toutes les requêtes d’une certaine adresse URL source vers la nouvelle adresse URL cible définie.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
