# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 


Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
La commande curl : ```curl --header "x-student: Megi_Balliu" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26```

La reponse : Il n'y a pas de reponse. Cette commande est juste censé ajouter un header avec notre nom, pour nous identifier. Le fait qu'il n'y ait pas d'erreur signifie que ca c'est bien passé.

## Quel est la version du protocole utilisé par le serveur ?
La commande : ```curl -v  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26```
Reponse : La version du protocole utilisé par le serveur est : HTTP/1.1
``
*   Trying 46.4.105.116:443...
    * Connected to webhook.site (46.4.105.116) port 443 (#0)
    * schannel: disabled automatic use of client certificate
    * ALPN: offers http/1.1
    * ALPN: server did not agree on a protocol. Uses default.
    > GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
    > Host: webhook.site
    > User-Agent: curl/7.83.1
    > Accept: */*
    >
    * Mark bundle as not supporting multiuse
    < HTTP/1.1 200 OK
    < Server: nginx
    < Content-Type: text/plain; charset=UTF-8
    < Transfer-Encoding: chunked
    < Vary: Accept-Encoding
    < X-Request-Id: ad61a4a5-9d07-443c-b92e-50b0941503a0
    < X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
    < Cache-Control: no-cache, private
    < Date: Sun, 25 Sep 2022 18:31:34 GMT
    <
    * Connection #0 to host webhook.site left intact
``
## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

``
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
    > Host: webhook.site
    > User-Agent: curl/7.83.1
    > Accept: */* 
``
Ce sont les headers que l'on envoie dans la requete. Ces headers contiennent plus d'informations sur le client, ou au sujet de ce qu'on cherche (avec GET)

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
Vu que je travaille actuellement sous Windows, on ne me donne pas des informations par rapport au certeficat SSL. Mais normalement la commande pour trouver ces informations c'est 
`` curl https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v -i ``
Et la reponse que moi j'ai avec cette commande c'est : 
`` 
*   Trying 46.4.105.116:443...
    * Connected to webhook.site (46.4.105.116) port 443 (#0)
    * schannel: disabled automatic use of client certificate
    * ALPN: offers http/1.1
    * ALPN: server did not agree on a protocol. Uses default.
    > GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
    > Host: webhook.site
    > User-Agent: curl/7.83.1
    > Accept: */*
    >
    * Mark bundle as not supporting multiuse
    < HTTP/1.1 200 OK
    HTTP/1.1 200 OK
    < Server: nginx
    Server: nginx
    < Content-Type: text/plain; charset=UTF-8
    Content-Type: text/plain; charset=UTF-8
    < Transfer-Encoding: chunked
    Transfer-Encoding: chunked
    < Vary: Accept-Encoding
    Vary: Accept-Encoding
    < X-Request-Id: 8e0e2c04-aeef-4452-a06a-8da9fd52529c
    X-Request-Id: 8e0e2c04-aeef-4452-a06a-8da9fd52529c
    < X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
    X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
    < Cache-Control: no-cache, private
    Cache-Control: no-cache, private
    < Date: Thu, 06 Oct 2022 12:19:17 GMT
    Date: Thu, 06 Oct 2022 12:19:17 GMT

    <
    * Connection #0 to host webhook.site left intact
``

## Quel est le code de la réponse ? Que signifie-t-il ?

200 OK - la famille de 200 dans la reponse c'est facon de te dire que tout c'est bien passé avec la requete que tu viens d'envoyer.


## Quels headers recevez vous dans la response ? Quels sont leur sens ?
``
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 9b33d89a-2936-4e07-91dd-b613094809f0
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 12:34:34 GMT
<
* Connection #0 to host webhook.site left intact 
``

Date - header qui montre quand le message est envoyé 
Content-type :  indique au client le type de contenu réellement renvoyé
Cache-Control : un header qui va dire ce qu'on doit "catch" dans la reponse et dans la requete

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
la requete : ``curl -d "Megi Balliu 1ere année de master" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe ``

la reponse : Il n'y a pas de reponse, donc a priori c'est que ca a marché.

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
 PAS FINIE `` curl -X POST "Content-Type: application/json" -F "nom = Megi" https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -v ``

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
