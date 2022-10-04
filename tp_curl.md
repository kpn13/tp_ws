# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
La commande exécutée est curl --verbose --header "x-student : KAMARO" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe 
La requête est: 
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: KAMARO
> 
la reponse est:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 352ea799-e56c-4ff5-9f89-44769f2316fc
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 14:29:16 GMT
< 


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
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: KAMARO
> Content-Type: text/plain
> Content-Length: 16
> 
reponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: bbfec9a3-9ded-4f0e-ac79-9a9aa7005079
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:06:39 GMT
<

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
commande: curl -X POST -H "x-student: KAMARO" -H "Content-Type: application/json" --data "{"login":"my_login","password":"my_password"}" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe --verbose
requête: 
> POST /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: KAMARO
> Content-Type: application/json
> Content-Length: 37
> 
réponse:
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 87aaf581-415f-4ce0-8769-48cc16c6935f
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:20:26 GMT
< 

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
La réponse est :
< HTTP/2 404 
< date: Tue, 04 Oct 2022 15:27:52 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=LwxjAP%2BZEox08GTrPDzPNS6Qo99MD2cPUTvjKkr2%2FYOdH0KF5IPrCp5htr3n4WE%2FUt16id12a1NfnDkHO5ydCLeMZM%2BV7y0zCGY5CP7m85MmKFHFx8yZQ28xX0DCn9Sler1LEGIIzLE%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 754ef1b1ad219966-FRA
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
< 

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
