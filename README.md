svg from https://github.com/jnovack/pokemon-svg

TODO:
- [x] render svg
- [x] turn image into silhouette
  - `filter: brightness(0%);`
- [x] add random letters
- [ ] render letters forming name
  - getting names by numbers from https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_National_Pok%C3%A9dex_number

```javascript
document.querySelectorAll('.roundy').forEach(r => {
r.querySelectorAll('tr').forEach((t) => {
const tds = t.querySelectorAll('td');
if (tds.length === 0 || !tds[0].textContent.startsWith('#')) { return; }
b = b || {};
b[tds[0].textContent.replace(/^#0*/g, '')] = tds[2].textContent;
})
});
// then, copy b from the dev console to index.html
```

- [ ] allow guessing correct/wrong
- [ ] think about hints (enlighten silhouette after a while?) blur(10px) or brightness(15%) -> 25% looks cool
- [ ] "next" button
- [ ] persist random order + names + images
- [ ] show overview of finished things
- [ ] add points, take spent time into consideration
- [ ] decorate gui
  - random pokemons in the corners that squiggles a bit, tilted towards center
- [x] add favicon
- [ ] deploy to itch or fly or so
- [ ] rewrite js logic using signals, polyfill is at: https://github.com/tc39/proposal-signals
