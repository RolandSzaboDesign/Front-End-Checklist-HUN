<h1 align="center">
<br>
  <img src="https://raw.githubusercontent.com/RolandSzaboDesign/Front-End-Checklist/master/data/images/logo-front-end-checklist.jpg" alt="Front-End Checklist" width="130">
  <br>
  <br>
  Front-End Ellenőrzőlista 🇭🇺
  <br>
</h1>

<h4 align="center">A Front-End Ellenőrzőlista egy teljeskörű gyűjtemény azokról az elemekről, amiket el kell helyezzünk, és le kell teszteljünk, mielőtt a HTML weblapunkat éles környezetbe helyezzük.</h4>

<p align="center">
    <span>További Ellenőrzőlisták:</span>
    <br>
  <a href="https://github.com/thedaviddias/Front-End-Performance-Checklist#---------front-end-performance-checklist-">🎮 Front-End Teljesítmény Ellenőrzőlista (angol nyelven)</a> • <a href="https://github.com/thedaviddias/Front-End-Design-Checklist#front-end-design-checklist">💎 Front-End Design Ellenőrzőlista (angol nyelven)</a>
</p>

Az alábbi dokumentum front-end fejlesztők több évi tapasztalatán alapszik. Bizonyos kiegészítések egyéb nyílt forráskódú ellenőrzőlistákból lettek áthozva.

## Tartalomjegyzék

1. **[Fejléc](#head)**
2. **[HTML](#html)**
3. **[Betűkészletek](#webfonts)**
4. **[CSS](#css)**
5. **[Képek](#images)**
6. **[JavaScript](#javascript)**
7. **[Biztonság](#security)**
8. **[Teljesítmény](#performance-1)**
9. **[Hozzáférhetőség](#accessibility)**
10. **[Kereső Optimalizálás](#seo)**
11. **[Fordítások](#translations)**

---

## Hogyan használd?

A **Front-End Ellenőrzőlistában** szereplő tételek szinte mindegyike szükséges a legtöbb projekthez, azonban néhány tétel elhagyható. Például, egy adminisztrációs webalkalmazásnál valószínűleg nem lesz szükség RSS Hírfolyamra. Háromféle prioritási fokozatot különböztetünk meg:

* ![Alacsony][low_img] azt jelöli, hogy a tétel **ajánlott**, de bizonyos helyzetekben elhagyható.
* ![Közepes][medium_img] azt jelöli, hogy a tétel **erősen ajánlott**, és csak nagyon specifikus esetekben hagyható el. Néhány elem, ha elhagyjuk, negatív hatással lehet a teljesítményre, vagy a keresőoptimalizálásra.
* ![Magas][high_img] azt jelöli, hogy a tétel **kötelező**, vagyis semmilyen okból nem hagyható el. Ha egy ilyen elem hiányzik, az működési zavart okoz az oldalban, vagy komoly hozzáférhetőségi vagy keresőoptimalizálási problémákat okoz. A tesztelést ezeken az elemeken kell kezdeni.

A külső források közül néhányat emotikonnal láttunk el, hogy segítsen megkülönböztetni a források típusait:

* 📖: dokumentáció vagy cikk
* 🛠: online eszköz / tesztelő eszköz
* 📹: multimédia vagy videó tartalom

> Hozzájárulhatsz a ***Front-End Ellenőrzőlista Oldal***hoz a [README_APP fájl elolvasásával](https://github.com/thedaviddias/Front-End-Checklist/blob/master/README_APP.md), amelyben minden le van írva a projektről.

---

## Fejléc

> **Megjegyzés:** Íme, [egy lista minden elemről](https://github.com/joshbuchea/HEAD), ami egy HTML dokumentum fejlécébe (`<head>`) kerülhet.

### Meta tag

* [ ] **Doctype:** ![Magas][high_img] A Doctype HTML5-re van állítva, és minden HTML oldal tetején szerepel.

```html
<!doctype html> <!-- HTML5 -->
```

> * 📖 [A karakterkódolás meghatározása - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding) `angol nyelven`

*Az alábbi 2 meta tagnek (Charset és Viewport) legelöl kell szerepelnie a head-ben.*

* [ ] **Karakterkódolás:** ![Magas][high_img] A karakterkészlet (UTF-8) megfelelően van deklaráva.

```html
<!-- A dokumentum karakterkódolásának beállítása -->
<meta charset="utf-8">
```

* [ ] **Viewport:** ![Magas][high_img] A viewport megfelelően van deklarálva.

```html
<!-- Viewport a reszponzív web designhoz -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

* [ ] **Oldal Címe:** ![Magas][high_img] Minden oldalon szerepel cím, lehetőleg egyedi. (Keresőoptimalizálás: A Google kiszámolja a pixel-szélességét a megadott címnek, és körülbelül 472 és 482 pixel között levágja azt. Az átlagos, még látható címhosszúság így körülbelül 55 karakterre jön ki).

```html
<!-- A dokumentum címe -->
<title>Az oldalunk címe kevesebb, mint 55 karakterben</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) `angol nyelven`
> * 🛠 [Keresésitalálat-eredmény generátor](https://www.sistrix.com/serp-snippet-generator/) `angol nyelven`

* [ ] **Meta Leírás:** ![Magas][high_img] Minden oldalon szerepel meta leírás, amely egyedi, és nem hosszabb 150 krakternél.

```html
<!-- Meta leírás -->
<meta name="description" content="Az oldalunk leírása kevesebb, mint 150 karakter hosszúságban.">
```

> * 📖 [Meta Leírás - HTML - MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_an_author_and_description) `angol nyelven`

* [ ] **Böngészőikonok:** ![Közepes][medium_img] Minden böngészőikon el van készítve, és rendesen megjelenik. Ha csak egyetlen `favicon.ico` fájlunk van, tegyük azt az oldal gyökérkönyvtárába. Normál esetben nem szükséges extra kód ennek felismertetéséhez, azonban bevett szokás az alábbi példát felhasználni. Manapság **PNG formátum ajánlott** az `.ico` formátum helyett (Méret: 32×32px).

```html
<!-- Normál böngészőikon -->
<link rel="icon" type="image/x-icon" href="https://pelda.hu/favicon.ico">
<!-- Javasolt böngészőikon formátum -->
<link rel="icon" type="image/png" href="https://pelda.hu/favicon.png">
```

> * 🛠 [Favikon Generátor](https://www.favicon-generator.org/) `angol nyelven`
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/) `angol nyelven`
> * 📖 [Favikon Puska](https://github.com/audreyr/favicon-cheat-sheet) `angol nyelven`
> * 📖 [Favikonok, Touch Ikonok, Tile Ikonok, stb. Melyikre van szükségünk? - CSS Tricks](https://css-tricks.com/favicon-quiz/) `angol nyelven`
> * 📖 [PNG favikonok - caniuse](https://caniuse.com/#feat=link-icon-png) `angol nyelven`

* [ ] **Apple Webalkalmazás Metaadatok:** ![Alacsony][low_img] Az Apple-féle meta tagek be vannak állítva.

```html
<!-- Apple Touch Ikon (legalább 200×200px) -->
<link rel="apple-touch-icon" href="/custom-icon.png">

<!-- Teljes képernyős megjelenés engedélyezése -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- Státuszsáv Stílusa (A lehetséges értékekért ld. alább: Támogatott Meta Tagek) -->
<!-- Nincs hatással, ha az előző meta tag hiányzik -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
```

> * 📖 [Webalkalmazások Beállítása](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html) `angol nyelven`
> * 📖 [Támogatott Meta Tagek](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html) `angol nyelven`

- [ ] **Windows Csempék:** ![Alacsony][low_img] A Windows-féle csempék megvannak és be vannak linkelve.

```html
<!-- Microsoft Csempék -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

A minimum elvárt XML kód a `browserconfig.xml` fájlban a következő:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Böngésző beállítási sémák referenciája](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx) `angol nyelven`

* [ ] **Canonical:** ![Közepes][medium_img] Használjuk a `rel="canonical"`-t, hogy megelőzzük a duplikált tartalmat.

```html
<!-- Segít megelőzni az ismételt tartalmakat -->
<link rel="canonical" href="http://pelda.hu/2020/06/a-legujabb-cikkunk.html">
```

> * 📖 [Használjunk Canoninal URL-eket - Search Console Segítség - Google Támogatás](https://support.google.com/webmasters/answer/139066?hl=en) `angol nyelven`
> * 📖 [5 gyakori rel=canonical hiba - Google Webmester Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html) `angol nyelven`

### HTML tagek

* [ ] **Nyelv attribútum:** ![Magas][high_img] A `lang` attribútum be van állítva az adott oldal megfelelő nyelvére a html tagen.

```html
<html lang="en">
```

* [ ] **Szövegirány attribútum:** ![Közepes][medium_img] A szövegirány fel van tüntetve a html tagen (Más HTML tageken is használható).

```html
<html dir="ltr">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir) `angol nyelven`

* [ ] **Más nyelv:** ![Alacsony][low_img] A jelenlegi oldalon használt nyelv azonosítója fel van tüntetve az alternate tagben.

```html
<link rel="alternate" href="https://es.pelda.hu/" hreflang="es">
```

* [ ] **x-default:** ![Alacsony][low_img] A weboldalunk azon lapjának linkje, ahol ki lehet választani az oldalunk nyelvét.

```html
<link rel="alternate" href="https://pelda.hu/" hreflang="x-default" />
```

> * 📖 [x-default - Google](https://webmasters.googleblog.com/2013/04/x-default-hreflang-for-international-pages.html) `angol nyelven`


* [ ] **Feltételes megjegyzések:** ![Alacsony][low_img] Internet Explorer-specifikus feltételes megjegyzések, amennyiben szükségünk van rájuk.

> * 📖 [A feltételes megjegyzésekről (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx) `angol nyelven`

* [ ] **RSS hírfolyam:** ![Alacsony][low_img] Ha a weboldalunk egy blog, vagy cikkeket tartalmaz, akkor adjunk meg RSS hivatkozást.

* [ ] **Kritikus CSS:** ![Közepes][medium_img] A Kritikus CSS egy olyan kódrészlet, amely az oldal először látható, ún. "hajtásvonal feletti részének" megjelenítéséhez szükséges. A normál CSS hívások előtt szerepel, `<style></style>` tagek között, egy sorba lecsökkentve (minify-olva).

> * 🛠 [Critical - Addy Osmani - GitHub](https://github.com/addyosmani/critical) ezt tudja automatizálni. `angol nyelven`

* [ ] **CSS sorrend:** ![Magas][high_img] Minden CSS fájlt előbb töltünk be a JavaScript fájloknál a `<head>`-ben (Kivétel akkor, ha néhány JS fájlnak a fejlécben kell futnia és aszinkron módon töltjük be őket).

### Közösségi oldalak meta adatai

Vizualizálva készíthetünk közösségi meta adatokat a [Meta Tags](https://metatags.io/) segítségével.

A ***Facebook Open Graph*** és ***Twitter Kártyák*** minden weboldal számára erősen ajánlottak. A többi közösségi oldalra akkor érdemes külön adatokat megadni, ha kimondottan ezeken az oldalakon szeretnénk célzott megjelenést.

* [ ] **Facebook Open Graph:** ![Alacsony][low_img] Minden Facebook Open Graph (OG) adat le van tesztelve, egyik sem hiányzik, és nem tartalmaznak hibás információt. A képek minimum mérete 600×315 pixel legyen, de az ajánlott méret 1200×630 pixel.

> **Megjegyzés:** Az `og:image:width` és `og:image:height` tulajdonságokkal megadhatjuk az internetes robotok számára a képünk méretét, így azok azonnal elkezdhetik megjeleníteni a képünket; nem kell előtte letölteniük és feldolgozniuk annak méretét.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://pelda.hu/oldal.html">
<meta property="og:title" content="Tartalom Címe">
<meta property="og:image" content="https://pelda.hu/kep.jpg">
<meta property="og:description" content="Ide jön a leírás">
<meta property="og:site_name" content="Weboldal Neve">
<meta property="og:locale" content="hu_HU">
<!-- Az alábbi tagek opcionálisak, de ajánlottak -->
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
```

> * 📖 [Megosztási Útmutató Webmestereknek](https://developers.facebook.com/docs/sharing/webmasters/) `angol nyelven`
> * 📖 [Megosztás - Bevett Szokások](https://developers.facebook.com/docs/sharing/best-practices/) `angol nyelven`
> * 🛠 Teszteljük oldalunkat a [Facebook OG teszterrel](https://developers.facebook.com/tools/debug/) `angol nyelven`

* [ ] **Twitter Kártya:** ![Alacsony][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@oldalunk_fiokjanak_neve">
<meta name="twitter:creator" content="@sajat_fiokunk_neve">
<meta name="twitter:url" content="https://pelda.hu/oldal.html">
<meta name="twitter:title" content="Tartalom Címe">
<meta name="twitter:description" content="Tartalom leírása kevesebb, mint 200 karakterben">
<meta name="twitter:image" content="https://pelda.hu/kep.jpg">
```

> * 📖 [Bevezetés a Kártyákba — Twitter Fejlesztők](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started) `angol nyelven`
> * 🛠 Teszteljük oldalunkat a [Twitter kártya validátorral](https://cards-dev.twitter.com/validator) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## HTML

### Bevett szokások

* [ ] **HTML5 Szemantikus Elemek:** ![Magas][high_img] A HTML5 szemantikus elemeit (header, section, footer, main...) a szemantikai jelentésüknek megfelelően használjuk.

> * 📖 [HTML Referencia](http://htmlreference.io/) `angol nyelven`

* [ ] **Hibaoldalak:** ![Magas][high_img] A 404 és 5xx kódú hibaoldalak léteznek. Ne felejtsük, hogy az 500-as hibaoldalak CSS-ét integrálnunk kell, mert a weboldalunk nem tud fájl-lekérést végezni szerverhiba esetén.

* [ ] **Noopener:** ![Közepes][medium_img] Ha külső oldalra mutató linkeket használunk a `target="_blank"` segítségével, adjuk a linkhez a `rel="noopener"` attribútumot, hogy megelőzzük a "tabnabbing" adathalász támadásokat. Ha szükséges a Firefox régebbi verzióit is támogatni, használjuk az alábbi kódot: `rel="noopener noreferrer"`.

> * 📖 [A rel=noopener bemutatása](https://mathiasbynens.github.io/rel-noopener/) `angol nyelven`

* [ ] **Kommentek eltávolítása:** ![Alacsony][low_img] Távolítsuk el a szükségtelen kódot, mielőtt éles környezetbe helyezzük a weboldalunkat.

### HTML tesztelés

* [ ] **W3C előírásoknak megfelelés:** ![Magas][high_img] Teszteljünk minden oldalt a W3C validátorral, hogy felismerjük a lehetséges problémákat a HTML kódban.

> * 🛠 [W3C Validátor](https://validator.w3.org/) `angol nyelven`

* [ ] **HTML Lint:** ![Magas][high_img] Használhatunk külső eszközöket a kódminőségünk konzisztensen tartására és a hibák kiküszöbölésére.

> * 🛠 [Dirty markup](https://www.10bestdesign.com/dirtymarkup/) `angol nyelven`

> * 🛠 [webhint](https://webhint.io/) `angol nyelven`

* [ ] **Linkek ellenőrzése:** ![Magas][high_img] Győződjünk meg róla, hogy nincsenek rossz hivatkozások az oldalon, ellenőrizzük a 404 hibákat.

> * 🛠 [W3C Link Ellenőrző](https://validator.w3.org/checklink) `angol nyelven`

* [ ] **Hirdetésblokkoló teszt:** ![Közepes][medium_img] Ellenőrizzük, hogy a weboldal helyesen jeleníti-e meg a tartalmat akkor is, ha a hirdetésblokkoló be van kapcsolva (Mutathatunk egy üzenetet a felhasználóinknak, hogy kapcsolják ki a hirdetésblokkolójukat az oldalunkon).

> * 📖 [Használj AdBlockert a Fejlesztő Környezetedben](https://andreicioara.com/use-adblocking-in-your-dev-environment-48db500d9b86) `angol nyelven`


**[⬆ vissza a tetejére](#table-of-contents)**

---

## Betűkészletek

> **Megjegyzés:** Külső betűkészletek használata olyan jelenséget okozhat, hogy a weboldalunkon lévő szöveg egy pillanatra eltűnik vagy stilizálatlanul jelenik meg (Flash Of Invisible Text/Flash Of Unstyled Text). Legyenek beállítva tartalék betűkészletek, amíg a külső források nem töltődnek be.
> * 📖 [Google Technikai Szempontok Betűkészletekhez](https://developers.google.com/fonts/docs/technical_considerations) `angol nyelven`

* [ ] **Betűkészlet formátumok:** ![Magas][high_img] A WOFF, WOFF2 és TTF formátumokat minden modern böngésző támogatja.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff). `angol nyelven`
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2). `angol nyelven`
> * 📖 [TTF/OTF - TrueType és OpenType betűkészlet támogatás](https://caniuse.com/#feat=ttf) `angol nyelven`
> * 📖 [A @font-face használata - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/) `angol nyelven`

* [ ] **Betűkészlet mérete:** ![Magas][high_img] Győződjünk meg, hogy a betűkészletek nem haladják meg a 2 MB-ot, az összes betűvariációt beleértve.

* [ ] **Web Font Loader:** ![Alacsony][low_img] A Typekit betűkészlet-loaderével kézben tarthatjuk a `@font-face`-es betűkészletek betöltődését

> * 🛠 [Typekit Web Font Loader](https://github.com/typekit/webfontloader) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## CSS

> **Megjegyzés:** Használjuk referenciának a legtöbb frontend fejlesztő által követett [CSS guidelines](https://cssguidelin.es/) és [Sass Guidelines](https://sass-guidelin.es/) oldalakat. Ha nem ismerünk egy CSS tulajdonságot, látogassuk meg a [CSS Reference](http://cssreference.io/) oldalt. A konzisztencia jegyében használjuk a [Code Guide](http://codeguide.co/) oldalt. Ezen linkek mindegyike angol nyelven érhető el.

* [ ] **Reszponzív Web Design:** ![Magas][high_img] A weboldal reszponzív web designra épül.
* [ ] **CSS Print:** ![Közepes][medium_img] Biztosítsunk nyomtatási stíluslapot minden oldalhoz.
* [ ] **CSS Előfeldolgozók:** ![Alacsony][low_img] Használjunk CSS előfeldolgozót a könnyebb fejlesztés érdekében: (e.g [Sass](http://sass-lang.com/), [Less](http://lesscss.org/), [Stylus](http://stylus-lang.com/)).
* [ ] **Egyedi ID:** ![Magas][high_img] Ha használunk CSS azonosítókat, győződjünk meg, hogy mindegyik egyedi.
* [ ] **Reset CSS:** ![Magas][high_img] Nullázzuk le a CSS kódunkat egy naprakész "Reset" stíluslappal. *(CSS Keretrendszerek, mint Bootstrap vagy Foundation használata esetén a Normalize.css alapból használva van.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/) `angol nyelven`
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/) `angol nyelven`
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/) `angol nyelven`

* [ ] **JS előtag:** ![Alacsony][low_img] Minden, JavaScripthez használt azonosító vagy osztály **js-** előtaggal van ellátva, és nem vonatkozik rá semmilyen stílus a CSS-ben.

```html
<div id="js-slider" class="my-slider">
<!-- Vagy -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Beágyazott vagy Sorközi CSS:** ![Magas][high_img] Óvakodjunk a sorközi, vagy `<style>` tagek közé beágyazott CSS-től. Csak a legszükségesebb esetben használjuk, például kritikus CSS-hez, vagy `background-image`-ekhez.
* [ ] **Böngésző Előtagok:** ![Magas][high_img] A CSS böngésző előtagok megfelelően vannak legenerálva a projektünk böngészőkompatibilitási elvárásainak megfelelően.

> * 🛠 [Autoprefixer](https://autoprefixer.github.io/) `angol nyelven`

### Teljesítmény

- [ ] **Összefűzés:** ![Magas][high_img] Legyen a CSS egységek egy fájlba összegyúrva *(Nem igaz HTTP/2 esetén)*.
- [ ] **Minifikálás:** ![Magas][high_img] Legyen minden CSS fájl minifikálva.
- [ ] **Non-blocking:** ![Közepes][medium_img] A CSS fájloknak a nem szabad a renderelést blokkolónak lenniük.

> * 📖 [loadCSS - Filament Group](https://github.com/filamentgroup/loadCSS) `angol nyelven`
> * 📖 [Példa a CSS preload-ra a loadCSS segítségével](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf) `angol nyelven`

- [ ] **Nem Használt CSS:** ![Alacsony][low_img] Távolítsuk el a nem használt CSS-t.

> * 🛠 [UnCSS Online](https://uncss-online.com/) `angol nyelven`
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss) `angol nyelven`
> * 🛠 [PurgeCSS](https://github.com/FullHuman/purgecss) `angol nyelven`
> * 🛠 [Chrome DevTools Lefedettség](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage) `angol nyelven`


### CSS tesztelés

* [ ] **Stylelint:** ![Magas][high_img] Ne legyen a CSS vagy SCSS fájlokban hiba.

> * 🛠 [stylelint, egy CSS linter](https://stylelint.io/) `angol nyelven`
> * 📖 [Sass útmutató](https://sass-guidelin.es/) `angol nyelven`

* [ ] **Reszponzív web design:** ![Magas][high_img] Minden oldal legyen letesztelve a következő töréspontokon: 320px, 768px, 1024px (az analitikánktól függően ezek az értékek eltérhetnek).

* [ ] **CSS helyesség:** ![Közepes][medium_img] Javítsuk a Validátor által írt CSS hibákat.

> * 🛠 [CSS Validátor](https://jigsaw.w3.org/css-validator/) `angol nyelven`

* [ ] **Asztali Böngészők:** ![Magas][high_img] Minden oldalt teszteljünk le az aktuális modern asztali böngészőkkel (Safari, Firefox, Chrome, Internet Explorer, Edge...).
* [ ] **Mobil Böngészők:**  ![Magas][high_img] Minden oldalt teszteljünk le az aktuális modern mobil böngészőkkel (Android natív böngésző, Chrome, Safari...).
* [ ] **Operációs Rendszer:**  ![Magas][high_img] Minedn oldalt teszteljünk le a modern operációs rendszereken (Windows, Android, iOS, Mac...).

- [ ] **Design pontosság:** ![Alacsony][low_img] A projekttől vagy a kreatívok minőségétől függően, elképzelhető, hogy üzleti üzelti igény a pixelpontos megvalósítás. Léteznek eszközök, amelyek segíthetnek ebben.

> [Pixel Perfect - Chrome bővítmény](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en) `angol nyelven`

* [ ] **Szövegirány:** ![Magas][high_img] Teszteljünk le minden oldalt balról-jobbra és jobbról-balra szövegirányú nyelvekkel, ha támogatnunk kell ezeket.

> * 📖 Jobbról-balra szövegirányú appok és weboldalak készítése: 1.rész - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/) `angol nyelven`
> * 📖 Jobbról-balra szövegirányú appok és weboldalak készítése: 2.rész - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Képek

> **Notes:** For a complete understanding of image optimization, check the free ebook **[Essential Image Optimization](https://images.guide/)** from Addy Osmani.

### Best practices

* [ ] **Optimization:** ![Magas][high_img] All images are optimized to be rendered in the browser. WebP format could be used for critical pages (like Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin) `angol nyelven`
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free. `angol nyelven`
> * 🛠 Use [KeyCDN Image Processing](https://www.keycdn.com/support/image-processing) for image optimization in real time. `angol nyelven`
> * 🛠 Use [Kraken.io](https://kraken.io/web-interface) awesome alternative for both png and jpg optimization. Up to 1mb per files on free plan. `angol nyelven`
> * 🛠 [TinyPNG](https://tinypng.com/) losslessly optimises png, apng (animated png) and jpg images. Free and paid version available. `angol nyelven`
> * 🛠 [ZorroSVG](http://quasimondo.com/ZorroSVG/) jpg-like compression for transparent images using svg masking. `angol nyelven`
> * 🛠 [SVGO](https://github.com/svg/svgo) a Nodejs-based tool for optimizing SVG vector graphics files. `angol nyelven`
> * 🛠 [SVGOMG](https://jakearchibald.github.io/svgomg/) a web-based GUI version of SVGO for optimising your svgs online. `angol nyelven`


* [ ] **Picture/Srcset:** ![Közepes][medium_img] You use picture/srcset to provide the most appropriate image for the current viewport of the user.

> * 📖 [How to Build Responsive Images with srcset](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/) `angol nyelven`

* [ ] **Retina:** ![Alacsony][low_img] You provide layout images 2x or 3x, support retina display.
* [ ] **Sprite:** ![Közepes][medium_img] Small images are in a sprite file (in the case of icons, they can be in an SVG sprite image).
* [ ] **Width and Height:** ![Magas][high_img] Set `width` and `height` attributes on `<img>` if the final rendered image size is known (can be omitted for CSS sizing).
* [ ] **Alternative text:** ![Magas][high_img] All `<img>` have an alternative text which describes the image visually.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/) `angol nyelven`

* [ ] **Lazy loading:** ![Közepes][medium_img] Images are lazyloaded (A noscript fallback is always provided).

**[⬆ vissza a tetejére](#table-of-contents)**

---

## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![Magas][high_img] You don't have any JavaScript code inline (mixed with your HTML code).
* [ ] **Concatenation:** ![Magas][high_img] JavaScript files are concatenated.
* [ ] **Minification:** ![Magas][high_img] JavaScript files are minified (you can add the `.min` suffix).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources) `angol nyelven`

* [ ] **JavaScript security:** ![Magas][high_img]

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript) `angol nyelven`

* [ ] **`noscript` tag:** ![Közepes][medium_img] Use `<noscript>` tag in the HTML body if a script type on the page is unsupported or if scripting is currently turned off in the browser. This will be helpful in client-side rendering heavy apps such as React.js, see [examples](https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498).

```html
<noscript>
  You need to enable JavaScript to run this app.
</noscript>
```

* [ ] **Non-blocking:** ![Közepes][medium_img] JavaScript files are loaded asynchronously using `async` or deferred using `defer` attribute.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS) `angol nyelven`

* [ ] **Optimized and updated JS libraries:** ![Közepes][medium_img] All JavaScript libraries used in your project are necessary (prefer Vanilla Javascript for simple functionalities), updated to their latest version and don't overwhelm your JavaScript with unnecessary methods.

> * 📖 [You may not need jQuery](http://youmightnotneedjquery.com/) `angol nyelven`
> * 📖 [Vanilla JavaScript for building powerful web applications](https://plainjs.com/) `angol nyelven`

* [ ] **Modernizr:** ![Alacsony][low_img] If you need to target some specific features you can use a custom Modernizr to add classes in your `<html>` tag.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses) `angol nyelven`

### JavaScript testing

* [ ] **ESLint:** ![Magas][high_img] No errors are flagged by ESLint (based on your configuration or standards rules).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Security

### Scan and check your web site

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)

### Best practices

* [ ] **HTTPS:** ![Magas][high_img] HTTPS is used on every page and for all external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/) `angol nyelven`
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html) `angol nyelven`
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity) `angol nyelven`

* [ ] **HTTP Strict Transport Security (HSTS):** ![Közepes][medium_img] The HTTP header is set to 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/) `angol nyelven`
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) `angol nyelven`
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html) `angol nyelven`

* [ ] **Cross Site Request Forgery (CSRF):** ![Magas][high_img] You ensure that requests made to your server-side are legitimate and originate from your website / app to prevent CSRF attacks.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) `angol nyelven`

* [ ] **Cross Site Scripting (XSS):** ![Magas][high_img] Your page or website is free from XSS possible issues.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) `angol nyelven`
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html) `angol nyelven`

* [ ] **Content Type Options:** ![Közepes][medium_img] Prevents Google Chrome and Internet Explorer from trying to mime-sniff the content-type of a response away from the one being declared by the server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options) `angol nyelven`

* [ ] **X-Frame-Options (XFO):** ![Közepes][medium_img] Protects your visitors against clickjacking attacks.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options) `angol nyelven`
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034) `angol nyelven`

* [ ] **Content Security Policy:** ![Közepes][medium_img] Defines how content is loaded on your site and from where it is permitted to be loaded. Can also be used to protect against clickjacking attacks.

> * 📖 [Content Security Policy - An Introduction - Scott Helme](https://scotthelme.co.uk/content-security-policy-an-introduction/) `angol nyelven`
> * 📖 [CSP Cheat Sheet - Scott Helme](https://scotthelme.co.uk/csp-cheat-sheet/) `angol nyelven`
> * 📖 [CSP Cheat Sheet - OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html) `angol nyelven`
> * 📖 [Content Security Policy Reference](https://content-security-policy.com/) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Performance

### Best practices

- [ ] **Goals to achieve:** ![Közepes][medium_img] Your pages should reach these goals:
  - First Meaningful Paint under 1 second
  - Time To Interactive under 5 seconds for the "average" configuration (a $200 Android on a slow 3G network with 400ms RTT and 400kbps transfer speed) and under 2 seconds for repeat visits
  - Critical file size under 170Kb gzipped

> * 🛠 [Website Page Analysis](https://tools.pingdom.com) `angol nyelven`
> * 🛠 [WebPageTest](https://www.webpagetest.org/) `angol nyelven`
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter) `angol nyelven`

* [ ] **Minified HTML:** ![Közepes][medium_img] Your HTML is minified.

* [ ] **Lazy loading:** ![Közepes][medium_img] Images, scripts and CSS need to be lazy loaded to improve the response time of the current page (See details in their respective sections).

* [ ] **Cookie size:** ![Közepes][medium_img] If you are using cookies be sure each cookie doesn't exceed 4096 bytes and your domain name doesn't have more than 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265) `angol nyelven`
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies) `angol nyelven`
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/) `angol nyelven`

* [ ] **Third party components:** ![Közepes][medium_img] Third party iframes or components relying on external JS (like sharing buttons) are replaced by static components when possible, thus limiting calls to external APIs and keeping your user's activity private.

> * 🛠 [Simple sharing buttons generator](https://simplesharingbuttons.com/) `angol nyelven`

### Preparing upcoming requests

> * 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/) `angol nyelven`

* [ ] **DNS resolution:** ![Alacsony][low_img] DNS of third-party services that may be needed are resolved in advance during idle time using `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://pelda.hu">
```

* [ ] **Preconnection:** ![Alacsony][low_img] DNS lookup, TCP handshake and TLS negotiation with services that will be needed soon is done in advance during idle time using `preconnect`.

```html
<link rel="preconnect" href="https://pelda.hu">
```

* [ ] **Prefetching:** ![Alacsony][low_img] Resources that will be needed soon (e.g. lazy loaded images) are requested in advance during idle time using `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Alacsony][low_img] Resources needed in the current page (e.g. scripts placed at the end of `<body>`) in advance using `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf) `angol nyelven`

### Performance testing

* [ ] **Google PageSpeed:** ![Magas][high_img] All your pages were tested (not only the homepage) and have a score of at least 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/) `angol nyelven`
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com) `angol nyelven`
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/) `angol nyelven`
> * 🛠 [GTmetrix - Website speed and performance optimization](https://gtmetrix.com/) `angol nyelven`
> * 🛠 [Speedrank - Improve the performance of your website](https://speedrank.app/) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Accessibility

> **Notes:** You can watch the playlist [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹 `angol nyelven`

### Best practices

- [ ] **Progressive enhancement:** ![Közepes][medium_img] Major functionality like main navigation and search should work without JavaScript enabled.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8) `angol nyelven`

- [ ] **Color contrast:** ![Közepes][medium_img] Color contrast should at least pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/) `angol nyelven`

#### Headings

* [ ] **H1:** ![Magas][high_img] All pages have an H1 which is not the title of the website.
* [ ] **Headings:** ![Magas][high_img] Headings should be used properly and in the right order (H1 to H6).

> * 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) `angol nyelven`

### Semantics

- [ ] **Specific HTML5 input types are used:** ![Közepes][medium_img] This is especially important for mobile devices that show customized keypads and widgets for different types.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/) `angol nyelven`

### Form

* [ ] **Label:** ![Magas][high_img] A label is associated with each input form element. In case a label can't be displayed, use `aria-label` instead.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute) `angol nyelven`

### Accessibility testing

* [ ] **Accessibility standards testing:** ![Magas][high_img] Use the WAVE tool to test if your page respects the accessibility standards.

> * 🛠 [Wave testing](http://wave.webaim.org/) `angol nyelven`

* [ ] **Keyboard navigation:** ![Magas][high_img] Test your website using only your keyboard in a previsible order. All interactive elements are reachable and usable.
* [ ] **Screen-reader:** ![Közepes][medium_img] All pages were tested in a screen-reader (VoiceOver, ChromeVox, NVDA or Lynx).
* [ ] **Focus style:** ![Magas][high_img] If the focus is disabled, it is replaced by visible state in CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) `angol nyelven`

**[⬆ vissza a tetejére](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![Magas][high_img] Google Analytics is installed and correctly configured.

> * 🛠 [Google Analytics](https://analytics.google.com/analytics/web/) `angol nyelven`
> * 🛠 [GA Checker (and others)](http://www.gachecker.com/) `angol nyelven`

* [ ] **Headings logic:** ![Közepes][medium_img] Heading text helps to understand the content in the current page.

> * 🛠 [Tota11y, tab Headings](http://khan.github.io/tota11y/#Try-it) `angol nyelven`

* [ ] **sitemap.xml:** ![Magas][high_img] A sitemap.xml exists and was submitted to Google Search Console (previously Google Webmaster Tools).

> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/) `angol nyelven`

* [ ] **robots.txt:** ![Magas][high_img] The robots.txt is not blocking webpages.

> * 📖 [The robots.txt file](https://varvy.com/robottxt.html) `angol nyelven`
> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool) `angol nyelven`

* [ ] **Structured Data:** ![Magas][high_img] Pages using structured data are tested and are without errors. Structured data helps crawlers understand the content in the current page.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data) `angol nyelven`
> * 📖 [RDFa - Linked Data in HTML](https://rdfa.info/) `angol nyelven`
> * 📖 [JSON-LD](https://json-ld.org/) `angol nyelven`
> * 📖 [Microdata](https://www.w3.org/TR/microdata/) `angol nyelven`
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/) `angol nyelven`
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Hierarchy](http://schema.org/docs/full.html) `angol nyelven`

* [ ] **Sitemap HTML:** ![Közepes][medium_img] An HTML sitemap is provided and is accessible via a link in the footer of your website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en) `angol nyelven`

* [ ] **Pagination link tags:** ![Közepes][medium_img] Provide `rel="prev"` and `rel="next"` to indicate paginated content.

> * 🛠 [Pagination (rel="prev/next") Testing Tool](https://technicalseo.com/seo-tools/rel-prev-next/) `angol nyelven`

> * 📖 [Pagination guidelines - Google Support](https://support.google.com/webmasters/answer/1663744?hl=en) `angol nyelven`

```html
<!-- Example: Pagination link tags for page 2 of a paginated list -->
<link rel="prev" href="https://pelda.hu/?page=1">
<link rel="next" href="https://pelda.hu/?page=3">
```

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Translations

The Front-End Checklist is also available in other languages. Thanks for all translators and their awesome work!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)
* 🇻🇳 Vietnamese: [euclid1990/Front-End-Checklist](https://github.com/euclid1990/Front-End-Checklist)
* 🇹🇼 Traditional Chinese: [EngineLin/Front-End-Checklist](https://github.com/EngineLin/Front-End-Checklist)
* 🇫🇷 French: [ynizon/Front-End-Checklist](https://github.com/ynizon/Front-End-Checklist)
* 🇷🇺 Russian: [ungear/Front-End-Checklist](https://github.com/ungear/Front-End-Checklist)
* 🇹🇷 Turkish: [eraycetinay/Front-End-Checklist](https://github.com/eraycetinay/Front-End-Checklist)
* 🇩🇪 German: [xfuture603/Front-End-Checklist](https://github.com/xFuture603/Front-End-Checklist)

---

## Front-End Checklist Badge

If you want to show you are following the rules of the Front-End Checklist, put this badge on your README file!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ vissza a tetejére](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Front-End Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is automatically reflected on the [Front-End Checklist](https://frontendchecklist.io) website.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

## Support

If you have any question or suggestion, don't hesitate to use Gitter or Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Facebook](https://www.facebook.com/frontendchecklist/)
* [Twitter](https://twitter.com/thedaviddias)

## Author

**[David Dias](https://github.com/thedaviddias)**

## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](.github/CONTRIBUTING.md).
<a href="https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors"><img src="https://opencollective.com/front-end-checklist/contributors.svg?width=890" /></a>


## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/front-end-checklist#backer)]

<a href="https://opencollective.com/front-end-checklist#backers" target="_blank"><img src="https://opencollective.com/front-end-checklist/backers.svg?width=890"></a>


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/front-end-checklist#sponsor)]

<a href="https://opencollective.com/front-end-checklist/sponsor/0/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/1/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/2/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/3/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/4/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/5/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/6/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/7/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/8/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/front-end-checklist/sponsor/9/website" target="_blank"><img src="https://opencollective.com/front-end-checklist/sponsor/9/avatar.svg"></a>

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ vissza a tetejére](#table-of-contents)**

[low_img]: data/images/priority/low.svg
[medium_img]: data/images/priority/medium.svg
[high_img]: data/images/priority/high.svg
