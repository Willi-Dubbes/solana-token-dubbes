# solana-token-dubbes
Solana Dubbes Token, A Meme Community Token for Gastronomy, Wine, Boulevard, Palatinate, Pfalz

# 🍷 Anleitung: Erstellung des "Dubbes" Solana Tokens via CLI

Diese Anleitung beschreibt die technische Erstellung des **Dubbes** Tokens auf der Solana Blockchain unter Verwendung des SPL-Token-Standards.

📋 Token Details
* Name: Dubbes
* Symbol: Dubbes
* Beschreibung: Meme Community Token, Pfalz, Wine, Boulevard, Hike, Gastronomy
* Dezimalstellen: 9 (Standard)

## 🛠 Voraussetzungen
Vorbereitung Solana CLI installieren [Pre-Steps](pre-steps.md)

## Wallet & Netzwerk konfigurieren
Zuerst erstellen wir eine lokale Wallet und setzen das Netzwerk auf das Mainnet (Produktion), da der Token zuvor auf Devnet bereits getestet wurde.
Falls ihr eueren eigenen Token erstellen möchtet empfehle ich euch diesen zuerst auf dem Devnet zu verbroben.
```bash
# Neues Wallet generieren
solana-keygen new --outfile ~/dubbes-wallet.json

# Wallet als Standard-Keypair setzen
solana config set --keypair ~/dubbes-wallet.json

# Netzwerk auf Mainnet setzen (für echte Token)
solana config set --url [https://api.mainnet-beta.solana.com](https://api.mainnet-beta.solana.com)
```
> [!NOTE]
> Wichtig, den Wallet Schlüssel sicher und geschützt vor fremden Augen aufbewahren. Wer den Schlüssel besitzt hat die Kontrolle über das Wallet und die enthaltenen Token.

Hinweis: Im nächsten Schritte ca. 0.1 SOL an die Adresse in [...-wallet].json senden, um die Solana Netz Gebühren für die Token Erstellung zu decken.

## Token-Metadaten vorbereiten
Erstelle eine Datei namens metadata.json. Diese enthält die Beschreibung deines Tokens. Lade das Bild vorab bei einem IPFS-Anbieter hoch.
Dateien siehe [Dateien](/solana-token-dubbes)

## Token Erstellung (Token-2022 Standard)
Ich nutze den moderneren Token-2022 Standard, um Name, Symbol und Metadaten-URI direkt beim Erstellen zu verknüpfen.
```bash
spl-token create-token --program-id TokenzQdBNbLqP5VEhdkXEhCwtH76KZmdvYnXEU \
  --name "Dubbes" \
  --symbol "Dubbes" \
  --uri "DEINE_URL_ZUR_JSON_DATEI"
```
Kopieren der ausgegebene Address. Dies ist die Mint-Adresse.

## Token Account & Minting
Erstellen eins Kontos, um die Token zu empfangen, und präge (minto) die gewünschte Menge (in meinem Beispiel 100 Millionen).
```bash
# Token-Konto erstellen
spl-token create-account <DEINE_MINT_ADRESSE>

# 100.000.000 Token prägen
spl-token mint <DEINE_MINT_ADRESSE> 100000000
```
##  Sicherheit: Mint Authority widerrufen
Um das Vertrauen der Community zu gewinnen, wird die Erlaubnis, weitere Token zu drucken, dauerhaft deaktiviert.
```bash
spl-token authorize <DEINE_MINT_ADRESSE> mint --disable
```

⚠️ Rechtlicher Hinweis: DUBBES ist ein Meme-Token zu Unterhaltungszwecken ohne inneren Wert oder Gewinnversprechen. Kryptotoken sind hochspekulativ. Diese Anleitung dient rein technischen Zwecken und stellt keine Anlageberatung dar. Investiere nur, was du bereit bist zu verlieren.



