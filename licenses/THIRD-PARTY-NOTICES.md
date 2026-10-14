# Componentes de terceiros – ERA Downloader V1 Beta

O ERA Downloader é distribuído junto com programas de terceiros que são executados
como **processos separados** (linha de comando). Eles não são ligados (linked) ao
código do ERA Downloader.

## Executáveis incluídos no instalador (sidecars)

| Componente | Versão (build atual) | Licença | Origem |
|---|---|---|---|
| FFmpeg / FFprobe (Windows) | 9.0.2 "essentials" (gyan.dev) | **GPL v3** (build inclui libx264, libx265 e outras bibliotecas GPL) | https://www.gyan.dev/ffmpeg/builds/ · espelho oficial https://github.com/GyanD/codexffmpeg |
| FFmpeg / FFprobe (macOS) | build estático martin-riedl.de | **GPL** | https://ffmpeg.martin-riedl.de/ |
| yt-dlp | 2026.08.19 (atualizado pelo app) | The Unlicense (domínio público) | https://github.com/yt-dlp/yt-dlp |

- Texto da licença do FFmpeg: `FFmpeg-LICENSE.txt` (gerado por `scripts/fetch-sidecars.mjs`).
- Versão, URL e checksum exatos do binário: `FFmpeg-SOURCE.txt`.

### Obrigações do GPL (FFmpeg) – leia antes de distribuir publicamente

1. Incluir o texto da licença (feito: pasta `licenses/` instalada junto com o app).
2. Disponibilizar o **código-fonte correspondente** dos binários GPL distribuídos
   (FFmpeg e bibliotecas GPL do build) — por exemplo hospedando o arquivo-fonte da
   mesma versão junto aos instaladores, ou incluindo uma oferta por escrito válida
   por 3 anos. Para a Beta fechada, `FFmpeg-SOURCE.txt` aponta para o código e os
   scripts do build; **antes de uma distribuição pública, hospede o pacote-fonte
   completo** (FFmpeg n9.0.2 + bibliotecas do build) junto com o instalador.
3. Não impor restrições adicionais ao uso desses binários.

O ERA Downloader apenas executa o FFmpeg como programa externo; essa forma de uso
é considerada agregação, e o código do ERA Downloader não fica sujeito ao GPL.

## Componente opcional baixado pelo app

| Componente | Licença | Origem |
|---|---|---|
| Deno (runtime JavaScript usado pelo yt-dlp no YouTube) | MIT | https://github.com/denoland/deno/releases |

Só é baixado se o usuário clicar em "Instalar Deno" em Configurações › Componentes;
o arquivo é verificado por SHA-256.

## Bibliotecas compiladas no aplicativo

Tauri 2 (MIT/Apache-2.0), React (MIT), Zustand (MIT), Tokio (MIT), Axum (MIT),
Reqwest (MIT/Apache-2.0), rusqlite (MIT) + SQLite (domínio público), tracing (MIT),
serde (MIT/Apache-2.0), regex (MIT/Apache-2.0), uuid (MIT/Apache-2.0), chrono
(MIT/Apache-2.0), sha2 (MIT/Apache-2.0), zip (MIT), os_info (MIT), fs4 (MIT/Apache-2.0),
windows-sys (MIT/Apache-2.0). A lista completa e as versões exatas estão em
`src-tauri/Cargo.lock` e `package-lock.json`.
