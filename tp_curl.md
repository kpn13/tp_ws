# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student:MOUNA"


la requete : 

> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student:MOUNA
> 


la réponse : 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 711d4c2e-5b24-4466-99d3-425884249ed5
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 15:30:22 GMT
< 


## Quel est la version du protocole utilisé par le serveur ? 
La version 1.1




## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
SENS : la méthode utilisée (GET)

> Host: webhook.site
SENS : le nom de domaine du serveur

> User-Agent: curl/7.74.0
SENS : la version de curl (7.74.0)

> Accept: */*
SENS : le client accepte tout les types de contenu

> x-student:MOUNA
SENS :  header customisé


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
SSL certificate verify ok.

Le certificat SSL utilise TLSv1.3 / TLS_AES_256_GCM_SHA384 et il est valide


## Quel est le code de la réponse ? Que signifie-t-il ?
code d'erreur : 200
signification : succes de la requete


## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< HTTP/1.1 200 OK
Sens : la requete a été executé avec succes


< Server: nginx
Sens : information sur le serveur


< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
Sens : type de contenu (text brut) et information d'encoding


< X-Request-Id: 125d4f7f-65b6-472f-98d9-caf00f95e9d4
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:50:52 GMT
< 



## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --request POST --data "this is mon text brut" -H "Content-Type: text/plain" -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5


la requete : 

> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Type: text/plain
> Content-Length: 21
> 




la reponse : 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 1fc0cd42-a53d-4e7e-b9dc-66b9aa0f847d
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 15:32:22 GMT
< 



## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

curl -v -d '{"student":"MOUNA"}' -H "Content-Type: application/json" -X POST https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5


la requete :

> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Content-Type: application/json
> Content-Length: 19
> 


la reponse :

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 0e6b81b7-559a-445c-a824-b2d456bf7bb8
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 15:33:50 GMT
< 


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
methode 01 :

curl -u "MOUNA:123SOLEIL" https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -v


la requete : 

> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> Authorization: Basic TU9VTkE6MTIzU09MRUlM
> User-Agent: curl/7.74.0
> Accept: */*
> 


la reponse : 

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 0b48f848-5b04-4325-9fb2-b888e5087846
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:43:28 GMT
< 



methode 02 : "Authorization: Basic [token]"

curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "Authorization:Basic 123SOLEIL" -v

la requete :

> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Authorization:Basic 123SOLEIL
> 


la réponse :

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: b07fb126-a727-4f22-9099-299e153807f1
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:47:22 GMT
< 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 -X GET -v

Skip : renvoit une erreur 404 (page not found)


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl https://demo.api-platform.com/top_books/1 -X PATCH -v

la reponse :

< HTTP/2 405 
< date: Thu, 06 Oct 2022 14:56:15 GMT
< content-type: text/html; charset=UTF-8
< allow: GET
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 405 Method Not Allowed
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=qco45zyhrK99rWeOZ%2F97F0%2Bxl3ayjEGnfibslk1W2MZxNyp1GEsvvjUFtqRjQGiBHtiptx1EnglOdY4W3vCp2QuKPj1st7%2FWpwSOibSJ8lVdCqCYdENhPtPiqrYyZjHm9jr4v5Zxhv0%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 755f3e1e8e136949-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8" />
    <meta name="robots" content="noindex,nofollow,noarchive" />
    <title>An Error Occurred: Method Not Allowed</title>
    <style>body { background-color: #fff; color: #222; font: 16px/1.5 -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; margin: 0; }
.container { margin: 30px; max-width: 600px; }
h1 { color: #dc3545; font-size: 24px; }
h2 { font-size: 18px; }</style>
</head>
<body>
<div class="container">
    <h1>Oops! An Error Occurred</h1>
    <h2>The server returned a "405 Method Not Allowed".</h2>

    <p>
        Something is broken. Please let us know what you were doing when this error occurred.
        We will fix it as soon as possible. Sorry for any inconvenience caused.
    </p>
</div>
</body>
* Connection #0 to host demo.api-platform.com left intact
</html>   




## Quel est le code HTTP reçu ? Quel est sa signification ?

code HTTP reçu : 405
signification : methode non authorisée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}  


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?

code HTTP : 404
signification : introuvable/inexistant

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

code HTTP : 301
Explication : le contenu n'est plus disponible à l'URL



## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

methode 1 : curl -L https://google.fr


methode 02 : changer le lien (from old URL to new URL)
