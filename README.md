# Pokeshadow

Mimics some game that exists for iPad (that has ads, is a native app etc.), aimed at children.

TODO:
- [x] render svg
- [x] turn image into silhouette
  - `filter: brightness(0%);`
- [x] add random letters
- [x] render letters forming name
- [x] allow guessing correct/wrong
- [x] take action on correct/wrong
- [x] show subject when correct
  - would be cool to enlargen and dissolve while moving to next level
  - or just make the corner pokemon nudge a bit, and maybe add some flair/confetti
- [ ] think about hints (enlighten silhouette after a while?) blur(10px) or brightness(15%) -> 25% looks cool
  - maybe different tokens
    - enlighten
    - blur
    - one correct letter (à la wordle)
    - a permanent token (or a level) that immediately highlights a correct guess (or accessed via consumable, one-time or one-time-per-subject)
    - clicking treasure could bring up store
- [ ] optimize for iPad
- [ ] add points, persist to localStorage
- [ ] decorate gui
  - random pokemons in the corners that squiggles a bit, tilted towards center
- [x] add favicon
- [ ] deploy to itch or fly or so
- [ ] rewrite js logic using signals, polyfill is at: https://github.com/tc39/proposal-signals
- [ ] randomize order and persist it
  - once finished, restart and bump the level
    - maybe increase the difficulty (decrease size of pokemon, add timer, make blurry etc. so that we 1) must use coins; 2) feel progress)

Acknowledgments: 

- SVGs from https://github.com/jnovack/pokemon-svg
- Favicon via https://realfavicongenerator.net
- Treasure chest icon via https://www.svgrepo.com/svg/335809/treasure-chest
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