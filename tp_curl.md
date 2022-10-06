# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

Requête : ```curl --header "x-student: Camille_HOUNSA" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe```


## Quel est la version du protocole utilisé par le serveur ?

Requête : ```curl -v https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe```
<!--
le protocole utilisé est HTTP avec la version 1.1
-->

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
<!--
GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: Camille_HOUNSA
-->

* GET : C'est la méthode utilisé pour la requête
* Host : C'est le nom du domaine du serveur auquel on envoie la requête
* User-Agent : C'est la chaine de caractère permettant d'identifier formellement le navigateur qui a généré la requête. On y trouve sa version.
* Accept : Il indique le type de contenu que le client est en mesure d'accepter.

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

``` SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384```

## Quel est le code de la réponse ? Que signifie-t-il ?

``HTTP/1.1 200 OK`` il signifi que la ressource est créée

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
Requête : ``curl -X HEAD -I  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5``
<!--
HTTP/1.1 200 OK
Server: nginx
Content-Type: text/plain; charset=UTF-8
Vary: Accept-Encoding
X-Request-Id: 50901b90-0bc6-4a69-8226-09e0ff666a76
X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
Cache-Control: no-cache, private
Date: Thu, 06 Oct 2022 13:07:29 GMT
-->

* Server : Caractéristique du serveur ayant envoyé la réponse
* Content-Type : Le type de contenu du corps de la réponse
* Vary : Spécifie que l'encodoage est bien accepté
* Date : Date de début de transfert des données

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

Requête: ```curl -d "Salut, moi c'est Camille" https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5```

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
