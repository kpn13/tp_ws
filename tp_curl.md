# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/37f00faa-5d4f-4572-97a8-2db3c5b785c5

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
| Cache-control | Contrôle le cache dans les naviguateur, proxies, ici pas ce cache |
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

-H "User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.1 (KHTML, like Gecko) Chrome/13.0.782.112 Safari/535.1"

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr

```sh
< HTTP/1.1 301 Moved Permanently
< Location: https://www.google.fr/
< Content-Type: text/html; charset=UTF-8
< Date: Wed, 05 Oct 2022 20:28:05 GMT
< Expires: Wed, 05 Oct 2022 20:28:05 GMT
< Cache-Control: private, max-age=2592000
< Server: gws
< Content-Length: 219
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
< Set-Cookie: CONSENT=PENDING+314; expires=Fri, 04-Oct-2024 20:28:05 GMT; path=/; domain=.google.fr; Secure
< P3P: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
<
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.fr/">here</A>.
</BODY></HTML>
```

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?

Le code recu est le 301, il est utilisé pour une redirection d'URL permanente. 

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
