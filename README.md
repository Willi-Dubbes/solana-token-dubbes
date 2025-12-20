# solana-token-dubbes
Solana Dubbes Token, A Meme Community Token for Gastronomy, Wine, Boulevard, Palatinate, Pfalz

# 🍷 Anleitung: Erstellung des "Dubbes" Solana Tokens via CLI

Diese Anleitung beschreibt die technische Erstellung des **Dubbes** Tokens auf der Solana Blockchain unter Verwendung des SPL-Token-Standards.

📋 Token Details
* Name: Dubbes
* Symbol: Dubbes
* Beschreibung: Meme Community Token, Gastronomy, Wine, Boulevard, Pfalz
* Dezimalstellen: 9 (Standard)

## 🛠 Voraussetzungen
Vorbereitung Solana CLI installieren [Pre-Steps](pre-steps.md)

## Wallet & Netzwerk konfigurieren
Zuerst erstellen wir eine lokale Wallet und setzen das Netzwerk auf das Mainnet (Produktion), da der Token zuvor auf Devnet bereits getestet wurde

```bash
# Neue Wallet generieren
solana-keygen new --outfile ~/dubbes-wallet.json

# Wallet als Standard-Keypair setzen
solana config set --keypair ~/dubbes-wallet.json

# Netzwerk auf Mainnet setzen (für echte Token)
solana config set --url [https://api.mainnet-beta.solana.com](https://api.mainnet-beta.solana.com)
```

Hinweis: Im nächsten Schritte ca. 0.1 SOL an die Adresse in [token-wallet].json senden, um die Gebühren zu decken.

