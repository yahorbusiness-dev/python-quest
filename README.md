# The Pyth Adventure

Ett gratis 8-bitarsspel på svenska där man lär sig programmera Python från noll.
31 uppdrag. Allt börjar på Ängen – resten får spelaren upptäcka själv.

## Filer

| Fil | Vad den är |
|---|---|
| `index.html` | Startsidan: beskrivning, bilder, inloggning och knapp till spelet |
| `spel.html` | Själva spelet (allt i en fil) |
| `bilder/` | Skärmbilder från spelet som visas på startsidan |

## Konton och molnsparning

Inloggning och sparning sköts av Supabase-projektet **PythonQuest**
(`https://jgjjbtkoguqupmszmpjn.supabase.co`). Tabellen `progress` har en rad per
spelare och skyddas med Row Level Security, så att varje spelare bara kan läsa
och ändra sin egen sparning. Nyckeln i koden är en offentlig nyckel och får synas.

Startsidan och spelet ligger på samma webbadress, så inloggningen delas mellan dem.

### Inställningar i Supabase när sidan är publicerad

1. **Authentication → URL Configuration**: sätt *Site URL* till sidans adress
   och lägg till adressen följt av `/**` under *Redirect URLs*.
2. **Authentication → Emails → SMTP Settings**: koppla in en egen mejltjänst
   (till exempel Resend). Utan den skickas mejl bara till medlemmar i
   Supabase-organisationen.

## Publicera

Sidan är helt statisk. Den kan publiceras med GitHub Pages
(Settings → Pages → Deploy from a branch → `main`, mapp `/`) eller med Netlify
genom att koppla det här repot.
