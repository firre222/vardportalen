# Los Santos Vårdportal

Intern vårdportal för sjukvården på servern. Personalen skickar in symtom och bilder till läkare, som ställer diagnos, bokar samtal och fördelar uppdrag. Portalen har också patientöversikt, chatt och personalprofiler.

Sidan körs på GitHub Pages och sparar allt i en gratis Firebase-databas (Cloud Firestore).

## Kom igång

### 1. Skapa databasen i Firebase
1. Gå till https://console.firebase.google.com och logga in med ett Google-konto.
2. Välj **Lägg till projekt**, ge det ett namn (till exempel `lss-vardportal`) och skapa det. Google Analytics behövs inte.
3. I menyn till vänster: **Build > Firestore Database > Skapa databas**. Välj platsen `eur3 (europe-west)` och starta i **produktionsläge**.
4. Öppna fliken **Regler**, ersätt allt med innehållet i filen `firestore.rules` här i repot och tryck **Publicera**.

### 2. Koppla portalen till databasen
1. I Firebase: kugghjulet > **Projektinställningar** > **Dina appar** > ikonen `</>` (webbapp). Ge appen ett namn och registrera den. Firebase Hosting behövs inte.
2. Kopiera värdena i `firebaseConfig` (apiKey, authDomain, projectId osv.).
3. Öppna `firebase-config.js` här i repot, ersätt alla `FYLL_I` med dina värden och spara.

### 3. Slå på GitHub Pages
1. I repot: **Settings > Pages**.
2. Under **Build and deployment** väljer du **Deploy from a branch**, grenen `main` och mappen `/ (root)`. Spara.
3. Efter någon minut ligger portalen på `https://<ditt-användarnamn>.github.io/<repo-namn>/`.

### 4. Första inloggningen
1. Öppna portalen, välj fliken **Administratör** och skriv behörighetskoden.
2. Gå till **Personal** och skapa konton åt personalen.

## Bra att veta
- Inloggningen är en del av portalen och skyddar inte databasen på riktigt. Den som kan Firebase skulle kunna läsa eller ändra data direkt. Använd inga riktiga lösenord och lägg inte in riktiga personuppgifter.
- Firebase gratisnivå räcker gott för en server: 50 000 läsningar och 20 000 skrivningar per dag.
- Sidan är dold för sökmotorer.
