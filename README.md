<!--
  MediEvilRecomp ITA - Mod Hub
  Author: https://github.com/Leproide
  License: GPL-3.0-or-later
-->

# MediEvilRecomp ITA - Mod Hub

Elenco di mod, asset pack e shader per **MediEvilRecomp ITA** (versione PAL italiana, SCES-01494). Il gioco legge questo repository e mostra le voci in **Mods → Explore Mod Hub**, da dove si installano con un clic.

Il repository non contiene le mod: ogni voce è un file di testo che punta al repository git della mod, fissato a un commit preciso.

> Le mod dell'hub del progetto originale (versione USA) usano indirizzi di memoria diversi e su questa versione non funzionano. Qui vanno solo voci provate sulla versione PAL italiana. Shader e asset pack che non toccano il codice del gioco funzionano su entrambe.

## Formato delle voci

Ogni voce è un file dentro `mods/`, senza estensione. Il nome del file è l'identificativo: lettere minuscole, numeri, `.`, `_` e `-`, massimo 64 caratteri. I file che iniziano con `_` vengono ignorati (vedi `mods/_example`).

```
type=shader
name=Nome visualizzato
description=Una o due frasi su cosa fa.
repository=https://github.com/Utente/Repository.git
commit=hash completo di 40 caratteri
authors=Utente1, Utente2
tags=shader
```

| Chiave | Obbligatoria | Significato |
|---|---|---|
| `type` | sì | `mod`, `assetpack` oppure `shader` |
| `name` | sì | nome visualizzato |
| `description` | sì | descrizione breve |
| `repository` | sì | URL `https://` del repository git della mod |
| `commit` | sì | hash completo (40 caratteri) della versione da installare |
| `authors` | sì | autori, separati da virgole |
| `path` | no | cartella del repository da installare, se non è la radice |
| `icon` | no | percorso dell'icona nel repository |
| `tags` | no | parole chiave, separate da virgole |
| `warning` | no | avviso mostrato prima dell'installazione. **Obbligatorio** se la mod usa la rete o fa qualcosa fuori dal controllo del giocatore |

Righe vuote e righe che iniziano con `#` vengono ignorate.

## Dove ospitarlo

Il gioco scarica le voci dalla cartella `mods/` del ramo `main` (configurabile). Funziona con:

- **GitHub, GitLab, Codeberg**, e server **Gitea/Forgejo** con un indirizzo che inizia con `gitea.` o `forgejo.`: i file vengono scaricati come archivio, il giocatore non ha bisogno di nulla.
- **Qualsiasi altro server git via `https://`**: il gioco usa il comando `git`, che deve essere installato sul PC del giocatore.

Lo stesso vale per i repository delle singole mod indicati nelle voci.

## Proporre una voce

1. Fai un fork di questo repository.
2. Aggiungi `mods/<identificativo>` nel formato descritto sopra, con il commit da distribuire.
3. Apri una pull request: la voce viene controllata prima di essere pubblicata. Per gli aggiornamenti si apre una nuova pull request con il nuovo commit.

## Regole

- Niente materiale protetto da copyright senza i diritti per distribuirlo, compresi file del gioco.
- Crediti a tutti gli autori; se parti dal lavoro di altri, la loro licenza deve permetterlo.
- Codice sorgente leggibile nel repository indicato: niente codice offuscato né scaricato a runtime senza `warning`.
- Niente comportamenti dannosi, raccolta di dati o modifiche fuori dalla cartella del gioco.
- Le mod che toccano il codice del gioco devono essere provate sulla versione PAL italiana.
- I contributi fatti con l'aiuto dell'intelligenza artificiale sono accettati, come nel resto del progetto: conta che siano corretti e provati.

Installare qualcosa dall'hub è a proprio rischio: le voci vengono controllate, ma questo non è una garanzia.

MediEvil è un marchio di Sony Interactive Entertainment. Questo hub è un progetto amatoriale non ufficiale, non affiliato né approvato da Sony Interactive Entertainment.

## License

GPL-3.0-or-later per i file di questo repository (README e voci). Ogni mod elencata ha la licenza del proprio repository.

## Author

https://github.com/Leproide
