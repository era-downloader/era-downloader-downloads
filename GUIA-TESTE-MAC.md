# ERA Downloader – guia de teste no Mac (Beta)

Obrigado por testar! Esta é a **primeira versão para Mac** e ainda não foi testada
em nenhum Mac, então problemas são esperados. Anote o que acontecer.

Requisitos: Mac com chip Apple (M1, M2, M3, M4, M5…), macOS 11 ou mais novo.

## 1. Instalar

1. Abra o arquivo `ERA Downloader_….dmg`.
2. Arraste **ERA Downloader** para a pasta **Aplicativos**.
3. Abra o app pela pasta Aplicativos.

### Se o macOS bloquear ("não pode ser aberto" / "Apple não pôde verificar")

O app ainda não tem assinatura paga da Apple, então o bloqueio na primeira vez é
normal. Opção A (sem Terminal):

1. Tente abrir o app uma vez e feche o aviso.
2. Abra **Ajustes do Sistema › Privacidade e Segurança**.
3. Role até o final: aparece "ERA Downloader foi bloqueado…" → clique em
   **Abrir Mesmo Assim** e confirme com sua senha/Touch ID.

Opção B (Terminal), se a opção A não aparecer ou o app fechar sozinho ao abrir:

```bash
xattr -dr com.apple.quarantine "/Applications/ERA Downloader.app"
```

Depois abra o app normalmente.

## 2. Preparar (1 minuto)

1. Vá em **Configurações › Componentes**.
2. Confira se yt-dlp, FFmpeg e FFprobe aparecem com versão (e não "Não encontrado").
3. Em "Runtime JavaScript", clique em **Instalar Deno** (recomendado para o YouTube).

## 3. Testes (anote ✅ ou ❌ em cada um)

Use um vídeo público do YouTube, de preferência em 4K.

1. **Análise:** cole o link → ANALISAR. Aparecem título, miniatura, qualidades?
2. **Player:** ABRIR NO EDITOR. O vídeo aparece e toca **com som**?
   (Se o player ficar preto/sem carregar, anote — a exportação deve funcionar mesmo assim.)
3. **Trecho 4K:** marque ~10 segundos (teclas **I** e **O**, ou digite IN/OUT),
   escolha qualidade 4K se existir, modo **Preciso**, **EXPORTAR**. O arquivo aparece em
   `Downloads/ERA Downloader` e abre no QuickTime com som?
4. **Vários trechos:** adicione 3 trechos (Enter adiciona) → exporte **Separados** e depois
   **Unificados**.
5. **Somente áudio:** exporte um trecho em MP3 e em WAV.
6. **Crop 9:16:** escolha 9:16, arraste o quadro no vídeo, exporte. O vídeo sai vertical?
7. **Cancelar:** inicie uma exportação longa (1–2 min em 4K) e clique **CANCELAR**.
   Some da lista de tarefas como "Cancelado"?
8. **Vídeo completo:** BAIXAR VÍDEO COMPLETO, modo **Rápido**.
9. Se tiver CapCut, DaVinci Resolve ou Premiere: os arquivos do teste 3 abrem neles?

## 4. Enviar o resultado

1. **Configurações › Sobre › Exportar diagnóstico** → salve o arquivo `.txt`.
   (Ele não contém vídeos, senhas, cookies nem links privados.)
2. Envie o `.txt` + a lista ✅/❌ + prints de qualquer erro.
