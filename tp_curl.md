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


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
