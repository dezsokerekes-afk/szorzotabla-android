# Szorzótábla 6.0 – Android alkalmazás projekt

A csomag az eredeti Szorzótábla 6.0 alapján készült, ingyenes Android APK előállítására.

**Állapot:** a forrásprojekt elkészült, de ebben a környezetben Android SDK híján még nem volt lefordítható vagy valódi készüléken kipróbálható. A ZIP nem telepíthető APK.

## Mit tartalmaz?

- 1–10-es szorzótáblák, minden esetben a választott szám az első tényező.
- Teljes (100 műveletes) tábla, telefonon 2, tableten 5, széles képernyőn 10 oszloppal.
- Piros 3D-s gombok, egybefüggő világos felülettel, kompakt 5·1 típusú felirattal.
- Az eredmény csak a gomb lenyomása alatt látható, érintésre és egérrel is.
- Ki-be kapcsolható kattanó hang.
- Offline működés, nincs reklám és adatgyűjtés, az Android alkalmazás nem kér internetengedélyt.

## APK készítése ingyen GitHub Actions szolgáltatással

1. Lépj be a https://github.com oldalra, szükség esetén regisztrálj ingyen.
2. Készíts egy **Public** (nyilvános) repositoryt, például `szorzotabla-android` néven. A közzétett forráskód nyilvános lesz.
3. Bontsd ki ezt a projektet, és a repositoryban válaszd az **Add file → Upload files** lehetőséget.
4. Húzd be a kibontott projekt **tartalmát** úgy, hogy az `app` mappa és a `.github/workflows/apk.yml` a repository gyökerébe kerüljön. **Ne csak a ZIP-fájlt töltsd fel.** Ha a rejtett `.github` mappa nem kerül fel, külön töltsd fel a `apk.yml` fájlt `.github/workflows/apk.yml` útvonalra.
5. Kattints a **Commit changes** gombra.
6. Válaszd az **Actions** fület, majd az **Android APK készítése** munkafolyamatot. A `Run workflow` gombbal kézzel is indíthatod.
7. Sikeres lefutás után a munkafolyamat lapján alul, az **Artifacts** részből töltsd le a `Szorzotabla-APK` csomagot. Bontsd ki: az `app-debug.apk` lesz a telepíthető fájl.

Ha a workflow nem indul, ellenőrizd a GitHub Actions engedélyezését a repository Settings → Actions menüjében.

**Fontos:** ez tesztaláírással ellátott *debug APK*. Androidon külön engedélyezni kellhet az adott forrásból történő telepítést. A Play Protect figyelmeztetést adhat. Minden új GitHub Actions futás eltérő tesztaláírást eredményezhet, ezért új verzióra frissítés előtt szükség lehet a régi alkalmazás eltávolítására.

## Helyi fordítás modern fejlesztői gépen

Android Studio telepítése után: a projekt megnyitása, Gradle Sync, majd **Build → Build APK(s)**. A projekt Android Gradle Plugin 8.7.3 / Gradle 8.9 / JDK 17 kombinációra készült, Android API 35-tel. A Windows 7-es számítógépen nem célszerű új Android Studio telepítésével próbálkozni; az online fordítás kényelmesebb.

## Böngészőben azonnal használható

Nyisd meg az `app/src/main/assets/index.html` fájlt egy modern böngészőben. Ez előzetes webes változatként, internet nélkül is működik.

A kód saját, nyilvános függőségeket nem tartalmazó HTML/CSS/JavaScript, és natív Android WebView-t használ.
