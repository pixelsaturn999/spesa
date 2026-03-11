# 🐒 Spesa dei Babbuini — PWA

App lista della spesa condivisa e sincronizzata, installabile su Android (e iPhone) come app nativa.

---

## 📲 Come installare su Android (metodo semplice — consigliato)

### Opzione A — Chrome sul telefono (più semplice)

1. Copia la cartella `spesa-pwa/` su un tuo server web, oppure usa **GitHub Pages** (gratuito):
   - Crea un repository pubblico su github.com
   - Carica i file (index.html, manifest.json, sw.js, icon-192.png, icon-512.png)
   - Vai su Settings → Pages → Source: main → Salva
   - Il sito sarà su `https://tuonomeutente.github.io/nome-repo/`

2. Apri Chrome sul tuo Android e vai all'URL del sito

3. Chrome mostrerà automaticamente il banner **"Aggiungi alla schermata Home"** — oppure tocca i 3 puntini → "Aggiungi alla schermata Home"

4. L'app appare nella home con l'icona 🐒, si apre a schermo intero senza barra del browser, e funziona **offline**!

---

### Opzione B — Generare un vero .apk con PWABuilder (gratuito)

1. Segui il punto 1 dell'Opzione A per pubblicare il sito

2. Vai su **https://www.pwabuilder.com**

3. Incolla l'URL del tuo sito e clicca "Start"

4. Clicca **"Package for Stores"** → Android → Scarica il pacchetto APK

5. Installa l'APK sul telefono (dovrai abilitare "Origini sconosciute" nelle impostazioni Android)

---

### Opzione C — Servire localmente da PC con telefono sulla stessa rete

```bash
# Nella cartella spesa-pwa/, esegui:
npx serve .
# oppure:
python3 -m http.server 8080
```

Poi vai su `http://IP-DEL-PC:8080` dal browser del telefono.

> ⚠️ Il Service Worker richiede HTTPS oppure localhost — su rete locale potrebbe non installarsi, ma l'app funziona comunque.

---

## 🔄 Sincronizzazione multi-device

La sincronizzazione usa **JSONBin.io** — la configurazione è già inclusa nell'app.
- Tutti i dispositivi che usano lo stesso Bin ID vedono la stessa lista
- L'aggiornamento avviene ogni 30 secondi automaticamente
- Il pulsante "Aggiorna" forza il refresh manuale
- Offline: la lista rimane disponibile in locale, si sincronizza quando torna la connessione

---

## 📁 File inclusi

| File | Scopo |
|------|-------|
| `index.html` | App principale con tutte le funzioni |
| `manifest.json` | Manifesto PWA (nome, icone, colori, modalità standalone) |
| `sw.js` | Service Worker — cache offline e background sync |
| `icon-192.png` | Icona app 192×192 px |
| `icon-512.png` | Icona app 512×512 px |
