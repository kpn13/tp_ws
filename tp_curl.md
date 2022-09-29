# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
  --> curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -H "x-student MADAOUI" -v

## Quel est la version du protocole utilisé par le serveur ?
  --> User-Agent: curl/7.85.0

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
    x-student:MADAOUI

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
	* Server certificate:
        *  subject: CN=webhook.site
 	*  start date: Jul 31 23:09:19 2022 GMT
	*  expire date: Oct 29 23:09:18 2022 GMT
	*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
	*  issuer: C=US; O=Let's Encrypt; CN=R3
	*  SSL certificate verify ok.

## Quel est le code de la réponse ? Que signifie-t-il ?
	(HTTP/1.1 200 OK) -> code :200
			  -> Signification : succès de la requête 

## Quels headers recevez vous dans la response ? Quels sont leur sens ?
	    Content-Type: text/plain; charset=UTF-8 -> indique le type de media 
 	    Transfer-Encoding: chunked	-> header spécifie la forme de codage utilisée
	    Vary: Accept-Encoding ->
	    X-Request-Id: 560a5ffe-a76b-4134-b380-1bc0f89b89b7 -> identifiant de la requête transmise au serveur
            X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 ->
 	    Cache-Control: no-cache, private
           
## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
   --> curl -X patch https://demo.api-platform.com/top_books/1 
   -->
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
   
   

## Quel est le code HTTP reçu ? Quel est sa signification ?
   --> 405 : methode non disponible

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1   

   -->	

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

   -->{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr
  --> <HTML>
      <HEAD>
         <meta http-equiv="content-type" content="text/html;charset=utf-8">
         <TITLE>301 Moved</TITLE>
      </HEAD>
      <BODY>
        <H1>301 Moved</H1>
        The document has moved
        <A HREF="https://www.google.fr/">here</A>.
      </BODY>
     </HTML>


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
