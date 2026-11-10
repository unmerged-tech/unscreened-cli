# unscreened-cli

Signed binaries of the `unscreened` CLI. This repository holds releases only; there is no source code here.

## Install

```sh
curl -fsSL https://unscreened-app.vercel.app/install.sh -o install.sh   # read it, then:
sh install.sh
```

The script installs to `~/.local/bin` (no sudo). It needs `minisign` (`brew install minisign`) and refuses to install without it.

## How signatures are verified

Every release ships `SHA256SUMS`, the raw binaries and `manifest.json`, each with a `.minisig` signature made offline with the unscreened release key. The installer checks `SHA256SUMS`, then the binary hash, then the binary signature. To check by hand:

```sh
minisign -Vm <file> -P RWSKF/VQcOclNqxeKJq16IcojYV7vNifJn+z69AMA5dDPFZjTOCYx5Na
```

Public key: `RWSKF/VQcOclNqxeKJq16IcojYV7vNifJn+z69AMA5dDPFZjTOCYx5Na`

## По-русски

Здесь лежат только подписанные бинарники CLI `unscreened`, исходников нет. Установка: скачайте `https://unscreened-app.vercel.app/install.sh`, прочитайте и запустите `sh install.sh` (нужен `minisign`). Скрипт проверяет подпись `SHA256SUMS` и самого бинарника публичным ключом выше; проверить вручную можно командой `minisign -Vm <файл> -P <ключ>`.
