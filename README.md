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

Dans la partie script on va généralement retrouver 3 parties :
    - <Data> utilisée pour déclarer les données initiales du composant
    - <Computed> utilisée pour définir des propriétés calculées (dynamique)
    - <Methods> utilisée pour définir les méthodes ou les fonctions qui seront utilisées pour réagir aux événements ou pour effectuer des actions dans le composant

Les principaux hooks de cycle de vie dans Vue :
    - <Create> - qui représente la durée pendant laquelle le composant est en construction.
        -> beforeCreate
        -> created
    - <Mount> - qui représente le moment durant lequel le composant va être rendu sur notre page
        -> beforeMount
        -> mounted
    - <Destroy> - qui représente le moment où le composant va être retiré de la page
        -> beforeDestroyed
        -> destroyed

<$emit> est une fonction utilisée pour déclencher un événement personnalisé à partir d'un composant enfant vers son composant parent (transmission de données)
<slot> Permet d'ajouter du html dans la balise parent
    - Si besoin de plusieurs slots déclarer comme ceci dans le composant enfant :
        -> slot <slot name="nom-du-slot"></slot>
    Et comme ceci dans le composant parent :
        ->  <template v-slot:nom-du-slot>
                <h3>Exemple texte</h3>
            </template>

<Vuex> est un gestionnaire d'état et une bibliothèque pour les applications Vue.js. Il permet de créer un store centralisé.
    - Store de Vuex
        -> state est semblable à la partie data avec un système de déclaration en clé valeur
        -> getters sont vu un peu comme computer et l'équivalent de la propriété calculée.
    - On peut accéder à une donnée du store en utilisant la syntaxe {{ $store.state.nomDuState }} ou {{ $store.getters.nomDuGetters }}
    Il est également possible d'utiliser mapState ou mapGetters dans la propriété computed du composant selon les besoins via un spred operator