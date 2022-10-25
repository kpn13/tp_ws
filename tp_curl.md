# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
La commande exécutée est curl --verbose --header "x-student : KAMARO" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 
La requête est: 
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1

la reponse est:
200
 

## Quel est la version du protocole utilisé par le serveur ?
Le serveur utilise la version 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
Les headers envoyés sont:
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1 : qui precise le type de requête envoyé, la page souhaité et le protocole souhaitée
> Host: webhook.site : precise le site d'hebergement de la ressource
> User-Agent: curl/7.74.0 : precise l'interface utilisé
> Accept: */* : precise le type de données que le client accepte
> x-student: KAMARO : precise l'identifiant du client de la requête

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
le certificat ssl utilisé est CAfile: /etc/ssl/certs/ca-certificates.crt et utilise le TSL version 1.3

## Quel est le code de la réponse ? Que signifie-t-il ?
le code de la réponse est 200 est signifie que la requête est reussie

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
< HTTP/1.1 200 OK : code de la reponse
< Server: nginx : serveur hebergeant le site
< Content-Type: text/plain; charset=UTF-8 : codage de la page
< Transfer-Encoding: chunked : mecanisme de transfert des données
< Vary: Accept-Encoding : informe les navigateurs si le client peut gérer la version compressée du site web.
< X-Request-Id: 378afa0a-b4c0-4d09-94f5-4a5cd2d03910 : identifiant de la requête
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe : identifiant de la page
< Cache-Control: no-cache, private : controleur du cache de la page
< Date: Tue, 04 Oct 2022 14:44:43 GMT : date et heure de la reque

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
commande exécutée: curl -X POST -H "x-student: KAMARO" -H "Content-Type: text/plain" --data "this is raw data" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe --verbose
requête: 
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1

reponse:
200 


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
commande: curl -X POST -H "x-student: KAMARO" -H "Content-Type: application/json" --data "{"login":"my_login","password":"my_password"}" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe --verbose
requête: 
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1

réponse:
200 


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
1ère méthode: 
la commande est: "curl -u "login:password" --header "x-student : KAMARO" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe --verbose"
la requete est: 
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1

et la réponse est: 
<html><body><h1>400 Bad request</h1>
Your browser sent an invalid request.
</body></html>

2è methode:
la commande est: curl -H "Authorization: Basic 37f00faa-5d4f-4572-97a8-2db3c5b785c5" --header "x-student : KAMARO"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 --verbose

la requête est: 
> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Authorization: Basic 37f00faa-5d4f-4572-97a8-2db3c5b785c5

Et la réponse est :
<html><body><h1>400 Bad request</h1>
Your browser sent an invalid request.
</body></html>

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
La réponse est :
404 


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
La réponse est:
<!DOCTYPE html>
<html>
<body>
    <h1>Oops! An Error Occurred</h1>
    <h2>The server returned a "405 Method Not Allowed".</h2>

    <p>
        Something is broken. Please let us know what you were doing when this error occurred.
        We will fix it as soon as possible. Sorry for any inconvenience caused.
    </p>

</body>

## Quel est le code HTTP reçu ? Quel est sa signification ?
le code reçu est 405 et signifie que la méthode PATCH est non permise.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
La réponse reçue est :
200 

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
La réponse est:
404

## Quel est le code HTTP ? Que signifie-t-il ?
le code est 404 signifiant que la page n'a pas été trouvé

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
le code reçu est 301 et signifie que l'url a été redirigé de manière permanente. La raison pour laquelle on reçoit cela est que Google redirige les utilisateurs de manière automatique vers la page https://www.google.fr/ mais que curl ne les accepte pas par défaut

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
La première méthode consiste à mettre la bonne url qui est https://www.google.fr/ et la seconde methode consiste à rajouter un -l dans la requête ce qui permet à curl d'accepter les rédirections.q