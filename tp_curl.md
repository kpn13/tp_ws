# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H"x-student: LAMIA_BOURIAH" -v



## Quel est la version du protocole utilisé par le serveur ?

curl --version
curl 7.74.0


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
x-student: LAMIA_BOURIAH ==> le header qu'on a mit.
subject: CN=webhook.site ==> le nom du site 
subjectAltName: host "webhook.site" matched cert's "webhook.site" ==> subjectAltName specifies additional subject identities





## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
curl  https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v -i
La période de validité
L’autorité de certification (AC) émettrice
L’objet (le domaine pour lequel le certificat est émis et suivant le type de certificat, des informations permettant d’identifier la société qui exploite le site)

Le contenu du certificat comprend également des éléments techniques comme :

L’utilisation de la clé
Des informations sur la liste de révocation des certificats (LRC)
Les algorithmes de signature et de hachage derrière le chiffrement


## Quel est le code de la réponse ? Que signifie-t-il ?
200 success


## Quels headers recevez vous dans la response ? Quels sont leur sens ?
curl -D - https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 

Tous les en-têtes apparaissant dans une réponse ne sont pas des en-têtes de réponse. Par exemple, l'en-tête Content-Length est un en-tête d'entité faisant référence à la taille du corps du message de requête. Cependant, ces requêtes d'entité sont généralement appelées en-têtes de réponses dans un tel contexte.



## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl -d " je ne suis qu'a ma deuxième question au bout de deux heures :) " https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5




## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -X POST https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "Content-Type : application/json" -d '{"login": "lamia", "pass":"mypass"}'



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
