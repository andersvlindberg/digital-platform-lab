# Mina anteckningar

- **Fil** = där jag skriver kod. Ligger i mappen `Dev\digital-platform-lab`
- **Commit** = ett fotografi av hur filerna ser ut just nu. Sparas i historiken
- **Branch** = min egen arbetsyta. Jag kan testa utan att förstöra main
- **main** = huvudgrenen. Här ska bara sånt som fungerar hamna
- **Push** = skicka upp mina commits till GitHub

Viktigt: en commit skapar INGEN ny fil.
Jag har alltid en `server.js` — commiten sparar hur den såg ut.
Som versionshistorik i Google Docs.

## Varför jag jobbar i en branch

Jag kan testa och ha sönder saker utan att main påverkas.
Blir det fel slänger jag grenen. Fungerar det lägger jag in det i main.
Så jobbar man på riktigt också — ingen committar direkt på main på ett jobb.

## Tre sätt att spara (de är inte samma sak)

1. **Ctrl+S** → sparar filen i mappen
2. **Commit** → sparar en punkt i historiken, på min dator
3. **Push** → kopierar historiken till GitHub

Ctrl+S är INTE en commit. Utan commit kan jag inte gå tillbaka.

Ingenting försvinner när jag stänger datorn. Filerna ligger kvar i mappen,
och jag står kvar i samma branch nästa gång.

## Varje gång jag jobbat klart

```
git status
git add .
git commit -m "Lab 02: knapp 1 fungerar"
git push
```

GitHub Desktop: Changes → skriv i Summary → Commit → Push origin

Committa varje gång något fungerar. Inte bara när jag är helt klar.
Varje commit är en punkt jag kan gå tillbaka till.

## Gå tillbaka till en tidigare version

```
git log --oneline                          visa alla punkter
git restore server.js                      tillbaka till senaste commiten
git restore --source=a1b2c3d server.js     tillbaka till en specifik
```

`a1b2c3d` är id:t jag ser i `git log`.

## Lägga in min branch i main

```
git switch main
git merge min-branch
git push
git branch -d min-branch
```

GitHub Desktop: byt till main → menyn Branch → Merge into current branch
→ välj min gren → Push origin

Det är `merge` som är "lägga in i main".

## Pull request

En förfrågan om att få lägga in en grens ändringar i en annan gren.

På jobbet: jag pushar min gren, öppnar en pull request,
en kollega granskar koden, sen mergas den in i main.
Det är kvalitetskontrollen.

Ensam behöver jag den inte. Jag kan merga själv.

VARNING: öppnar jag en pull request från min fork föreslår GitHub
automatiskt Mats kursrepo som mottagare. Det vill jag inte.
Ska det in i min egen main måste jag byta "base" till mitt eget repo.

## Commit-meddelanden

Skriv VAD som ändrades.

Bra: "Lab 02: validering av occurredAt"
Dåligt: "fix", "ändringar", "uppdatering"
