# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:DODEMAN" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe
Réponse :
HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9b7dd6eb-f2bb-4c1e-85b9-f9f0bcb5fa9b
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:19:46 GMT
<
* Connection #0 to host webhook.site left intact

## Quel est la version du protocole utilisé par le serveur ?
HTTP/1.1 

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Header envoyés :
< x-student:DODEMAN -> les header à apporter avec la réponse 
< -v -> apporte beaucoup d'informations 

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
On peut trouver qu'il se connecte en utilisant TLSv1.3 
On peut trouver son certificat et qu'il est vérifié 

## Quel est le code de la réponse ? Que signifie-t-il ?
Le code est 200 OK. Il signifie que la requête est réussie. 

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
Status Line : 
< HTTP/1.1 200 OK 
< Date: Tue, 04 Oct 2022 14:19:46 GMT

Response header :
< Server: nginx

Entity header : 
< Content-Type: text/plain; charset=UTF-8

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:DODEMAN" -v --data "texte_brut" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN
> Content-Length: 10
> Content-Type: application/x-www-form-urlencoded

Réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: c5b8af76-7ebb-4bad-84cd-d4483a3f6fc5
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:47:51 GMT
<
* Connection #0 to host webhook.site left intact

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:DODEMAN" -v -X POST https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 
-H "Content-Type: application/json" -d '{"login":"my_login","password":"my_password"}'

Requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:DODEMAN
> Content-Type: application/json
> Content-Length: 45

Réponse : 
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: fff56757-090a-4b47-874c-21a8e2ca5d63
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:17:26 GMT

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
