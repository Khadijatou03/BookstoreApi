# BookStoreApi 📚

Une API RESTful complète pour la gestion d'une librairie en ligne, développée avec ASP.NET Core 9.0 et MongoDB.

## 📋 Description

BookStoreApi est une application web API qui permet de gérer une collection de livres via des opérations CRUD (Create, Read, Update, Delete). L'application utilise MongoDB comme base de données NoSQL pour stocker les informations sur les livres.

## 🛠️ Technologies Utilisées

- **.NET 9.0** - Framework principal
- **ASP.NET Core** - Framework API web
- **MongoDB** - Base de données NoSQL
- **MongoDB.Driver** - Driver MongoDB pour .NET
- **OpenAPI/Swagger** - Documentation API

## 🚀 Fonctionnalités

- **GET** `/api/books` - Récupérer tous les livres
- **GET** `/api/books/{id}` - Récupérer un livre par son ID
- **POST** `/api/books` - Créer un nouveau livre
- **PUT** `/api/books/{id}` - Mettre à jour un livre existant
- **DELETE** `/api/books/{id}` - Supprimer un livre

## 📦 Modèle de Données

### Book (Livre)

```json
{
  "id": "string",
  "bookName": "string",
  "price": "decimal",
  "category": "string",
  "author": "string"
}
```

## ⚙️ Configuration

### Prérequis

- .NET 9.0 SDK
- MongoDB Server
- Visual Studio 2022 ou VS Code

### Configuration de la Base de Données

La connexion à MongoDB est configurée dans le fichier `appsettings.json` :

```json
{
  "BookStoreDatabase": {
    "ConnectionString": "mongodb://localhost:27017",
    "DatabaseName": "BookStore",
    "BooksCollectionName": "Books"
  }
}
```

### Installation et Exécution

1. **Cloner le repository**
   ```bash
   git clone https://github.com/Khadijatou03/BookstoreApi.git
   cd BookstoreApi
   ```

2. **Configurer MongoDB**
   - Assurez-vous que MongoDB est installé et en cours d'exécution
   - La base de données `BookStore` sera créée automatiquement

3. **Restaurer les dépendances**
   ```bash
   dotnet restore
   ```

4. **Exécuter l'application**
   ```bash
   dotnet run
   ```

L'API sera accessible à l'adresse : `https://localhost:7xxx` ou `http://localhost:5xxx`

## 📚 Documentation API

Une fois l'application démarrée, vous pouvez accéder à la documentation interactive Swagger :
- URL : `https://localhost:7xxx/openapi/index.html`

### Exemples de Requêtes

#### Créer un livre
```http
POST /api/books
Content-Type: application/json

{
  "bookName": "Le Petit Prince",
  "price": 12.99,
  "category": "Fiction",
  "author": "Antoine de Saint-Exupéry"
}
```

#### Récupérer tous les livres
```http
GET /api/books
```

#### Récupérer un livre par ID
```http
GET /api/books/507f1f77bcf86cd799439011
```

#### Mettre à jour un livre
```http
PUT /api/books/507f1f77bcf86cd799439011
Content-Type: application/json

{
  "bookName": "Le Petit Prince (Édition Spéciale)",
  "price": 15.99,
  "category": "Fiction",
  "author": "Antoine de Saint-Exupéry"
}
```

#### Supprimer un livre
```http
DELETE /api/books/507f1f77bcf86cd799439011
```

## 🏗️ Architecture du Projet

```
BookStoreApi/
├── Controllers/
│   └── BooksController.cs     # Contrôleur API pour les livres
├── Models/
│   ├── Book.cs               # Modèle de données Book
│   └── BookStoreDatabaseSettings.cs  # Configuration DB
├── Services/
│   └── BooksService.cs       # Service de gestion des livres
├── Program.cs                # Point d'entrée et configuration
├── appsettings.json          # Configuration de l'application
└── BookStoreApi.csproj       # Fichier de projet
```

## 🔧 Développement

### Structure des Services

- **BooksService** : Service responsable des opérations CRUD sur la collection MongoDB
- **BooksController** : Contrôleur API qui expose les endpoints REST
- **BookStoreDatabaseSettings** : Configuration fortement typée pour la connexion MongoDB

### Bonnes Pratiques Implémentées

- Injection de dépendances
- Configuration fortement typée
- Async/Await pour les opérations de base de données
- Validation des modèles
- Gestion des erreurs HTTP appropriée
- Documentation OpenAPI automatique

## 🐳 Docker

Le projet est configuré pour fonctionner avec Docker. Un fichier `docker-compose.dcproj` est inclus pour faciliter le déploiement en conteneur.

## 📝 Auteur

Développé par **Khadijatou Ba**

## 📄 Licence

Ce projet est sous licence MIT.

## 🔗 Liens Utiles

- [Documentation .NET](https://docs.microsoft.com/fr-fr/dotnet/)
- [Documentation MongoDB](https://docs.mongodb.com/)
- [Documentation ASP.NET Core](https://docs.microsoft.com/fr-fr/aspnet/core/)
