HTML and CSS code guide

Golden rule
Checker tous les navigateurs (ie > 7, safari, firefox > 3.2, chrome)
Avant propos
L'utilisation de less pour organiser les fichiers est vivement recomandé Se baser sur le bootstrap de twitter est vivement recommandé twitter
HTML
HTML syntax

Utiliser les soft-tabs avec deux espaces (aucune tabulations)
Nested elements doivent être indenté de 2 espace
Toujours utilisé des double quote ("), jamais des simple
Ne jamais fermer les element simple avec un back slash
Exemple incorrecte:

<!DOCTYPE html>
<html>
<head>
<title>Page title</title>
</head>
<body>
<img src='images/company-logo.png' alt='Company' />
<h1 class='hello-world'>Hello, world!</h1>
</body>
</html>
Exemple correct :

<!DOCTYPE html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>
HTML5 doctype

Doctype à utilisé

<!DOCTYPE html>
Ordre des attributs dans le code

Toujours utiliser le même ordre de déclaration des attributs d'un élément

class
id
data-*
for|type|href
Example

<a class="" id="" data-modal="" href="">Exemple link</a>
CSS
CSS syntax

Utilisé les soft-tabs avec deux espace
Quand on groupe les selectors, les mettres chacun sur une ligne
Inclure un espace devant les incollades
Ajouter l'incollade fermente sur une nouvele ligne
Mettre un espace après chaque :
Une déclaration = un ligne
Fermer toutes les déclaration par un point virgule, même la dernière
un espace après chaque virgule des les propriétées d'une déclaration à part pour les rgba
Ne pas mettre de zéro pour les valeur inférieur à 1
les valeurs hexa sont en minuscule
Ecrire #fff au lieu de #FFFFFF
Mettre en double quote les attribut des les selectore.g., input[type="text"]
Ne pas spécifier l'unité pour les valeurs égales à 0
Exemple incorrect :

.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}
Exemple correct:

.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin: 0 0 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
Ordre des déclarations

Les déclarations doivent être regroupées par fonction

.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
Préfixe des propriétés

.selector {
  -webkit-border-radius: 3px;
     -moz-border-radius: 3px;
          border-radius: 3px;
}
Règle pr les déclaration avec ue seul propriété

Si une seul déclarartion, la mettre sur une ligne

.span1 { width: 60px; }
.span2 { width: 140px; }
.span3 { width: 220px; }

.sprite {
  display: inline-block;
  width: 16px;
  height: 15px;
  background-image: url(../img/sprite.png);
}
.icon           { background-position: 0 0; }
.icon-home      { background-position: 0 -20px; }
.icon-account   { background-position: 0 -40px; }
Ajout de commentaire pour dissocier les grand partie

Commentaires

Exemple incorrecte:

/* Modal header */
.modal-header {
  ...
}
Exemple correcte:

/* Wrapping element for .modal-title and .modal-close */
.modal-header {
  ...
}
Nom des class

minuscules, avec tiret (pas de camelCase et d'underscrore)
Eviter les raccourcis sans pour autant écrire 10 mots par classes
Exemple incorrecte:

.t { ... }
.red { ... }
.header { ... }
Exemple correcte:

.tweet { ... }
.important { ... }
.tweet-header { ... }
Selectors

Utiliser plutot des classes que les tags générique
éviter de trop encapsuler les selector
Exemple incorrecte:

span { ... }
.page-container #stream .stream-item .tweet .tweet-header .username { ... }
.avatar { ... }
Exemple correcte:

.avatar { ... }
.tweet-header .username { ... }
.tweet .avatar { ... }
Organization

Organiser le code par section est composants
Formulaires

Toujours utiliser des
pour les checkbox, si besoin d'une légende pour les oui est non par Example, encapsuler le tout ds fieldset
Images

Toujours priviliger le css aux images
Image uniquement en png et jpg
Priviliègé les sprites
Rétrocompatibilter

Pour l'utilisation des balises html5 inclure le html5shiv.js
<!-- Le HTML5 shim, for IE6-8 support of HTML5 elements -->
<!--[if lt IE 9]>
  <script src="assets/js/html5shiv.js"></script>
<![endif]-->
Javascript

Inclure les script js en bas de page
Utilisation de jquery et jquery-ui
Pour formulaire de validation utiliser jquery-validation
Pour les autre élement piocher dans twitter et select2

Utilisation de soft-tabs avec 2 espace

Utiliser le camelCase au lieu du underscore

Toujours mettre les parenthèses

Ne jamais utiliser $.get ou $.post. Utiliser $.ajax et toujours proposé un success handler et un error handler.

Utiliser $.fn.on à la place de $.fn.bind, $.fn.delegate et $.fn.live.

Penser au delegator

stocker les dom elements si besoin de les réutiliser

Exemple incorrecte:

$("p").on("click", function(){
  $(this).css('color', '#fff');
    alert($(this).text());
});
Exemple correcte:

$("p").on("click", function(){
    _this = $(this);
    _this.css('color', '#fff');
    alert(_this.text());
});
Pour les selecteur css utile uniquement au javascript les préfixé de "js-"

Aucun javascript inline

Eviter les référence à du text dans le javascript préférer de les stocker dans les callback ajax ou dans les data-attributes

Question ?
