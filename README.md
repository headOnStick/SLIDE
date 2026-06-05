# A Inteligência Artificial ao Serviço do Treinador
### Aplicações Práticas e Ferramentas de Apoio

Apresentação de **André Rocha** para o **13.º Congresso de Treinadores de Portugal** (Albufeira '26).

Deck HTML autossuficiente (zero dependências, sem CDN) — corre em qualquer browser, offline.

---

## Como apresentar

Abre o ficheiro no browser:

```bash
xdg-open presentation.html      # Linux
# open presentation.html        # macOS
# start presentation.html       # Windows
```

Ou serve por HTTP local (recomendado para garantir o autoplay dos vídeos):

```bash
python3 -m http.server 8765
# depois abre http://127.0.0.1:8765/presentation.html
```

### Controlos
| Tecla | Ação |
|-------|------|
| `↓` `→` `Espaço` | Próximo slide |
| `↑` `←` | Slide anterior |
| `Home` / `End` | Primeiro / último |
| `F` | Ecrã inteiro |
| Pontos laterais | Saltar para um slide |

Os vídeos arrancam do início ao entrar no slide e pausam ao sair.

---

## Estrutura

```
presentation.html        # o deck completo (HTML + CSS + JS inline)
assets/
├── fonts/               # Carlito (tipo do template do congresso), embebida
├── brand-title-bg.jpg   # fundo de marca — slide de abertura
├── brand-content-bg.jpg # fundo de marca — slide de fecho
├── footer-band.png      # faixa de ondas + logos (rodapé)
├── congress-logo.png    # logótipo do congresso (canto)
├── claude-code.png      # slide 6 — captura do Claude Code
├── goncalo-1.mp4 / -2   # slide 4 — clips verticais 9:16 (defesas)
├── goncalo-*-poster.jpg # posters dos clips
├── grocha-h264.mp4      # slide 7 — vídeo do Protocolo G.R.O.C.H.A.
└── grocha-poster.jpg    # poster do vídeo G.R.O.C.H.A.
```

## Os 11 slides

1. Abertura (marca) — título da sessão
2. Quem sou eu — Treinador de campo × CTO (Hoopers)
3. "É para quem quer, não é só para quem sabe"
4. Este é o Gonçalo — clips das defesas (vídeo)
5. "Pai, para que serve este exercício?" — treino ↔ jogo
6. Claude Code em ação — captura do terminal
7. Protocolo G.R.O.C.H.A. — vídeo split-screen (o momento WOW)
8. Banho de realidade — "É." / "Nem por isso."
9. Movimento individual vs coletivo — escopo e limites
10. O Manifesto — usar a IA com cuidado
11. Fecho (marca) — Obrigado

## Trocar / acrescentar média

- **Mais defesas do Gonçalo:** adiciona `assets/goncalo-3.mp4`, `goncalo-4.mp4` e duplica um cartão `.vclip` no slide 4.
- **Vídeos** devem estar em **H.264 (yuv420p)** para tocarem no browser. Para converter:
  ```bash
  ffmpeg -i origem.mp4 -c:v libopenh264 -pix_fmt yuv420p -b:v 4M -movflags +faststart -an saida.mp4
  ```

---

*Tipo de letra: Carlito (SIL Open Font License) — clone métrico do Calibri, igual ao template do congresso.*
