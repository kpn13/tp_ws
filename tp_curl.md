# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : 

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
         curl https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -v -H "x-student:sadeddine"
*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server did not agree on a protocol. Uses default.
> GET /d4ec90aa-8173-48dd-8414-6fb832ea2a26 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> x-student:sadeddine
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: be8b1f9b-5ba9-42ee-8463-445dcc4e65c2
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 12:40:17 GMT
<
* Connection #0 to host webhook.site left intact

## Quel est la version du protocole utilisé par le serveur ?
curl 7.83.1 (Windows) libcurl/7.83.1 Schannel
Release-Date: 2022-05-13
Protocols: dict file ftp ftps http https imap imaps pop3 pop3s smtp smtps telnet tftp
Features: AsynchDNS HSTS IPv6 Kerberos Largefile NTLM SPNEGO SSL SSPI UnixSockets


## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
             "x:student : sadeddine" >= identifier le client      
              HTTP/1.1 200 OK >= version hhtp
              Server: nginx >=nom du serveur
              Content-Type: text/plain; charset=UTF-8 >=utilisé pour indiquer le type de média d'origine de la ressource
              Vary: Accept-Encoding >= Il est utilisé par le serveur pour indiquer quels en-têtes sont utilisés
              X-Request-Id: 21a138db-4434-4687-804e-9776f6bee5fd >= peut être utilisé pour tracer des requêtes individuelles vers un service Web ​​du client vers le serveur.
              X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26 
              Cache-Control: no-cache, private >=  contient des instructions dans les requêtes et dans les réponses
              Date: Thu, 22 Sep 2022 13:05:25 GMT

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
    

## Quel est le code de la réponse ? Que signifie-t-il ?
      200 = la requete est une succées.

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< Cache-Control: no-cache
< Connection: close
< Content-Type: text/html

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl -d 'test' -v -H "x-student:sadeddine" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
curl -d '{"clé":"valeur"}' -v -H "Content-Type:application\json" -X POST https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:sadeddine"
: Unnecessary use of -X or --request, POST is already inferred.
*   Trying 46.4.105.116:443...
* Connected to webhook.site (46.4.105.116) port 443 (#0)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server did not agree on a protocol. Uses default.
> POST /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> Content-Type:application\json
> x-student:sadeddine
> Content-Length: 14


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
1ere methode : curl -u login:sad -v https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501
2eme methode : curl -H 'Authorization:bG9naW46c2Fk=' -v https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H "x-student:sadeddine"
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.83.1
> Accept: */*
> 'Authorization:bG9naW46c2Fk='
> x-student:sadeddine


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}
## Quel est le code HTTP reçu ? Quel est sa signification ?
le code http: 2, la signification = succées.


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"}

## Quel est le code HTTP ? Que signifie-t-il ?
le code http est 404 , la page est introuvable

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

< HTTP/1.1 301 Moved Permanently
< Location: https://www.google.fr/
< Content-Type: text/html; charset=UTF-8
< Date: Tue, 25 Oct 2022 16:31:55 GMT
< Expires: Tue, 25 Oct 2022 16:31:55 GMT
< Cache-Control: private, max-age=2592000
< Server: gws
< Content-Length: 219
< X-XSS-Protection: 0
< X-Frame-Options: SAMEORIGIN
< Set-Cookie: CONSENT=PENDING+680; expires=Thu, 24-Oct-2024 16:31:55 GMT; path=/; domain=.google.fr; Secure
< P3P: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< Alt-Svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
le code http renvoyé est 301 , on parle de rederiction , document est deplacé vers une nouvelle adresse (URI)

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
