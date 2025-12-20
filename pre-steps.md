## 🛠 Voraussetzungen

Anleitung aus der Solana Doku Seite
Installiere Rust, die Solana CLI und das Anchor Framework unter Windows (WSL),

Für Debian oder Debian-basierte Linux-Distribution wie Ubuntu oder Mint ...

1. **Aktualisieren der Paketlisten**:

```bash
sudo apt-get update
```

2. **Installieren Abhängigkeiten 1**:

```bash
sudo apt-get install -y \
    build-essential \
    pkg-config \
    libudev-dev llvm libclang-dev \
    protobuf-compiler libssl-dev
```

3. **Installieren Abhängigkeiten 1**:

```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

##Beispiel Output
```bash
Installed Versions:
Rust: rustc 1.91.1 (ed61e7d7e 2025-11-07)
Solana CLI: solana-cli 3.0.10 (src:96c3a851; feat:3604001754, client:Agave)
Anchor CLI: anchor-cli 0.32.1
Surfpool CLI: surfpool 0.12.0
Node.js: v24.10.0
Yarn: 1.22.1
```
4. ** Überprüfen auf erfolgreiche Installation
```bash
rustc --version && solana --version && anchor --version && surfpool --version && node --version && yarn --version
```


