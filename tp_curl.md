# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : 

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
Commande :  `curl --header "X-student : Saidane" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26` 
Requête : On essaye d'accéder à l'URL avec un header portant sur notre nom d'étudiant. 
Réponse : 
```
 % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    91    0    91    0     0    513      0 --:--:-- --:--:-- --:--:--   517<html><body><h1>400 Bad request</h1>
Your browser sent an invalid request.
</body></html>
```
Curl répond que la requête est invalide car le header donné n'est pas celui attendu

## Quel est la version du protocole utilisé par le serveur ?
Commande : ` curl -i --header "X-student : Saidane" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26` 
Reponse : `HTTP/1.0` il s'agit donc de la v1 du protocole HTTP
## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
`x-student`
Le header envoyé permet d'avoir des infos sur l'étudiant

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
` curl -v --header "X-student : Saidane" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26`
On apprend que le certificat utilisé est TLSv1.3 / TLS_AES_256_GCM_SHA384 et que ce certificat est valide pour cette requête.


## Quel est le code de la réponse ? Que signifie-t-il ?
On a : 
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: CN=webhook.site
*  start date: Jul 31 23:09:19 2022 GMT
*  expire date: Oct 29 23:09:18 2022 GMT
*  subjectAltName: host "webhook.site" matched cert's "webhook.site"
*  issuer: C=US; O=Let's Encrypt; CN=R3
*  SSL certificate verify ok.


## Quels headers recevez vous dans la reponse ? Quels sont leur sens ?
```
< HTTP/1.0 400 Bad request
< Cache-Control: no-cache
< Connection: close
< Content-Type: text/html
```
On apprend que la requête est invalide (error 400)

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse


## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse
`curl -d '{"x-student":"Saidane"}' -H "Content-Type: application/json" -X POST  https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26`
```
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: af84d8af-7a40-417b-a97b-1354ee2504d9
< X-Token-Id: d4ec90aa-8173-48dd-8414-6fb832ea2a26
< Cache-Control: no-cache, private
< Date: Thu, 22 Sep 2022 13:07:15 GMT
```


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 
`curl -u "login:Saidane" https://webhook.site/d4ec90aa-8173-48dd-8414-6fb832ea2a26 -v`

## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
La méthode GET est par défaut 
```
{"@context":"\/contexts\/Book","@id":"\/books\/07dd4786-aaa7-4d08-a467-076b76f1d1b6","@type":"https:\/\/schema.org\/Book","id":"07dd4786-aaa7-4d08-a467-076b76f1d1b6","isbn":"9791891164452","title":"Cupiditate a eum natus officia laudantium recusandae aliquam.","description":"Qui vitae enim et explicabo possimus nesciunt voluptatibus. Officia fugit iste et et. Totam repellendus provident voluptatem.","author":"Percival Toy","publicationDate":"2020-01-25T00:00:00+00:00","reviews":[{"@id":"\/reviews\/2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","@type":"https:\/\/schema.org\/Review","id":"2b069fe2-a6f7-4b17-b9a5-090caaabdc7f","body":"Qui voluptatem beatae quia accusamus et libero. Officia voluptatibus qui molestias temporibus."},{"@id":"\/reviews\/dc276e75-d6af-430d-8e50-1a4a15cd39bd","@type":"https:\/\/schema.org\/Review","id":"dc276e75-d6af-430d-8e50-1a4a15cd39bd","body":"Voluptatum vero ab ducimus sapiente consequatur explicabo. Occaecati repellat nobis doloremque enim est ipsam atque. Nihil autem expedita aut et molestiae aut sequi. Vitae quo explicabo ut corporis sapiente minima ut. Aut quae nam in ut officiis dolorum ut."},{"@id":"\/reviews\/8cf8e5d4-c4cd-48ab-abbe-868d74137647","@type":"https:\/\/schema.org\/Review","id":"8cf8e5d4-c4cd-48ab-abbe-868d74137647","body":"Earum non qui fugit consequuntur magnam. Ut sed fuga culpa quibusdam doloribus eum quis. Aut modi porro nulla quaerat. Veniam quidem in aut voluptatem. Eum laudantium aut amet debitis ut."},{"@id":"\/reviews\/25f8d916-9692-4783-8dbe-5042fa4e9bff","@type":"https:\/\/schema.org\/Review","id":"25f8d916-9692-4783-8dbe-5042fa4e9bff","body":"Natus autem est ut sunt laboriosam ex quos. Temporibus facere error voluptate odio. Dolores est aut aliquam. Commodi occaecati itaque impedit vitae nihil officia beatae."}]}
```

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
` curl --request PATCH https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6`
```
{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"The content-type \u0022application\/x-www-form-urlencoded\u0022 is not supported. Supported MIME types are \u0022application\/merge-patch+json\u0022, \u0022application\/vnd.api+json\u0022."}
```

## Quel est le code HTTP reçu ? Quel est sa signification ?
HTTP/2

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1
`{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}`

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
