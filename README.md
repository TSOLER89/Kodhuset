# Kodhuset AB

## Projektbeskrivning

Kodhuset AB är en webbplats utvecklad med Umbraco CMS som en del av kursen Publiceringsverktyg och UX.

Webbplatsen innehåller information om företaget, tjänster, projekt, kontaktuppgifter och vanliga frågor (FAQ).

Syftet är att skapa en innehållshanterad webbplats där redaktörer kan uppdatera och publicera information genom Umbraco Backoffice utan att behöva ändra webbplatsens kod.

## Tekniker

- Umbraco CMS 18.2.1
- ASP.NET Core / .NET 10
- C#
- Razor (.cshtml)
- HTML
- SCSS / CSS
- Dart Sass
- SQLite (lokal databas)

## Funktionalitet

### Innehållshantering

Webbplatsens innehåll hanteras genom Umbraco Backoffice.

Administratörer och behöriga användare kan skapa, redigera och publicera innehåll.

Innehållet lagras i Umbraco och presenteras genom Razor-mallar.

### Dokumenttyper

Projektet använder flera dokumenttyper för att strukturera innehållet.

I den individuella uppgiften har dokumenttypen **Vanlig fråga** skapats för att hantera vanliga frågor och svar.

Dokumenttypen innehåller tre fält:

| Fält     | Datatyp          | Syfte                    |
| -------- | ---------------- | ------------------------ |
| Fråga    | Textstring       | Frågans rubrik           |
| Svar     | Rich Text Editor | Frågans svar             |
| Kategori | Dropdown         | Kategorisering av frågan |

Med dokumenttypen kan flera FAQ-sidor skapas med samma struktur.

### FAQ

Två FAQ-sidor har skapats och publicerats.

- Kan Kodhuset hjälpa oss att skapa en webbplats?
- Utvecklar Kodhuset skräddarsydda system?

Frågorna visas som klickbara kort på startsidan.

Innehållet hämtas dynamiskt från Umbraco, vilket innebär att frågorna kan uppdateras i Backoffice utan att ändra Razor-koden.

### Användarroller

Projektet använder olika användargrupper för att styra publiceringsprocessen.

**Skribent**

- Kan skapa innehåll.
- Kan redigera innehåll.
- Kan spara utkast.
- Kan inte publicera.

**Redaktör**

- Kan skapa och redigera innehåll.
- Kan publicera innehåll.

Rollindelningen gör det möjligt att skilja mellan innehållsproduktion och publicering.

### Design och responsivitet

Webbplatsen använder en mörkblå och petrolgrön färgpalett.

Designen innehåller:

- Responsiv navigering.
- Anpassade rubriker och textstorlekar.
- Projektkort och FAQ-kort.
- Gemensamma SCSS-stilar.
- Anpassning för olika skärmstorlekar.

## Projektstruktur

| Fil/mapp                    | Funktion                   |
| --------------------------- | -------------------------- |
| `Views/Startsida.cshtml`    | Startsida och FAQ-länkar   |
| `Views/Sida.cshtml`         | Vanliga innehållssidor     |
| `Views/Projekt.cshtml`      | Presentation av projekt    |
| `Views/VanligFraaga.cshtml` | FAQ-detaljsida             |
| `Styles/`                   | SCSS-filer                 |
| `wwwroot/css/site.css`      | Genererad CSS              |
| `Program.cs`                | Konfiguration och uppstart |
| `umbraco/Data/`             | Lokal Umbraco-data         |

## Starta projektet

Projektet kräver .NET 10 SDK och Node.js.

Installera beroenden och bygg CSS:

```powershell
dotnet restore
npm ci
npm run bygg
```

Starta applikationen:

```powershell
dotnet run --launch-profile "Umbraco.Web.UI"
```

Webbplatsen körs lokalt med de adresser som anges i `Properties/launchSettings.json`.

Umbraco Backoffice nås via `/umbraco`.

Observera att den lokala databasen och mediafilerna behövs för att återskapa det befintliga innehållet.

## Möjliga framtida förbättringar

- Samla navigeringen i en gemensam Razor-partial.
- Använda en gemensam layout för samtliga sidtyper.
- Samla FAQ-sidans separata CSS med webbplatsens övriga stilar.
- Förbättra möjligheten att administrera navigeringen direkt i Umbraco.

## Sammanfattning

Projektet visar hur Umbraco kan användas för att skapa en webbplats med strukturerat innehåll, återanvändbara dokumenttyper och rollbaserad publicering.

Genom kombinationen av Umbraco, Razor och SCSS separeras innehållshantering från webbplatsens presentation.
