# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : KANE_Cheikne, DIALLO_Talibe

curl --header "x-student:KANE_Cheikne, DIALLO_Talibe" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl -v -header "x-student:KANE_Cheikne, DIALLO_Talibe" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Voici la requête : 

> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.81.0
> Accept: */*
> x-student:KANE_Cheikne, DIALLO_Talibe
> 
* TLSv1.2 (IN), TLS header, Supplemental data (23):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.2 (IN), TLS header, Supplemental data (23):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
* TLSv1.2 (IN), TLS header, Supplemental data (23):
* Mark bundle as not supporting multiuse

Voici la reponse :

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4f137a12-dba8-42b2-9d08-a5ed96fb35db
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:37:23 GMT


## Quel est la version du protocole utilisé par le serveur ?

< HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

> Host: webhook.site : Le serveur que nous interrogeons
> User-Agent: curl/7.81.0 : Requete client
> Accept: */* :  
> x-student:KANE_Cheikne, DIALLO_Talibe


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

*  SSL certificate verify ok.

## Quel est le code de la réponse ? Que signifie-t-il ?

200 : Tout s'est bien passé

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< Server: nginx  ;
< Content-Type: text/plain; charset=UTF-8  : Accepte des textes,codage utlisé est UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding : Accepte d'autres types de codage
< X-Request-Id: 4f137a12-dba8-42b2-9d08-a5ed96fb35db : Identifiant de la requete
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 : Identifiant de notre site par le jeton
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:37:23 GMT : Date a laquelle il nous a retourne la reponse

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl  --header "x-student:KANE_Cheikne, DIALLO_Talibe" -H "Bonjour,veuillez recevoir ma requete" -X POST https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl --header "x-student:KANE_Cheikne, DIALLO_Talibe" -d '{"KANE":"CHEIKNE", "DIALLO":"TALIBE"}' -H "Content-Type: application/json" -X POST https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

curl --header "x-student:KANE_Cheikne, DIALLO_Talibe" -u "cheikne:talibe"  https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe
curl --header "x-student:KANE_Cheikne, DIALLO_Talibe" -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"  https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe
## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

 curl --header "x-student:KANE_Cheikne, DIALLO_Talibe" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl --header "x-student:KANE_Cheikne, DIALLO_Talibe"  -X PATCH  https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -d '{"kane":"cheikne": "diallo":"TALIBE"}'

## Quel est le code HTTP reçu ? Quel est sa signification ?

HTTP/1.1 200 OK : Effectuer avec success

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

< HTTP/2 200 
< date: Thu, 06 Oct 2022 12:36:33 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 183
< cache-control: no-cache, private
< etag: "06a23177dff31429d2a7390117fe1b2d"
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

< HTTP/2 404 
< date: Thu, 06 Oct 2022 12:39:20 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google


## Quel est le code HTTP ? Que signifie-t-il ?

curl https://demo.api-platform.com/top_books/1 : A retourne un 200 ----> tout s'est bien passe

curl https://demo.api-platform.com/top_books/9999 :  A retourne un 404 ---> Que la page n'a pas ete trouvee

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

< HTTP/2 301 
< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Thu, 06 Oct 2022 12:43:44 GMT
< expires: Thu, 06 Oct 2022 12:43:44 GMT
< cache-control: private, max-age=2592000

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

< HTTP/2 301  ---> Indique la ressource demandee a ete deplacee definitivement vers un autre emplacement.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

- On doit mettre a jour toutes les references de cette url
- Partager les nouvelles URL sur les réseaux sociaux (sur Twitter, Facebook, Google+ et les autres)
- faire des pings aux moteurs pour signaler les nouvelles URL


