        # TP curl - comprendre les requêtes et les réponses HTTP

        Pour les questions suivantes, vous devez utiliser l'url suivante  : https://webhook.site/#!/37f00faa-5d4f-4572-97a8-2db3c5b785c5

        Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

        <!-- ## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse -->
        curl -v --header "X-student:masharideh"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5





        ## Quel est la version du protocole utilisé par le serveur ?
        http/1.1



        ## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
        --"x-student:masharideh" 

        ## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
         SSL certificate verify ok.
         old SSL session ID is stale, removing



        ## Quel est le code de la réponse ? Que signifie-t-il ?
         200
           
       Le code de statut de réponse HTTP 200 OK indique la réussite d'une requête. Une réponse 200 
       
        ## Quels headers recevez vous dans la response ? Quels sont leur sens ?
        
         HTTP/1.1 200 OK
         Server: nginx
         Content-Type: text/plain; charset=UTF-8
         Transfer-Encoding: chunked
         Vary: Accept-Encoding
       X-Request-Id: f3393849-05ba-4e30-b9f1-97344a2c6a68
      <X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
      < Cache-Control: no-cache, private
      < Date: Thu, 06 Oct 2022 14:28:38 GMT
       < 
       Connection #0 to host webhook.site left intact


        ## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
        
       curl -v --header "X-student:masharideh"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 "Content-Type: text/plain" POST --data "mariam"


        ## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
        
        curl -v --header "X-student:masharideh"  https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 "Content-Type: application/json"  POST -d '{"NOM":"Dalton", "PRENOM":"joe", "NAISSANCE":"2000-08-15", "VILLE":"Orleans"}' 
        
        POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
     > Host: webhook.site
     > User-Agent: curl/7.74.0
     > Accept: */*
     > X-student:masharideh
     > Content-Length: 77
     > Content-Type: application/x-www-form-urlencoded



        ## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
        
        curl https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "X-student:masharideh" -u "log:12344" -v



        ## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
        erreur


        ## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
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
        {"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}


        ## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
        "@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}


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
        301 moved ==> la ressource a été déplacée



        ## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
        1-utiliser www.google.fr
         2- utiliser l'option -L pour suivre les redirections
