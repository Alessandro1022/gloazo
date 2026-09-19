# Golazo

En flappy-stil fotbollsmatch — sparka bollen genom malen istallet for att flyga mellan pelare.
Ren HTML/CSS/JS, ingen build, inga beroenden.

## Kora lokalt
Oppna `index.html` direkt i webblasaren, eller kor en lokal server:

```
npx serve .
```

## Deploya pa GitHub
```
git init
git add .
git commit -m "Golazo v1"
git branch -M main
git remote add origin https://github.com/<ditt-anvandarnamn>/golazo.git
git push -u origin main
```

## Deploya pa Vercel
1. Ga till vercel.com och logga in (kan anvanda GitHub-kontot).
2. "Add New Project" -> valj golazo-repot.
3. Framework preset: "Other" (statisk sajt, ingen build kravs).
4. Deploy. Klart pa nagra sekunder — du far en lank typ `golazo.vercel.app`.

Varje push till `main` deployar automatiskt om.

## Mot App Store (iOS)
Det har ar en webbsida, inte en native-app, sa App Store kraver ett extra steg:
paketera sidan med **Capacitor** (capacitorjs.com) som wrappar `index.html` i en
riktig iOS-app-shell. Det kravs dessutom:
- En Mac med Xcode installerat
- Ett Apple Developer-konto (99 USD/ar)
- Riktiga app-ikoner och en launch screen

Grundstegen (nar du har en Mac):
```
npm init -y
npm install @capacitor/core @capacitor/cli @capacitor/ios
npx cap init golazo se.aetossystems.golazo
npx cap add ios
npx cap copy
npx cap open ios
```
Sedan bygger och skickar du in appen fran Xcode som vilken annan iOS-app.

## Filer
- `index.html` — hela spelet (HTML, CSS, JS i en fil)
- `vercel.json` — Vercel-konfiguration
- `package.json` — metadata, inga byggsteg kravs
