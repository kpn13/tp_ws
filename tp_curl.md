# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl -H "x-student: Combettes" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe


## Quel est la version du protocole utilisé par le serveur ?
HTTP/1.1 


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: Combettes
> 

get : type de requête 
host : nom du site
user-agent : "outil" de requête et version
Accpet: Acceptation
x-student: Combettes c'est mon -H

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.


## Quel est le code de la réponse ? Que signifie-t-il ?
200

Le code de statut de réponse HTTP 200 OK indique la réussite d'une requête. Une réponse 200 peut être mise en cache par défaut.


## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK    -> version et code de retour
< Server: nginx         -> type de serveur
< Content-Type: text/plain; charset=UTF-8   -> type de réponse (ici pas de HTML)
< Transfer-Encoding: chunked            -> uf je sais pas
< Vary: Accept-Encoding         -> pareil
< X-Request-Id: f7d2695c-c468-4b74-ad42-0646e187dc81        -> id de ma requête
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe          -> id de mon token
< Cache-Control: no-cache, private              -> pas d'accès a mon cache
< Date: Tue, 04 Oct 2022 14:28:03 GMT               -> date & heure
< 



## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

curl -H "x-student: Combettes" -v --data "Test texte"   https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

requête :
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: Combettes
> Content-Length: 10
> Content-Type: application/x-www-form-urlencoded
> 

réponse :
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: d6413577-b059-40a6-b2db-b1593f3a25d2
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:48:49 GMT
< 


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse


curl -X POST \
   https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe  \
  --data "{"Hello" : "World"}" \
  -H 'Content-Type: application/json' \
  -H "x-student: Combettes" \
  -v
  

> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: Combettes
> Content-Type: application/json
> Content-Length: 15
> 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e1ee83ea-5e1d-4f79-9de7-f8fea859ba3e
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:59:53 GMT
<

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

Méthode 1:

curl -v -H "x-student:Combettes" -u "utilisateur:motdepasse" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> Authorization: Basic dXRpbGlzYXRldXI6bW90ZGVwYXNzZQ==
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:Combettes
> 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: eb23e1c5-9b2c-470b-ab19-eb41fa0bce51
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:12:13 GMT
< 

Méthode 2:
curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v -H "x-student:Combettes"  -H "Authorization: Basic bG9naW46cGFzc3dvcmQ"

> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:Combettes
> Authorization: Basic bG9naW46cGFzc3dvcmQ
> 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 75f587ce-76aa-4a74-92c6-58b84c4be82e
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:17:54 GMT
< 




## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
 

curl -i -H "Cache-Control: must-revalidate"  -H "Pragma: no-cache"  -H "Expires: 0" https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

ne marche pas

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl -v --data "test" -X PATCH https://demo.api-platform.com/top_books/1

Erreur 405 il n'acceptes pas la méthode.

## Quel est le code HTTP reçu ? Quel est sa signification ?

Que je n'ai pas le droit de patcher le site.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

404 car la page n'existe pas

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

301 c'est une redirection d'url

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

curl -L https://google.fr -v 

curl -v https://www.google.com/ 