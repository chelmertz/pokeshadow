# Pokeshadow

Mimics some game that exists for iPad (that has ads, is a native app etc.), aimed at children.

TODO:
- [x] render svg
- [x] turn image into silhouette
  - `filter: brightness(0%);`
- [x] add random letters
- [x] render letters forming name
- [x] allow guessing correct/wrong
- [ ] take action on correct/wrong
- [ ] show subject when correct
  - would be cool to enlargen and dissolve while moving to next level
  - or just make the corner pokemon nudge a bit, and maybe add some flair/confetti
- [ ] think about hints (enlighten silhouette after a while?) blur(10px) or brightness(15%) -> 25% looks cool
  - maybe different tokens
    - enlighten
    - blur
    - one correct letter (à la wordle)
- [ ] "next" button
- [ ] persist random order + names + images
- [ ] show overview of finished things
- [ ] add points, take spent time into consideration
- [ ] decorate gui
  - random pokemons in the corners that squiggles a bit, tilted towards center
- [x] add favicon
- [ ] deploy to itch or fly or so
- [ ] rewrite js logic using signals, polyfill is at: https://github.com/tc39/proposal-signals

Acknowledgments: 

- SVGs from https://github.com/jnovack/pokemon-svg
- Favicon via https://realfavicongenerator.net
- Pokémon names and numbers from https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_National_Pok%C3%A9dex_number - fetched using the js below in a dev console

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