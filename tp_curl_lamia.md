# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H"x-student: LAMIA_BOURIAH" -v



## Quel est la version du protocole utilisé par le serveur ?

curl -v https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501
HTTP/1.1 200 OK



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
curl -d '{"login":"lamia", "password":"mypass"}' -H "Content-Type: application/json" -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501




## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
Première requete:curl https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -u "lamia:mypass" -v  

REPONSE 1 : 
Server auth using Basic with user 'lamia'
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> Authorization: Basic bGFtaWE6bXlwYXNz
> User-Agent: curl/7.74.0
> Accept: */*


 
 DEUXIEME REQUETE :curl https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "Authorization: Basic STUDENT" -v

 REPONSE 2: 
 > GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Authorization: Basic STUDENT

 


 




## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 



curl: (6) Could not resolve host: GET
curl: (3) URL using bad/illegal format or missing URL



## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl: (6) Could not resolve host: PATCH
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



## Quel est le code HTTP reçu ? Quel est sa signification ?
Code HTTP reçu : 405 method not allowed, donc on ne peut pas utiliser la méthode PATCH pour cette requête


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
<html>
<head><title>400 Bad Request</title></head>
<body>
<center><h1>400 Bad Request</h1></center>
<hr><center>cloudflare</center>
</body>
</html>


## Exécuter la commande suivante puis indiquer la réponse : curl -X https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
Not found ==> code HTTP 404


## Exécuter la requête suivante et copier la réponse : curl https://google.fr
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
301 Moved : il s'agit d'une redirection, ça force le navigateur web en charge de consulter un contenu a une adresse donnée sur internet a vous afficher le contenu d'un autre site web.

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
