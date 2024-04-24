# opc_vueJS2_cli
Installation via CLI (interface en ligne de commande) = permet de fournir une base au standard au projet
Conditions avoir node déjà installer
Installation du CLI = npm install -g @vue/cli
Création application = vue create <nomApplication>
A partir de là plusieurs options de configuration sont possibles pour créer le projet (version vue, lint, tests...)
Pour naviguer dans l'outil Vue CLI, vous devez utiliser :
    - les touches fléchées pour la direction
    - la touche Retour/Entrée pour choisir votre option
    - la barre d'espace pour sélectionner une option parmi les inputs de type "checkbox"
Pour accéder à l'interface vue CLI = vue ui

Archtecture principale de l'appliacation :
    <node_modules> - contient l'ensemble des dépendances de l'application.
    <public> - ce répertoire contient le favicon.ico et le fichier  index.html  de base qui serviront à générer le reste de votre application ;
    <src> - ce répertoire contient la quasi-totalité du code
    <.gitignore> - ce fichier contient une liste de fichiers et/ou de répertoires qui ne seront pas attachés à un repository.
    <package.json> - il s'agit du fichier de configuration de base de votre projet. Il comprend des métadonnées comme le nom et la version de votre projet, mais il contient également des informations essentielles comme les scripts pouvant être exécutés (comme serve, build, lint) et les dépendances requises pour votre projet :
    <serve> - il s'agit du script qui permet de lancer une environnement de développement en local,
    <build> - ce script permet de créer la version finale qui sera livrée à un client ou à l'utilisateur.
Continuons et ouvrons ensuite le répertoire <src> :
    <Assets> - il s'agit du répertoire dans lequel vous placerez les images et les autres ressources obligatoires auxquelles vous devrez peut-être faire référence dans votre application (c'est-à-dire les vidéos, les documents PDF, etc.).
    <Components> - ce répertoire contiendra les composants de notre application.
    <main.js> - c'est ici que sont définies les options de configuration plus high-level de Vue.
    <router> - fichier pour gérer les routes de notre application

Lancer l'environnement en local = npm run serve

Un composant avec l'extension <.vue> est composé de 3 blocs
    <Script> - où vit votre JavaScript
    <Template> - où vit votre HTML
    <Style> - où vit votre CSS