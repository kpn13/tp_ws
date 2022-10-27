# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

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

Requete : ```curl -d '{"login": "camille", "password": "sucess"}' -H "Content-Type: application/json" -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501```


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

* first : ``curl https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501  -u "camille:sucess" -v``
<!--
SSL certificate verify ok.
* Server auth using Basic with user 'camille'
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> Authorization: Basic Y2FtaWxsZTpzdWNlc3M=
> User-Agent: curl/7.74.0
> Accept: */*
-->

* second : ``curl https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "Authorization: Basic AUTHENTIFICATION" -v``

<!--
 SSL certificate verify ok.
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> Authorization: Basic AUTHENTIFICATION
-->


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 

<!--
curl: (6) Could not resolve host: GET
curl: (1) Protocol "s" not supported or disabled in libcurl
-->

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

requete : ``curl -X PATCH https://demo.api-platform.com/top_books/1``
<!--
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
</html>
-->

## Quel est le code HTTP reçu ? Quel est sa signification ?

<!--
C'est une 405 pour Méthode non autorisée
-->


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

<!--
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}
-->

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

<!--
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}
-->

## Quel est le code HTTP ? Que signifie-t-il ?

<!--
Il s'agit d'une 404 page not found
-->

## Exécuter la requête suivante et copier la réponse : curl https://google.fr
<!--
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8"> <TITLE>301 Moved</TITLE></HEAD><BODY> <H1>301 Moved</H1> The document has moved <A HREF="https://www.google.fr/">here</A>. </BODY></HTML>
>

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

<!--
Il s'agit d'une 301 pour redirection permanante
-->

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

first :
<!--
Pour annuler cette redirection, il faut supprimer le cache de la façon suivante :

- Cliquez sur le menu en haut à droite de Google Chrome puis sur "Paramètres".
- Dans la catégorie "Confidentialité", cliquez sur "Effacer les données de navigation...".
- Choisissez depuis quand est-ce que vous souhaitez que le cache soit effacé (depuis le moment où vous avez eu le problème pour la première fois), puis seléctionnez uniquement "Images et fichiers en cache"
-->

second :

<!--
Si vous utilisez le client FTP Transmit sous OSX, vous avez surement remarqué que les fichier .htaccess ne sont pas visibles dans la liste des fichiers de vos serveurs. Ces fichiers sont en effet cachés par défaut par l'application.
-->
