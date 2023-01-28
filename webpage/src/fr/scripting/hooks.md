# Crochets

onNoteStored
------------

### Appel de méthode et paramètres
```js
/**
 * This function is called when a note gets stored to disk
 * You cannot modify stored notes, that would be a mess since
 * you are most likely editing them by hand at the same time
 *
 * @param {NoteApi} note - the note object of the stored note
 */
function onNoteStored(note);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [sur-note-open.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/on-note-opened.qml).

noteOpenedHook
--------------

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée après l'ouverture d'une note
  *
  * @param {NoteApi} note - l'objet note qui a été ouvert
  */
function noteOpenedHook (note);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [sur-note-open.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/on-note-opened.qml).

noteDoubleClickedHook
---------------------

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée après un double clic sur une note
  *
  * @param {NoteApi} note - l'objet de note sur lequel l'utilisateur a cliqué
  */
function noteDoubleClickedHook (note);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [external-note-open.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/external-note-open.qml).

insertMediaHook
---------------

Cette fonction est appelée lorsqu'un fichier multimédia est inséré dans la note actuelle.

Si cette fonction est définie dans plusieurs scripts, le premier script qui renvoie une chaîne non vide l'emporte.

### Appel de méthode et paramètres
```js
/**
 * @param fileName string le chemin du fichier du fichier multimédia source avant sa copie dans le dossier multimédia
 * @param markdownText string le texte en markdown du fichier multimédia, par exemple ![mon-image](média / mon-image-4101461585.jpg)
 * @return string le nouveau texte Markdown du fichier multimédia
 */
function insertMediaHook (fileName, markdownText);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml).

insertAttachmentHook
--------------------

Cette fonction est appelée lorsqu'un fichier de pièce jointe est inséré dans la note actuelle.

Si cette fonction est définie dans plusieurs scripts, le premier script qui renvoie une chaîne non vide l'emporte.

### Appel de méthode et paramètres
```js
/**
* @param fileName string le chemin du fichier de la pièce jointe source avant sa copie dans le dossier de la pièce jointe
* @param markdownText string le texte en Markdown du fichier joint, par exemple [my-file.txt](pièces jointes/mon-fichier-4245650967.txt)
* @return string le nouveau texte en Markdown du fichier joint
*/
function insertAttachmentHook (fileName, markdownText);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml).

insertingFromMimeDataHook
-------------------------

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée lorsque du HTML ou un fichier multimédia est collé dans une note avec `Ctrl + Maj + V`
 *
 * @param text texte de l'objet QMimeData
 * @param html HTML de l'objet QMimeData
 * @ renvoie la chaîne à insérer à la place du texte de l'objet QMimeData
 */
function insertingFromMimeDataHook (text, html);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml), [insérer-titre-avec-lien-de-github-url.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/insert-headline-with-link-from-github-url.qml) ou [note-text-from-17pm-mail.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/note-text-from-5pm-mail.qml).

handleNoteTextFileNameHook
--------------------------

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée lorsqu'une note est stockée sur le disque si
  * "Autoriser le nom du fichier de note à être différent du titre" est activé
  * dans les paramètres
  *
  * Il vous permet de modifier le nom du fichier de note
  * Gardez à l'esprit que vous devez vous soucier des noms en double!
 *
  * Renvoie une chaîne vide si le nom de fichier de la note doit
  * ne pas être modifié
  *
  * @param {NoteApi} note - l'objet note de la note stockée
  * @return {string} le nom de fichier de la note
  */
function handleNoteTextFileNameHook (note);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml) ou [nom-de-balise-d'utilisation-dans-nom-de-fichier.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/use-tag-names-in-filename.qml).

handleNoteNameHook
------------------

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée lorsque le nom de la note est déterminé pour une note
  *
  * Il vous permet de modifier le nom de la note qui est visualisée
  *
  * Renvoie une chaîne vide si le nom de la note ne doit pas être modifié
  *
  * @param {NoteApi} note - l'objet note de la note stockée
  * @return {string} le nom de la note
  */
function handleNoteNameHook (note);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml).

Ce n'est peut-être pas une bonne idée d'utiliser ce hook si le paramètre permettant d'utiliser le nom de fichier comme nom de note est actif.

handleNewNoteHeadlineHook
-------------------------

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée avant la création d'une note
 *
 * Elle vous permet de modifier le titre de la note avant sa création
 * Notez que vous devez faire attention à un nom de note unique, sinon
 * la nouvelle note ne sera pas créée, elle sera seulement présente dans la liste des notes
 *
 * Vous pouvez utiliser cette fonction pour créer des modèles de notes
 *
 * @param texte du titre qui serait utilisé pour créer le titre
 * @return {string} le titre de la note
 */
function handleNewNoteHeadlineHook(headline);
```

Vous pouvez jeter un œil à l'exemple [custom-new-note-headline.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/custom-new-note-headline.qml).

preNoteToMarkdownHtmlHook
-------------------------

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée avant la génération du code HTML Markdown d'une note
 *
 * Elle vous permet de modifier ce qui est passé au convertisseur Markdown vers HTML
 *
 * La fonction peut par exemple être utilisée dans de multiples scripts pour rendre du code (comme LaTeX math ou mermaid)
 * dans sa représentation graphique pour l'aperçu
 *
 * La note ne sera pas modifiée dans ce processus
 *
 * @param {NoteApi} note - l'objet note
 * @param {string} markdown - le Markdown qui doit être converti en HTML
 * @param {string} forExport - true si le HTML est utilisé pour une exportation, false pour l'aperçu
 * @return {string} le Markdown modifié ou une chaîne vide si rien ne doit être modifié
 */
function preNoteToMarkdownHtmlHook(note, markdown, forExport);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [preview-styling.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/preview-styling.qml).

noteToMarkdownHtmlHook
----------------------

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée lorsque le code HTML Markdown d'une note est généré
 *
 * Elle vous permet de modifier ce HTML
 * Elle est par exemple appelée avant par l'aperçu de la note
 *
 * Cette fonction peut être utilisée dans plusieurs scripts pour modifier le HTML de l'aperçu
 *
 * @param {NoteApi} note - l'objet note
 * @param {string} html - le HTML qui est doit être rendu
 * @param {string} forExport - true si le HTML est utilisé pour une exportation, false pour l'aperçu
 * @return {string} le code HTML modifié ou une chaîne vide si rien ne doit être modifié
 */
function noteToMarkdownHtmlHook(note, html, forExport);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [exemple.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/example.qml) ou [preview-styling.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/preview-styling.qml).

Veuillez vous référer à la documentation du [sous-ensemble HTML pris en charge](http://doc.qt.io/qt-5/richtext-html-subset.html) pour une liste de tous les styles CSS pris en charge.

encryptionHook
--------------

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée lorsque le texte doit être chiffré ou déchiffré
  *
  * @param text string le texte à crypter ou décrypter
  * @param password string le mot de passe
  * @param decrypt bool si un faux chiffrement est demandé, si un vrai déchiffrement est demandé
  * @return le texte déchiffré chiffré
  */
fonction encryptionHook (texte, mot de passe, décrypter);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [encryption-keybase.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/encryption-keybase.qml), [encryption-pgp.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/encryption-pgp.qml) ou [encryption-rot13.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/encryption-rot13.qml).

noteTaggingHook
---------------

Vous pouvez implémenter votre propre mécanisme de marquage de note, par exemple avec un texte spécial dans votre note comme `@ tag1`, `@ tag2`, `@ tag3`.

### Appel de méthode et paramètres
```js
/**
  * Gère le marquage des notes pour une note
  *
  * Cette fonction est appelée lorsque des balises sont ajoutées, supprimées ou renommées dans
  * une note ou les balises d'une note doivent être listées
  *
  * @param note
  * L'action @param peut être "ajouter", "supprimer", "renommer" ou "lister"
  * @param tagName nom de la balise à ajouter, supprimer ou renommer
  * @param newTagName nom de la balise à renommer si action = "renommer"
  * @return note chaîne de texte ou chaîne-liste de noms de balises (si action = "list")
  */
function noteTaggingHook (note, action, tagName, newTagName);
```

-   dès qu'un script est activé qui implémente la nouvelle fonction `noteTaggingHook` le marquage des notes sera géré par cette fonction
-   les fonctionnalités suivantes doivent fonctionner via l'interface utilisateur QOwnNotes
    -   importation initiale de balises telles que `@tag` à partir de vos notes et écrasement de votre attribution de balise actuelle
        -   vous ne perdrez pas votre arbre de balises, juste l'ancienne affectation aux notes
        -   vous pouvez toujours déplacer des balises dans d'autres balises
        -   si plus d'une balise porte le même nom dans votre arborescence de balises, le premier hit sera attribué
    -   l'ajout d'une balise à une note ajoutera la balise au texte de la note
    -   la suppression d'une étiquette d'une note supprimera l'étiquette du texte de la note
    -   la suppression des balises dans la liste des balises supprimera ces balises de votre notes
    -   renommer les balises dans la liste des balises renomme ces balises dans votre Notes
    -   le marquage en masse des notes dans la liste de notes ajoutera ces balises à votre Notes
    -   la suppression massive des balises des notes de la liste de notes supprimera ces balises de vos notes
    -   l'application déclenchera une série d'actions `ajouter` et `supprimer` pour toutes les balises sélectionnées et leurs enfants sur toutes les notes si les balises sont déplacées dans le panneau des balises

Vous voudrez peut-être jeter un coup d'œil à l'exemple [note-tagging.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/note-tagging.qml) pour implémenter votre propre mécanisme de balisage.

::: warning
Assurez-vous que votre action `liste` est vraiment rapide car elle sera exécutée pour chaque note à chaque rechargement du dossier de notes !
:::

noteTaggingByObjectHook
----------------------

De la même manière que [noteTaggingHook](#notetagginghook), vous pouvez implémenter votre propre mécanisme de balisage de note, mais vous n'êtes pas lié aux noms de balises dans la racine de l'arborescence des balises. De cette façon, vous pouvez utiliser l'intégralité de l'arborescence des balises au lieu d'une seule liste de balises.

Avec `noteTaggingByObjectHook` vous obtenez un objet `TagApi` comme paramètre, au lieu d'un nom de balise. Et comme résultat pour l'action `list`, vous devez fournir une liste d'identifiants de balises.

Cela signifie également que vous devez créer vous-même les balises manquantes pour pouvoir fournir une liste des identifiants de balises déjà existants pour l'action `list`.

### Appel de méthode et paramètres
```js
/ **
 * Gère le marquage des notes pour une note
 *
 * Cette fonction est appelée lorsque des balises sont ajoutées, supprimées ou renommées dans
 * une note ou que les balises d'une note doivent être listées
 *
 * @param note
 * L'action @param peut être "ajouter", "supprimer", "renommer" ou "lister"
 * Balise @param à ajouter, supprimer ou renommer
 * @param newTagName nom de la balise à renommer si action = "renommer"
 * @return note chaîne de texte ou liste de chaînes d'identifiants de balises (si action = "list")
 * /
function noteTaggingByObjectHook(note, action, tag, newTagName);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [note-tagging-by-object.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/note-tagging-by-object.qml) pour implémenter votre propre mécanisme de balisage.

autocompletionHook
------------------

Vous pouvez renvoyer une liste de chaînes à ajouter à la liste de saisie semi-automatique lorsque la saisie semi-automatique est invoquée (par exemple en appuyant sur <kbd>Ctrl + Espace</kbd>).

### Appel de méthode et paramètres
```js
/**
 * Appelle la fonction autocompletionHook pour tous les composants de script
 * Cette fonction est appelée lorsque l'auto-complétion est invoquée dans une note
 *
 * @return QStringListe de texte pour la liste de saisie semi-automatique
 */
function callAutocompletionHook();
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [autocompletion.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/autocompletion.qml).

websocketRawDataHook
--------------------

Ce hook est appelé lorsque des données sont envoyées depuis l'extension de navigateur QOwnNotes Web Companion via le menu contextuel du navigateur Web.

### Appel de méthode et paramètres
```js
/**
 * @param requestType peut être "page" ou "selection"
 * @param pageUrl l'URL de la page Web sur laquelle la demande a été effectuée
 * @param pageTitrer le titre de la page Web où la demande a été faite
 * @param rawData les données qui ont été transmises, HTML pour requestType "page" ou texte brut pour requestType "selection"
 * @param screenshotDataUrl l'URL des données de la capture d'écran si la page Web où la demande a été faite
 * @return true si les données ont été gérées par un hook
 */
function callHandleWebsocketRawDataHook (requestType, pageUrl, pageTitle, rawData, screenshotDataUrl);
```

Vous voudrez peut-être jeter un coup d'œil aux exemples [websocket-raw-data-new-note.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/websocket-raw-data-new-note.qml) et [websocket-raw-data-selection-in-note.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/websocket-raw-data-selection-in-note.qml).

onDetachedProcessCallback
-------------------------

Ce hook est appelé lorsqu'un thread de script de [startDetachedProcess](methods-and-objects.html#starting-an-external-program-in-the-background) est exécuté.

### Appel de méthode et paramètres
```js
/**
  * Cette fonction est appelée lorsqu'un thread de script est terminé.
 * Astuce: thread[1]==0 aide à déterminer si un lot de processus démarrés pour un certain identifiant est terminé.
 *
 * @param {QString} callbackIdentifier - l'identifiant fourni lors de l'appel de startDetachedProcess ()
 * @param {QString} resultSet - le résultat du processus
 * @param {QVariantList} cmd - l'ensemble du tableau de commandes [0-executablePath, 1-parameters, 2-exitCode]
 * @param {QVariantList} thread - le tableau d'information sur les threads [paramètre de rappel passé à 0, 1 threads restants pour cet identifiant]
 */
function onDetachedProcessCallback (callbackIdentifier, resultSet, cmd, thread);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [callback-example.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/callback.qml).

windowStateChangedHook
--------------

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée après le déclenchement d'un événement WindowStateChange
 *
 * @param {QString} windowState - le nouvel état de la fenêtre, la valeur du paramètre peut être "minimized", "maximized", "fullscreen", "active" ou "nostate"
 */
function windowStateChangedHook (windowState);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [window-state-changed.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/window-state-changed.qml).

workspaceSwitchedHook
----------------------

Ce crochet est appelé quand il y a bascule entre les flux de travail.

### Appel de méthode et paramètres
```js
/**
 * Cette fonction est appelée quand il y a bascule entre les flux de travail
 *
 * @param oldUuid uuid actuel de l'espace de travail
 * @param newUuid nouvel uuid de l'espace de travail
 */
function workspaceSwitchedHook(oldUuid, newUuid);
```

Vous voudrez peut-être jeter un coup d'œil à l'exemple [websocket-raw-data-new-note.qml](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples/workspaces.qml).
