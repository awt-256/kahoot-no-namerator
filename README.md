# kahoot-no-namerator
A few lines of code to let you choose your own name in kahoot. (Overrides the "Friendly Nickname Generator")

Run the following code in your browser's console before you enter the pin of your game.
```js
function inject(module) {
    const uuid = Math.random();
    window.webpackJsonp.push([[], {[uuid]: module}, [[uuid]]]);
  
    return uuid;
}
inject((_,__, {c: cache}) => {
    for (const i in cache) if (cache[i].exports && cache[i].exports.a && cache[i].exports.a.NAMERATOR && cache[i].exports.a.JOIN) {
        cache[i].exports.a.NAMERATOR = cache[i].exports.a.JOIN;
    }
});
```

Or, paste this into the url (or as a bookmark) of your browser.
```js
javascript:((u,i)=>webpackJsonp.push([[],{[u]:(m,e,{c})=>{for(i in c)c[i].exports&&c[i].exports.a&&c[i].exports.a.NAMERATOR&&(c[i].exports.a.NAMERATOR=c[i].exports.a.JOIN)}},[[u]]]))(Math.random());
```
