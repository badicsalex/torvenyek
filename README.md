# Magyar törvények git repo

Ebben a git repositoryban (a továbbiakban: adattárban) a fontosabb magyar törvények (jelenleg csak a Ptk. és Btk.) érhetőek el, könnyen olvasható TXT, HTML, illetve automatikus feldolgozásra szánt JSON formátumban. Az egyes commitok az egyes törvénymódosítások hatálybalépését reprezentálják, helyes dátummal, időrendben. Így egy egyszerű "checkout" segítségével elérhető az akkor hatályos joganyag, vagy egy diff tool segítségével könnyen olvashatóak a módosítások:

![Ptk egy módosítása meld-ben](/ptk_meld.png?raw=true)

A [HTML változatok elérhetőek checkout nélkül is ezen a linken](https://stickman.hu/junk/tv/).

A projekt fő célja, hogy felkeltse a magyar mérnökök, illetve informatikával szemező jogtudósok érdeklődését azzal, hogy megmutatja, lehetséges a magyar joganyagon alkalmazni a programozásban bevált analitikai módszereket és eszközöket, és kecsegtet a számítógéppel támogatott jogi elemzés és jogalkotás lehetőségével.

Külön köszönet a [github-ra rakott Alaptörvény](https://github.com/petergerner/alaptorveny) projektnek az ihletért.

## Módszertan, megbízhatóság

Először is: ez a adattár nem hiteles, nem jogforrás, és nem jogász állította össze, csupán egy érdekesség. A használatából keletkező kárért nem vagyok felelős.

A adattár automatikusan lett generálva a [hun_law toolset](https://github.com/badicsalex/hun_law) segítségével, hiteles Magyar Közlöny kiadások nyelvi feldolgozásával.

Az eredményt összenéztem a Nemzeti Jogszabálytáron lévő verziókkal:

### Ptk.
Csupán két betű eltérés van a két verzió között:

- A 6:326. § (1) bekezdés d) pontja végén az írásjel nincs vesszőre cserélve. Ez az automatikus előállítás egy hiányossága, ami viszont nem rontja az érthetőséget.
- A 6:548. § (1) bekezdésében a "továbbá közigazgatási perben nem volt elhárítható." szöveg az NJT-n "továbbá **a** közigazgatási perben nem volt elhárítható."-ként szerepel. Ez hiba az NJT-n, ugyanis az eredeti módosító jogszabályban nincs "a".

### Btk.

- Sok helyen a pontok végén lévő írásjelek nincsenek helyesbítve
- Több felsorolásnál is máshol van vágva az utolsó elem, és a felsorolást követő szövegrész (Pl. 353. § (2) bekezdés). Ez nyelvtanilag mindenhol egyértelmű, de gépi feldolgozás esetén okozhat hibát.
- Érdekes helyzet a 282. § (3) bekezdés c) pontja, ami nem követi jól a "nyitó szöveg", "pontok", "zárószöveg" formulát, mert két pont között van egy záró szövegnek tűnő "darab", így szerintem nem felel meg a 61/2009. (XII. 14.) IRM rendelet 47. § (4) bekezdésének. Ez a generátorban úgy lett lekezelve, hogy a c) pont részének tekinti a "kapcsolatban követik el, vagy" szövegrészt.

## Kapcsolat

  Ha hibát talál ezen a repon vagy a hun_law-ban, vagy fejlesztési javaslata van, nyugodtan nyisson egy github issue-t. Ha a törvénnyel van baja, kérem keresse a Belügyminisztériumot vagy a kedvenc képviselőjét :)

Elérhető vagyok továbbá az admin kukac stickman pont hu címen.

Python programozót és fronted fejlesztőt keresek ehhez, és hasonló projektekhez.

## Szerzői jogok

Ugyan a törvényszövegek maguk valószínűleg nem tartozhatnak szerzői jog alá (és ez egy jogállamban nagyon helyes is!), ez a adattár azért több csupán a törvényszövegeknél: rendszerezve van, kiegészítve metaadatokkal, és könnyen feldolgozható formára van hozva. Így minden itt található fájl és metaadat felett, amennyire a törvény engedi, **alapvetően minden szerzői jogom fenntartom**.

Viszont: nagyon szívesen adok engedélyt a másolására, használatára, a legtöbb célra ingyenesen, csak kérem keressen meg e-mailben vagy github issue-val.

Badics Alex, 2020.10.11
