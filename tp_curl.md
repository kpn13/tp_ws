# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

$ curl -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student:MOUNA"


la requete : GET



la réponse : succès (200)



## Quel est la version du protocole utilisé par le serveur ? 
curl -i --header "x-student:MOUNA"

HTTP version : 1.1


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:MOUNA
> 

Sens : header customisés 


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
SSL certificate verify ok.

A propos du certificat SSL: utilise TLSv1.3 / TLS_AES_256_GCM_SHA384 et le certificat est valide


## Quel est le code de la réponse ? Que signifie-t-il ?
code d'erreur : 200
signification : succes

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 125d4f7f-65b6-472f-98d9-caf00f95e9d4
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:50:52 GMT
< 

Sens : la requete a été executé avec succes

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --request POST --data "this is mon text brut" -H "x-student:MOUNA" -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

la requete : POST
la reponse : 200 OK



## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse



## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
curl -u "login:MOUNA" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -v
requete : GET
reponse : succes 200


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
Skip : renvoit page not found

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
