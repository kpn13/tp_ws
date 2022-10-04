# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "LACHEHEB"
Le système renvoie le code HTML de la page ayant l'URL passé

## Quel est la version du protocole utilisé par le serveur ?
curl -v https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -H "x-student: LACHEHEB"
la version : HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
-H "typeContenu: contenu" ==> Utiliser pour indiquer le type de la ressource envoyer
-H "Accept: text/html" ==> Le type de contenu que le client peut traiter
-d "[json data]"

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
SSL utilise TLSv1.3: c'est un protocol destiné à fournir une meilleure sécurité et à améliorer les pérformances


## Quel est le code de la réponse ? Que signifie-t-il ?
<!DOCTYPE html>
<html>
<head>
    <title>Error:  - Webhook.site</title>
    <link href="/assets/css/libs/bootstrap.min.css" rel="stylesheet" crossorigin="anonymous">
    <link href="/css/app.css" rel="stylesheet">
</head>
<body>
<div class="container" style="padding: 40px">
    <div class="row">
        <div class="col-sm-4 col-sm-offset-4 text-center">
            <h1>Webhook.site Error</h1>
            <p class="lead">404 </p>
                        <p class="small">
                    The URL was deleted manually, or expired automatically.

    To avoid URLs expiring automatically, you can
    <a href="/register">upgrade to Webhook.site Pro or Enterprise</a>.
            </p>
                        <br>
            <p><a class="btn btn-primary" href="/" role="button">&larr; Back to Webhook.site</a></p>
            <br>
            <p class="small muted">Copyright &copy; 2022 Webhook ApS</p>
        </div>
    </div>
</div>
</body>
</html>
===> signification: le code html de la page ayant l'URL passé en requête.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
HTTP/1.1 200 OK ===> La version du protocol utilisé par le serveur
Server: nginx ===> le nom du serveur
Content-Type: text/plain; charset=UTF-8 ===> type du contenu renvoyé
Vary: Accept-Encoding
X-Request-Id: 03287c3e-eb26-4915-9e00-a6aa67f46c10
X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
Cache-Control: no-cache, private ===> Le Cash de control
Date: Tue, 04 Oct 2022 14:54:03 GMT ===> La date de la requête

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
