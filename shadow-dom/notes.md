
Infos
  https://developers.google.com/web/fundamentals/getting-started/primers/shadowdom

Specs
  https://w3c.github.io/webcomponents/spec/shadow/

Polymer
  new in v2
    https://www.polymer-project.org/2.0/docs/about_20#shadow-dom-v1
  what is shady DOM
    http://stackoverflow.com/questions/37691135/whats-the-difference-between-polymers-shady-dom-vs-shadow-dom
    https://www.polymer-project.org/1.0/blog/shadydom#shadow-dom-is-awesome-why-is-there-a-shady-dom

Polyfill
  https://github.com/webcomponents/webcomponentsjs


Old ways
  - BEM (Block / Element / Modifier) pour CSS
    http://getbem.com/introduction/
  - CSS Modules
    https://github.com/css-modules/css-modules
  -

Exemple code
  - https://gist.github.com/ebidel/2d2bb0cdec3f2a16cf519dbaa791ce1b

Light DOM -> partie du shadow DOM qui est laissée à l'utilisateur (ce que l'on va mettre dans les slots)

La plupart des Events sont propagés dans le shadowDOM : hover, drag / drop events, keyboard / mouse events...

Les événements customs ne sont pas propagés en dehors du shadow DOM, sauf si spécifié par "composed: true" :
selectTab() {
  const tabs = this.shadowRoot.querySelector('#tabs');
  tabs.dispatchEvent(new Event('tab-select', {bubbles: true, composed: true}));
}


Certains styles sont hérités, pour les reset il faut faire "all: initial"

```
<style>
  :host {
    all: initial; /* 1st rule so subsequent properties are reset. */
  }
</style>
```

Création du contenu par <template>
https://developers.google.com/web/fundamentals/getting-started/primers/customelements


CSS containment
https://developers.google.com/web/updates/2016/06/css-containment
