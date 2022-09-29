# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 

**Requete** : 
**Reponse** : 


## Quel est la version du protocole utilisé par le serveur ?
HTTP 1.1



## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:RachdiChemseddine


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384



## Quel est le code de la réponse ? Que signifie-t-il ?
**Code** : 400
**Signification** : requete invalide.



## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9d9d1b1c-c66c-4f91-9617-6ffce9158b42
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:50:34 GMT


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl  POST "TextBrute" -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

**Requete** :  
**Reponse** : 



## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl --request POST --data '{"username":"chems","password":"123"}' -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26




## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
curl  -u "chems:123" -H "x-student:RachdiChemseddine" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26



## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

**reponse** :



## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

**reponse** : 



## Quel est le code HTTP reçu ? Quel est sa signification ?

**code** : 405
**Signification** :



## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

**reponse** :



## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

**reponse** :



## Quel est le code HTTP ? Que signifie-t-il ?

**Code** : 404
**Signification** :



## Exécuter la requête suivante et copier la réponse : curl https://google.fr

**reponse** :



## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

**Code** :
**Signification** :



## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

**solutions** :
