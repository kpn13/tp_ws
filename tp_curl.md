# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -v --header "x-student: renaud" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26
requete : GET 
réponse : 200 OK

## Quel est la version du protocole utilisé par le serveur ?
La version est HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1 -> La méthode utilisé
> Host: webhook.site -> nom de domaine du serveur sur lequel on effectue la requête
> User-Agent: curl/7.74.0 -> indique la version de curl utilisé
> Accept: */* -> le type de contenue que le client peut interpreter, ici le client peut accepter tout type
> x-student: renaud -> en tete personalisé


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Le type de SSL utilisé : ici TLSv1.3

## Quel est le code de la réponse ? Que signifie-t-il ?
le code est 200, cela signifie que la requête a reussi

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< Server: nginx                                      -> information sur le serveur
< Content-Type: text/plain; charset=UTF-8            -> indique le type de média de la ressource
< Transfer-Encoding: chunked                         ->spécifie l'encodage
< Vary: Accept-Encoding                              -> on accepte d'utiliser la réponse dans le cache
< X-Request-Id: 8393534f-3de1-4f19-b59c-3b138118a5d1 -> en tete custom, id de la requete
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26   -> id du token
< Cache-Control: no-cache, private                   -> spécifications pour le cache
< Date: Thu, 29 Sep 2022 14:09:02 GMT                -> date de la requpete


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl -d "test" -X POST https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -v

requête :
> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Length: 4
> Content-Type: application/x-www-form-urlencoded

Réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 4ccea687-b025-4484-8e54-5332db0a53be
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:44:26 GMT

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl -v -d '{"eleve":"renaud"}' -H "Content-Type: application/json" -X POST https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête:> POST /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
réponse:< HTTP/1.1 200 OK


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

1ère méthode:
curl -v -u "cerenaud:mdp" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

requête: > GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
réponse : > GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1

2ème méthode:
curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "Authorization:Basic 111" -v

requête : > GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
réponse : < HTTP/1.1 200 OK


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
curl https://demo.api-platform.com/top_books/1 -X PATCH -v

réponse :< HTTP/2 405 

## Quel est le code HTTP reçu ? Quel est sa signification ?
Code 405 : méthode non autorisée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
Erreur 404 : page non trouvée


## Exécuter la requête suivante et copier la réponse : curl https://google.fr
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
On reçoit le code 301: erreur de redirection
La page a été déplacée vers une autre URL 

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
