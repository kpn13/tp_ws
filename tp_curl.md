# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 

 Pour aller sur le site on utilise la commande : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

Pour rajouter le header : curl --header "x-student: Nom_Prenom" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

Ou on peut faire les deux questions avec une seule requete : curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student: Nom_Prenom" -v. La reponse qu'on a c'est : 
** Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server did not agree on a protocol. Uses default.
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> x-student: Megi_Balliu
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 3c053785-650c-4443-8990-55628c3f180d
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:43:49 GMT
<
* Connection #0 to host webhook.site left intact**

## Quel est la version du protocole utilisé par le serveur ?

curl --version nous donne la version utilisé et aussi les protocoles

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?


## Quel est le code de la réponse ? Que signifie-t-il ?


## Quels headers recevez vous dans la response ? Quels sont leur sens ?


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
