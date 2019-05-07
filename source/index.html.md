---
title: FLAT documentation

language_tabs: # must be one of https://git.io/vQNgJ
 # - shell
 # - ruby
 # - python
  - javascript

#toc_footers:
 # - <a href='#'>Sign Up for a Developer Key</a>
 # - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction


Bienvenue dans la documentation de l'API FLAT. Ce document à pour but de donner une vue d'ensemble du projet tout en fournissant quelques pointeurs vers de la documentation complémentaire. il est conçu comme un guide de démarrage destiné aux développeurs au sein de l'entreprise.
L’API respecte l’architecture REST. Son utilisation exige la connaissance de base des services web.

Tous les appels de l’API commencent par cette URL à laquelle s’ajoute le chemin vers l’action désirée.

Exemple : `https://www.flat.fr/user/create`

L'API est accessible uniquement via le protocole Http et accepte les requêtes HTTP POST, PATCH, GET et DELETE.
Les données envoyées en POST doivent respecter le format JSON.

Les appels à l'API ne sont pas autorisés depuis un navigateur Web

Suite aux changements récurrents, la documentation est susceptible d'etre modifié.
La zone grise à droite permet de montrer les codes correspondants    

Tout au long de ce document, vous découvrirez des références aux différentes parties de FLAT.

## Pré-requis

- Node JS version 8.9.4
- NPM version 5.6

## Installation

Démarrage du serveur dans l'environnement de développement

`npm run dev`

</br>

Démarrage du serveur dans l'environnement de test

`npm run test`


# Authentication

Certaines requêtes doivent être authentifiées pour être exécutées. Un jeton JWT doit être généré depuis votre compte.

Les appels vers l’API doivent tous préciser dans leurs données POST un paramètre “token” avec ce jeton pour valeur.

<aside class="success">
Rappel — un utilisateur content est un utilisateur authentifié
</aside>

# Liste des actions disponibles selon le module

## Module inscription

Schema associé à droite

```json
[
  "email" : {
		"type" : "String",
		"index" : true
	},
	"username" : "String",
	"firstname" : "String",
	"lastname" : "String",
	"password" : "String",
	"phone" : {
		"type" : "String",
		"index" : true
	},
	"verifyCode" : "String",
	"verifyCodeMail" : "String",
	"phoneVerified" : "Boolean",
	"emailVerified" : "Boolean",
	"status" : "Boolean",
	"urlVerifyEmail" : {
		"type" : "String",
		"index" : true
	},
	"facebook" : {
		"id" : "String",
		"token" : "String",
		"email" : "String",
		"firstname" : "String",
		"lastname" : "String"
	},
	"google" : {
		"id" : "String",
		"token" : "String",
		"email" : "String",
		"firstname" : "String",
		"lastname" : "String"
	},
	"properties" : [{
		"id" : "property"
	}],
	"imgFilePath" : "String",
	"createdAt" : "String",
	"updatedAt" : "String",
	"authToken" : {
		"auth" : "Boolean",
		"accessToken" : "String"
	},
	"counter" : {
		"count" : "Number",
		"countHistory" : "[Number]",
		"ttl" : "Date"
	},
	"deviceId" : "String",
	"importantMessage" : "String",
	"disponibilities" : "[String]",
	"numberOfNotificationNotAnsweredInWaiting" : "Number"
]
```

Requete HTTP | Paramètre | Description
------------ | ----------| -----------
`GET http://flat.fr/user/emailVerification/:uid/:url` | uid | l'identifiant de l'utilisateur
`GET http://flat.fr/user/resetPassword/:uid/url` | uid | l'identifiant de l'utilisateur
`POST http://flat.fr/user/create` | phonenumber | le numéro de téléphone de l'utilisateur
`GET http://flat.fr/user/confirmationPhoneCode` | code, phonenumber | le code 2fa et le numéro de téléphone de l'utilisateur
`GET http://flat.fr/user/resetPassword/:uid/url` | uid | l'identifiant de l'utilisateur
`GET http://flat.fr/user/resetPassword/:uid/url` | uid | l'identifiant de l'utilisateur
`GET http://flat.fr/user/resetPassword/:uid/url` | uid | l'identifiant de l'utilisateur
`GET http://flat.fr/user/resetPassword/:uid/url` | uid | l'identifiant de l'utilisateur
