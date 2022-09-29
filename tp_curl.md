# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x:student:aymen" -v


## Quel est la version du protocole utilisé par le serveur ?

HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x:student:aymen

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
 SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384


## Quel est le code de la réponse ? Que signifie-t-il ?
200 OK
que la requete est traiter avec succés


## Quels headers recevez vous dans la response ? Quels sont leur sens ?


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl  -X POST -d 'hamid'  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x:student:aymen" -v 
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x:student:aymen
> Content-Length: 5
> Content-Type: application/x-www-form-urlencoded




## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl  -X POST -H "Content-Type:application/json"\ -d 'hamid'\  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x:student:aymen" -v   

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
