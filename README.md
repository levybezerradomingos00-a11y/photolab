# PHOTO LAB — editor de fotografias

Aplicativo **estático, mobile-first e sem IA generativa**. Possui **34 tratamentos**, incluindo efeitos fade, preto e branco e uma aba personalizada inspirada nas referências visuais do projeto.

## Uso

- Abra `index.html` em um navegador moderno e selecione uma foto.
- Escolha uma categoria e um preset, ou ajuste intensidade, fade, grão e exposição.
- Compare o original com o resultado e exporte em JPG (94%) ou PNG.
- A foto é processada com Canvas no seu próprio dispositivo. Não existe upload de arquivos, backend, serviços de IA ou analítica.

## Publicação no GitHub Pages

1. Faça upload dos arquivos **e pastas** deste projeto para a raiz do repositório `photolab` (incluindo `assets/` e `.nojekyll`).
2. No GitHub, abra **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**; selecione `main` e `/(root)`; salve.
4. Após a publicação, abra `https://levybezerradomingos00-a11y.github.io/photolab/` no Safari do iPhone.
5. No Safari, use **Compartilhar → Adicionar à Tela de Início** para acesso rápido (quando disponível).

## Google Sites

Use **Inserir → Incorporar → URL** e cole a URL publicada no GitHub Pages, ou adicione um botão com link direto ao PHOTO LAB. **No iPhone, prefira abrir no Safari**: navegadores embutidos e iframes podem limitar o seletor de arquivos e os downloads/compartilhamentos.

## Recursos e limites

- Edição determinística dos pixels usando `<canvas>`, sem recriar pessoas ou cenários.
- O Instagram decide independentemente se mostrará rótulos de conteúdo editado/IA.
- JPG e PNG; resoluções de 1600 px, 2400 px e original até 22 megapixels. Imagens maiores devem usar uma resolução reduzida para evitar travamentos de memória, principalmente no iOS.
- A prévia funciona numa resolução menor para economizar bateria e memória. A exportação é recalculada no tamanho selecionado.
- Arquivos HEIC dependem de suporte do navegador. Em caso de incompatibilidade, converta para JPG.
- Um service worker salva apenas os arquivos do app para acesso offline após a primeira visita sob HTTPS. Não armazena as fotos.
- Nenhuma dependência de build: apenas HTML, JS e CSS.

## Testes

`python tests/smoke_test.py` (requer `playwright` com Chromium instalado e `Pillow` para gerar imagens de teste).

O teste verifica seleção de presets, visualização do original, slider de intensidade, responsividade mobile e exportação JPG/PNG.