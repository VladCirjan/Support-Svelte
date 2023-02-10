![Logo Svelte](https://blog.engineering.publicissapient.fr/wp-content/uploads/2020/03/svelte-logo_20191220.png)

# C'est quoi Svelte ?

Svelte est un outil permettant de créer des applications Web rapides. Il est similaire aux frameworks JavaScript tels que React et Vue, qui partagent l'objectif de faciliter la création d'interfaces utilisateur interactives fluides.

Mais il y a une différence cruciale: Svelte convertit votre application en JavaScript idéal au moment de la construction, plutôt que d'interpréter le code de votre application au moment de l'exécution. Cela signifie que vous ne payez pas le coût de performance des abstractions du framework et que vous n'encourez pas de pénalité lors du premier chargement de votre application. 

Vous pouvez créer l'intégralité de votre application avec Svelte, ou vous pouvez l'ajouter progressivement à une base de code existante. Vous pouvez également expédier des composants sous forme de packages autonomes qui fonctionnent n'importe où, sans les frais généraux d'une dépendance à un framework conventionnel.

## Comprendre les composants

Dans Svelte, une application est composée d'un ou plusieurs *composants*. Un composant est un bloc de code autonome réutilisable qui encapsule HTML, CSS et JavaScript qui vont ensemble, écrits dans un fichier `.svelte`.

***L'exemple 'Hello world' dans l'éditeur de code est un composant simple :*** 

![Resultat 1](./images/screenshot1-svelte.png)

## Composants imbriquées

***Fichier*** `App.svelte` :
```html
<p>This is a paragraph.</p>

<style>
	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>
```
Il ne serait pas pratique de mettre toute votre application dans un seul composant. Au lieu de cela, nous pouvons importer des composants à partir d'autres fichiers, puis les utiliser comme si nous incluions des éléments.

Ajoutons une `<script>` balise App.svelte qui importe le fichier (notre composant) `Nested.svelte` dans notre application ...

***Fichier*** `Nested.svelte` ***(sur le screenshot il est dénommé*** `Niché.svelte` ***c'est à cause de google traduction) :***
```html
<p>This is another paragraph.</p>
```
... puis utilisez le composant `Nested` dans le balisage de l'application :

![Resultat 2](./images/screenshot2-svelte.png)

Notez également que le nom du composant `Nested` est en majuscule. Cette convention a été adoptée pour nous permettre de faire la différence entre les composants définis par l'utilisateur et les balises HTML standard.

## Balise HTML

Dans Svelte, on peut se passer des `<` et `>` et rendre de l'HTML directement dans un composant. On fait cela avec la balise spéciale `{@html ... }`

***Code de base (sans la balise) :***
```html
<script>
	let string = `this string contains some <strong>HTML!!!</strong>`;
</script>

<p>{string}</p>
```

***Code avec utilisation de la balise*** `{@html ...}` :

![Resultat 3](images/screenshot3-svelte.png)

## Faire une application

Tout d'abord, vous devrez intégrer Svelte à un outil de construction. Nous vous recommandons d'utiliser [SvelteKit](https://kit.svelte.dev/) , qui configure [Vite](https://vitejs.dev/) avec [vite-plugin-svelte](https://github.com/sveltejs/vite-plugin-svelte/) pour vous...

```bash
npm create svelte@latest myapp
```
[Guide étape par étape pour utiliser l'outil.](https://svelte.dev/blog/svelte-for-new-developers)

***Pour configurer votre éditeur de texte avec l'extension officielle de Svelte pour VS Code, executer la commande :***
```bash
ext install svelte.svelte-vscode
```


---

**NB**: *Beaucoup de copier/coller depuis le site officiel car c'est très bien expliqué et facile à comprendre. J'ai synthétiser pour aller à l'essentiel donc ce support n'est pas recommander pour quelqu'un qui n'a pas/trop peu de connaisssance en la matiére.*

*Source : https://svelte.dev/tutorial/basics*

---