# Statut du retour, liste des codes

Chaque appel à l’API donne lieu à une réponse , retournant un code spécifique en fonction du résultat obtenu. L’analyse de ce code vous permet de vous assurer que la requête à été traité avec succès.

Tous les codes >= 400 indiquent que la requête n’a pas été traitées avec succès par nos serveurs.


Code HTTP | Message | Signification
---------- | -- | ------------
200 | OK | Requête traitée avec succès.
201 | Created | Requête traitée avec succès et création d’un document.
403 | Forbidden | Le serveur a compris la requête, mais refuse de l'exécuter.
404 | Not Found | Ressource non trouvée.
418 | I’m a teapot | « Je suis une théière »
500 | Internal Server Error | Erreur interne du serveur.
503 | Service Unavailable | Service temporairement indisponible ou en maintenance.
