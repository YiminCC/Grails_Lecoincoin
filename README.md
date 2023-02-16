# Grails_Lecoincoin
## 1.Fonctionnels
### 1.1.Backend
- Une couche de sécurité existe pour empêcher l’accès à la partie backend sans identifiants.
- Les comptes utilisateurs ont 3 rôles différents:
  - ADMIN
  - MODERATOR
  - CLIENT
- Le modèle de données permet de gérer des annonces (SaleAd) et leurs illustrations (Illustration).
- Toutes les opérations de CRUD sont disponibles sur les entités représentant 
  - Les utilisateurs
  - Les annonces  
  - Les illustrations n’a pas de gestion indépendante, elles sont simplement modifiables dans les annonces
#### 1.1.2 Étapes d’exécution
- S’identifier en tant qu'ADMIN et MODERATOR
  - Cet utilisateur a accès à la page **users et annonces**
	- Dans la page d'**index de user**, vous pouvez gérer tous les utilisateurs et les fonctions suivantes peuvent être mises en œuvre:
	  - Cliquer sur 'New user' peut créer un utilisateur.
	  - Les détails de l’utilisateur correspondant peuvent être consultés en cliquant sur le lien pour accéder à la page 'user/show'.
	  - Vous pouvez cliquer sur le bouton 'edit' pour accéder à la page 'edit'.
	  - L'utilisateur correspondant peut être supprimé en cliquant sur le bouton 'delete'.
	  - **Remarque : Les curseurs gauche/droite et haut/bas et des fonctions de pagination ont été ajoutés à cette page pour permettre aux utilisateurs de visualiser les informations complètes du tableau.**
    - Sur la page **user/create**: vous pouvez créer username, password et userrole.
    - Sur la page **user/show**: Vous pouvez voir les détails de l'utilisateur correspondant, ainsi que cliquer sur le bouton 'edit' pour modifier les informations et sur le bouton 'delete' pour supprimer.
    - Sur la page **user/edit**: Vous pouvez modifier le nom d'utilisateur, le mot de passe, ajouter une nouvelle annonce, etc.
	- **La fonction de page d'index d'annonce est similaire à la fonction de page d'accueil de l'utilisateur.**
	  - Elle peut gérer toutes les annonces, cliquer sur le lien ou le bouton correspondant, et peut réaliser les fonctions d'affichage des informations détaillées, de création d'une nouvelle annonce, de modification des informations d'annonce et de suppression d'annonce.
	- Sur la page **annonce/create**: vous pouvez créer title, description, price, illustration, is Active ou pas et author.
	- Sur la page **annonce/show**: vous pouvez voir les détails de l’utilisateur correspondant, ainsi que cliquer sur le bouton 'edit' pour modifier les informations et sur le bouton 'delete' pour supprimer.
	- Sur la page **annonce/edit**: Vous pouvez modifier le titre, la description, le prix, ajouter de nouvelles illustrations, etc.
***
- S’identifier en tant qu'CLIENT
  - Cet utilisateur a accès à la page **annonces**
	- Cet utilisateur ne peut gérer que sa propre annonce sur la page d'annonce, et les autres fonctions sont les mêmes que les autres utilisateurs.  
***

### 1.2. API REST
- Les méthodes GET / POST / PUT / PATCH et DELETE pris en charge sur les entités représentant les utilisateurs ainsi que les annonces (ressource individuelle ou collection).GET / PUT / PATCH / DELETE pour user et annonce (individuelle) et GET / POST pour users et annonces (collection).
  - Les méthodes que l'on a réalisées:
	- User (individuelle)
	  - On a fait la méthode de récupérer un utilisateur selon id de user(GET).
	  - Les deux méthodes ensuite sont modifier intégralement ou partiellement des informations d'un utilisateur(PUT, PATCH).
	  - La quatrième méthode réalisé est supprimer un utilisteur selon id de user(DELETE).
	- Users (collection)
	  - On peux récupérer une liste des utilisateurs en utilisant la méthode GET.
	  - La méthode POST, on peux ajouter un role à un nouveau user avant d'ajouter ce user.
	- Pour annonce, c'est un peu près similaire.
	- Annonce(individuelle)
	  - La méthode GET, c'est récupérer une annonce en cherchant le ID de l'annonce.
	  - PUT/PATCH, on peux modifier intégralement ou partiellement des informations d'une annonce selon ID de l'annnonce.
	  - On a aussi réalisé à supprimer une annonce en mettant ID de l'annonce.
	- Annonces (collection)
	  - Méthode GET, c'est récupérer une liste des annnonces.
	  - La méthode POST, on peux créer une nouvelle annonce avec les informations.
	- Et finalement, on a exporté la collection de tous les méthodes dans le fichier Grails_estia_22_23_api.postman_collection.json au répertoire.


