# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : [https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501](https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501)

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse

```sh
curl --header "x-student: VILLELEGIER"  -v https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26
```

```sh
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.74.0
> Accept: */*
> x-student: VILLELEGIER


< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 8bff04f0-dd23-4b7d-ab7b-1147efa48376
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 29 Sep 2022 14:11:15 GMT
```


## Quel est la version du protocole utilisé par le serveur ?

http 1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?

| Headers |  |
| ------    | ------   |
| Host: | Le nom de domaine du serveur|
| User-Agent:   | Une chaine de charactere précisant au serveur quel application, os, version essaye de se connecter |
| Accept: | Type de media pouvant être accepter en retour, ici */* signifie qu' on accepte tout|


## Quelles informations pouvez-vous trouver à propos du certificat SSL ?

```sh
 Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.
```


## Quel est le code de la réponse ? Que signifie-t-il ?

Le code de retour est 200 => requête réussie

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

| Headers | |
| ------    | ------   |
| Server: | Le nom du serveur | 
| Content-Type: | Type de contenu retourné, ici UTF-8 |
| Transfer-Encoding | La forme encodage utilisé pour transferé l'entitité au serveur (chunked, compress, deflate, gzip, identity) |
| Vary| Précise au serveur si il peut utilisé la reponse en cache pour les future requête |
| Cache-control | Contrôle le cache dans les naviguateur, proxies, ici pas de cache |
| Date | Date et heure de l'envoie de la réponse |


## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse

```sh
curl -X POST -H "x-student: VILLELEGIER" -H "Content-Type: text/plain" --data "this is raw data" -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5
```

```sh
> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: VILLELEGIER
> Content-Type: text/plain
> Content-Length: 16


< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 6fce31a8-f18e-4116-a459-22950c2ff00f
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 13:56:43 GMT
```


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse

```sh
curl -X POST -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student: VILLELEGIER" -H 'Content-Type: application/json' -d '{"login":"my_login","password":"my_password"}'
```

```sh
> POST /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: VILLELEGIER
> Content-Type: application/json
> Content-Length: 45


< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 151f327f-6a6c-47b6-820e-3eb74741fea8
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:00:42 GMT
```

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

_Méthode n°1_ : en utilisant l'option `-u` qui genère le header automatiquement.

```sh
curl -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student: VILLELEGIER" -u "login:password"


> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> Authorization: Basic bG9naW46cGFzc3dvcmQ=
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: VILLELEGIER


< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 94ec747d-e50e-4c4c-8b78-e31cc47d7ce4
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:04:32 GMT
```

_Méthode n°2_ : En générant nous même le header ¯\_(ツ)_/¯

```sh
curl -v https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5 -H "x-student: VILLELEGIER" -H "Authorization: Basic bG9naW46cGFzc3dvcmQ="

> GET /37f00faa-5d4f-4572-97a8-2db3c5b785c5 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student: VILLELEGIER
> Authorization: Basic bG9naW46cGFzc3dvcmQ=


< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 3a88d39a-37aa-4739-bd72-c60cdf4cdd87
< X-Token-Id: 37f00faa-5d4f-4572-97a8-2db3c5b785c5
< Cache-Control: no-cache, private
< Date: Thu, 06 Oct 2022 14:05:46 GMT
```

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 




La requête renvoie un 404.
Mais si on demande du html avec curl, on obtient un 200 et le livre. 

```sh
curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 -H "Accept: text/html" -v
```

```sh
< HTTP/1.1 200 OK
< Date: Thu, 06 Oct 2022 20:24:30 GMT
< Content-Type: text/html; charset=utf-8
< Transfer-Encoding: chunked
< Connection: keep-alive
< Cache-Control: s-maxage=3, stale-while-revalidate
< Link: </docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation", </.well-known/mercure>; rel="mercure"
< Permissions-Policy: browsing-topics=()
< Vary: Accept-Encoding
< X-Nextjs-Cache: STALE
< X-Powered-By: Next.js
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=TLsRecZQNWhLqbAWFn93vtgag0%2FCgr6y4Ezv50NTcnzKMA8YS%2FXcK2M8Qj6UYA6V0DkRTSoILyXzILzE%2FJbqZb%2BvhtLE1%2BZV6SRQEXZ9cgvCMuGJFcwAhNzQTUN5eJ6Th%2BeTKFq3VKmC4EUxLniSY5Rlrsk%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 75611ef508d699aa-CDG
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
```

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

```sh
curl --request PATCH https://demo.api-platform.com/top_books/1 -v

> PATCH /top_books/1 HTTP/1.1
> Host: demo.api-platform.com
> User-Agent: curl/7.83.1
> Accept: */*


< HTTP/1.1 405 Method Not Allowed
< Date: Thu, 06 Oct 2022 14:26:36 GMT
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Connection: keep-alive
< Allow: GET
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Permissions-Policy: browsing-topics=()
< Status: 405 Method Not Allowed
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=uGlJLHTIL4a8bBYLDYm2IFgtx6oJ5%2FGusPqFy1vYWHdJ5LUms%2FEQeb6i4UI5Ws6I06YIOkGu%2FuCLolyLZwqA36VqypO6v9l57Bj85WFZ6hLGXMgFXlSOv8ThXl1EPbi1KFzN4%2FIKIk0%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 755f12b02cd783ba-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

```


## Quel est le code HTTP reçu ? Quel est sa signification ?

Le code reçu est 405 Method Not Allowed, il indique que la méthode utilisée pour la requête est connue du serveur mais qu'elle n'est pas supportée par la ressource ciblée. Top book doit être 
générer automatiquement, cela fait sens que seul GET soit autorisé.

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

```sh
> GET /top_books/1 HTTP/1.1
> Host: demo.api-platform.com
> User-Agent: curl/7.83.1
> Accept: */*



< HTTP/1.1 200 OK
< Date: Thu, 06 Oct 2022 14:30:54 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 183
< Connection: keep-alive
< Cache-Control: no-cache, private
< Etag: "06a23177dff31429d2a7390117fe1b2d"
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Permissions-Policy: browsing-topics=()
< Vary: Accept
< Vary: Content-Type
< Vary: Authorization
< Vary: Origin
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=9tBmJ7KYmG9KGeXpocu1rhMCqzqQLGNEZkxBvsmKJypDELRLoyAFrbxvFBZnUDZIAFNdHRUQZHvqyfEZxI%2BwhP8ti2nTd7m7UFqxt0ksLpudeTf409RVBrfPA%2B3ozVoWhhZvByT5nlc%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 755f18fdbe6a3759-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}* Connection #0 to host demo.api-platform.com left intact
```


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

```sh
> GET /top_books/9999 HTTP/1.1
> Host: demo.api-platform.com
> User-Agent: curl/7.83.1
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 404 Not Found
< Date: Thu, 06 Oct 2022 14:33:05 GMT
< Content-Type: application/ld+json; charset=utf-8
< Content-Length: 120
< Connection: keep-alive
< Cache-Control: no-cache, private
< Link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< Permissions-Policy: browsing-topics=()
< Status: 404 Not Found
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< Via: 1.1 google
< CF-Cache-Status: DYNAMIC
< Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=IcR7SjuSonJnc3n4WlCLoLiJ1h8EgOr6SWUnGMpTyx9fbS0WKCXKrMid%2BSQICuMjUycsI9fF465A%2B8NJ5D6T6l0MtGpV7Pef9goXfvoWdnHvi4D85mLez9cwcVbQSfqQ%2BtOhO%2F3neMc%3D"}],"group":"cf-nel","max_age":604800}
< NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< Server: cloudflare
< CF-RAY: 755f1c2fbbf2375d-MXP
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
<
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}* Connection #0 to host demo.api-platform.com left intact
```


## Quel est le code HTTP ? Que signifie-t-il ?

Le code reçu est le 404 Not Found, il indique qu'un serveur ne peut pas trouver la ressource demandée. Probablement qu'il n'existe pas de top book 9999, top book semble avoir que 100 livres.

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

```sh
< HTTP/1.1 301 Moved Permanently
< Location: https://www.google.fr/
< Content-Type: text/html; charset=UTF-8
< Date: Thu, 06 Oct 2022 14:42:00 GMT
< Expires: Thu, 06 Oct 2022 14:42:00 GMT
< Cache-Control: private, max-age=2592000
< Server: gws
< Content-Length: 219
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
< Set-Cookie: CONSENT=PENDING+429; expires=Sat, 05-Oct-2024 14:42:00 GMT; path=/; domain=.google.fr; Secure
< P3P: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
```

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code recu est le 301, il est utilisé pour une redirection d'URL permanente. 

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.

_Solution n°1_ : utilisé `--location command-line option`, ce flag précise à curl de renvoyer une requête à la nouvelle adresse danc ce cas https://www.google.fr/.

```sh
curl https://google.fr -v -L
```


_Solution n°2_ : suivre la redirection à la main en exécutant une nouvelle requête curl avec la nouvelle adresse ¯\_(ツ)_/¯.


