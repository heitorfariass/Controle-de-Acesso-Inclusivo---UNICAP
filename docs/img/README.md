# 📁 Imagens e mídia do projeto

Conteúdo atual desta pasta:

| Arquivo | O que é |
| :--- | :--- |
| `demo.gif` | GIF otimizado (400 px, 8 fps) do vídeo real do protótipo — exibido no topo do README |
| `demo.mp4` | Vídeo completo original (com áudio) — reproduzido nativamente pelo GitHub |
| `primeiro-teste-rfid.jpg` | Primeiro contato e testes com o leitor RC522 |
| `montagem-mdf-laser.jpg` | Montagem da estrutura v1 em MDF cortado a laser (depois substituída por peças 3D) |

## O que ainda pode entrar aqui

- **Foto do protótipo completo montado** (horizontal, bem iluminado) — seria a capa ideal
  para o *Social Preview* do GitHub (Settings → General → Social preview) e pode substituir
  ou acompanhar o GIF no topo do README.
- Fotos de detalhe da eletrônica e do mecanismo de trava instalado, para enriquecer a galeria.

> O GIF foi gerado a partir do vídeo com ffmpeg (paleta otimizada). Se o vídeo for regravado,
> regenere com: `ffmpeg -i video.mp4 -vf "fps=8,scale=400:-1,palettegen" p.png` e depois
> `ffmpeg -i video.mp4 -i p.png -lavfi "fps=8,scale=400:-1[x];[x][1:v]paletteuse=dither=bayer:bayer_scale=5" -loop 0 demo.gif`.
