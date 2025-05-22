## Description
DevProfile est une application web développée avec Laravel 11, permettant aux utilisateurs authentifiés de créer un profil de développeur, de gérer leurs projets et compétences, et de générer un CV au format PDF. 

## Fonctionnalités
- Authentification : Inscription et connexion avec Laravel Breeze.
- Profil utilisateur : Modification du profil (nom, email, titre, bio) et affichage sur une page publique via une URL unique (/profile/username).
- Projets : Création, modification, suppression et affichage des projets (titre, description, lien optionnel).
- Compétences : Ajout, suppression et affichage des compétences.
- Génération de CV : Téléchargement d'un CV au format PDF contenant le profil, les projets et les compétences, généré avec Laravel DomPDF.
- Structure MVC : Organisation claire des modèles, contrôleurs et vues.
- Design : Interface stylisée avec Tailwind CSS.

## Prérequis
- PHP >= 8.0.2
- Composer
- MySQL
- Node.js et npm (pour Tailwind CSS)
- Laravel 11
- Git

## Installation
1. Cloner le dépôt :
   git clone https://github.com/votre-utilisateur/devprofile.git
   cd devprofile
  

2. Installer les dépendances :
  
   composer install
   npm install
  

3. Configurer l'environnement :
   - Copiez le fichier .env.example vers .env :
    
     cp .env.example .env
    
   - Configurez la connexion à la base de données MySQL dans le fichier .env :
    env
     DB_CONNECTION=MySQL
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=projectLaravel
     DB_USERNAME="root"
     DB_PASSWORD=""
    

4. Creation de projet :
  
   composer create-project laravel/laravel projectLaravel

5. Exécuter les migrations :
  
   php artisan migrate
  

6. Installer Laravel Breeze :
  
   composer require Laravel/breeze(^1.19) --dev
   php artisan breeze:install blade
   npm install && npm run build
  

7. Installer Laravel DomPDF :
  
   composer require barryvdh/Laravel-dompdf
  

8. Lancer le serveur de développement :
  
   php artisan serve
  
   Accédez à l'application via http://localhost:8000.

## Utilisation
1. Inscription/Connexion : Créez un compte ou connectez-vous via /register ou /login.
2. Gestion du profil : Modifiez votre profil (nom, email, titre, bio) depuis /profile.
3. Gestion des projets et compétences : Ajoutez, modifiez ou supprimez des projets et compétences depuis le tableau de bord (/dashboard).
4. Profil public : Consultez un profil via /profile/username.
5. Génération de CV : Téléchargez un CV PDF depuis la page de profil public en cliquant sur "Télécharger CV".

## Structure du projet
- Modèles : User, Project, Skill (avec relations Eloquent).
- Contrôleurs : DashboardController, ProfileController, ProjectController, SkillController, PublicProfileController, PDFController.
- Vues : Templates Blade pour le tableau de bord, le profil, et le CV PDF.
- Routes : Définies dans routes/web.php avec middleware auth pour sécuriser les fonctionnalités.
- Base de données : Tables users, projects, skills avec relations One-to-Many.


## Contributions
Ce projet a été réalisé en binôme :
- Membre 1 : Responsable de l'authentification, des migrations et des contrôleurs CRUD.
- Membre 2 : Responsable du design avec Tailwind CSS, de la génération de PDF et des tests.

## Ressources
- [Documentation Laravel](https://laravel.com/docs/11.x)
- [Laravel Breeze](https://laravel.com/docs/11.x/starter-kits#breeze-and-blade)
- [Laravel DomPDF](https://github.com/barryvdh/laravel-dompdf)
- [Tailwind CSS](https://tailwindcss.com/)
- [MySQL Workbench](https://www.mysql.com/products/workbench/)