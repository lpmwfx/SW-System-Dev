# 🚀 AI-Assisted Project Build Guide for SagasWeave

Denne guide beskriver, hvordan man bygger et AI-assisteret projekt ved hjælp af SagasWeave techstack. Denne tilgang er designet til at maksimere AI-assistance og minimere traditionel kodeudvikling, primært gennem Markdown-baseret indhold og CLI-værktøjer.

## ⚠️ Vigtig Bemærkning om Optimalitet

Denne techstack er yderst specialiseret og optimeret til AI-drevet narrativ og indholdsgenerering. Den er **mindre optimal** for projekter, der kræver:
*   Komplekse, interaktive brugergrænseflader, der ikke let kan abstraheres til Markdown.
*   Tung grafisk udvikling eller spil med avanceret 3D-grafik.
*   Projekter, hvor finmasket kontrol over UI-komponenter og interaktioner er afgørende, og hvor en traditionel UI-IDE er foretrukket.
*   Projekter, der kræver realtidsydelse eller lav-niveau systemadgang, som ikke kan opnås via React Native/Tauri.

Overvej nøje, om denne tilgang passer til dit projekts specifikke behov.

## 🛠️ 1. Miljøopsætning

Før du starter, skal du sikre dig, at dit udviklingsmiljø er korrekt konfigureret.

### Nødvendige Værktøjer:
*   **Node.js**: LTS-version (anbefales).
*   **Bun**: En hurtig JavaScript-runtime, bundler, transpiler og package manager.
*   **Git**: Til versionskontrol.
*   **En Teksteditor**: F.eks. VSCode, Textastic (iPad) eller Obsidian, da de understøtter Markdown godt.

### Installation:
1.  **Installer Node.js**: Følg instruktionerne på [nodejs.org](https://nodejs.org/).
2.  **Installer Bun**: `curl -fsSL https://bun.sh/install | bash`
3.  **Klon SagasWeave Repository**:
    ```bash
    git clone [URL til SagasWeave repo]
    cd SagasWeaveProject/SW-System
    ```
4.  **Installer Afhængigheder**:
    ```bash
    bun install
    ```

## 📝 2. Forstå Markdown-Strukturen

Kerneprincippet i SagasWeave er, at alt indhold og logik defineres i Markdown-filer (`.md`) ved hjælp af specifikke `::TAG` syntakser.

### Nøgle-Tags:
*   `::SCENE`: Definerer narrative scener eller sektioner.
*   `::UI`: Beskriver brugergrænsefladekomponenter og deres struktur.
*   `::AI`: Indeholder instruktioner eller prompts til AI-modeller for indholdsgenerering, fejlkorrektion, etc.
*   `::STATE`: Definerer applikationens tilstandsvariabler.
*   `::LOGIC`: Indeholder simpel logik, der kan fortolkes af systemet.

### Eksempel på Markdown-Fil:
```markdown
# Min Første Scene

::SCENE::start
Velkommen til eventyret! Du står ved en gaffel i vejen.

::UI::choice
- Gå til venstre::goto::left_path
- Gå til højre::goto::right_path

::AI::generate_description
Generer en kort, mystisk beskrivelse af venstre sti.

::SCENE::left_path
Du vælger venstre sti. Den er mørk og fuld af spindelvæv.

::STATE::player_location=forest_path
```

## ⚙️ 3. Kompilering af Projektet

SagasWeave bruger CLI-værktøjer til at parse dine Markdown-filer og generere eksekverbar kode (TypeScript/TSX).

### Kompileringskommando:
```bash
npx sw-compile md/
```
Denne kommando vil:
1.  Parse alle `.md` filer i `md/` mappen.
2.  Splitte indholdet baseret på `::TAG` syntaks.
3.  Validere strukturen, navngivningen og linking.
4.  Generere `.ts` og `.tsx` filer i de relevante output-mapper (f.eks. `src/web/`, `src/native/`).

## 🤖 4. Håndtering af AI-Opgaver

`::AI` blokke kræver AI-behandling. Dette gøres via `ai-task-runner`.

### Kør AI-Opgaver:
```bash
npx sw-ai-fix
```
Denne kommando scanner projektet for ubehandlede `::AI` blokke, sender dem til den konfigurerede LLM (f.eks. GPT-4o) og integrerer det genererede output tilbage i projektet. Dette kan inkludere tekst, UI-komponenter eller logik.

## ▶️ 5. Kørsel og Forhåndsvisning

Du kan køre og forhåndsvise dit projekt i forskellige miljøer.

### Kør Projektet:
```bash
npx sw-run --target=web
# Eller for native:
npx sw-run --target=ios
npx sw-run --target=android
npx sw-run --target=macos
npx sw-run --target=windows
```
Denne kommando starter en lokal server og/eller simulator, der viser dit kompilerede projekt. For web-mål vil en URL typisk blive vist i terminalen, som du kan åbne i din browser.

## 🧪 6. Test

Test udføres via Puppeteer og en dedikeret test-server.

### Kør Tests:
```bash
npx sw-run-test
```

## 📂 7. Strukturfiler

Vigtige konfigurationsfiler, der styrer systemets adfærd:

*   `sw-naming-book.json`: Definerer navngivningskonventioner for filer, funktioner, klasser og komponenter. **Følg disse regler strengt for at sikre AI-kompatibilitet.**
*   `script-tags.json`: Definerer alle `::TAG`s, deres formål og den forventede output-type.
*   `game.json`: Global topologi og flow-mapping for dit narrative spil eller app.
*   `levels/*.json`: Lokale sceneklynger eller kapitler.

## ✅ Principper for Succes

*   **KISS (Keep It Simple, Stupid)**: Hold dine Markdown-filer så enkle og strukturerede som muligt.
*   **AI-as-fallback**: AI er et værktøj til at assistere og korrigere, ikke til at styre hele udviklingsprocessen. Du definerer strukturen, AI'en udfylder detaljer.
*   **Everything is a file**: Alle outputs er standard filformater (`.ts`, `.tsx`, `.json`, `.md`).
*   **Portable**: Systemet er designet til at fungere i CLI-miljøer, hvilket muliggør fjernudvikling via SSH uden GUI-afhængighed.

Ved at følge denne guide kan du effektivt udnytte SagasWeave techstack til at skabe AI-assisterede projekter.