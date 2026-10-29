# Projeto 6 — De Pátria para Pátria: plano de design

## Objetivo

Evoluir a página existente “De Pátria para Pátria” para corresponder ao design do Sprint 6, preservando o repositório `web_project_homeland` e adaptando o site para desktop (1280px), tablet (768px) e celular (320px).

## Escopo

- Manter as seções existentes: `header`, `lead`, `intro` e `footer`.
- Acrescentar, dentro de `main` e antes do rodapé: `photo-grid`, `places`, blocos repetidos `place` e `cover`.
- Usar CSS Grid obrigatoriamente em `photo-grid` e `places`.
- Armazenar as imagens do Figma na pasta `images` e manter cada bloco BEM em seu próprio arquivo dentro de `blocks`.
- Usar apenas HTML e CSS existentes, sem bibliotecas ou JavaScript.
- Manter a fonte Inter local, o fundo cinza, sem margens brancas e sem rolagem horizontal.

## Abordagens consideradas

1. Colar todo o HTML e CSS em uma só etapa: rápida, mas dificulta localizar erros e reduz o aprendizado.
2. Construir por entregas visuais: imagens, lugares, capa/rodapé e responsividade. Esta abordagem foi escolhida porque permite conferir o resultado em cada largura de tela e entender o CSS Grid gradualmente.

## Estrutura planejada

- `index.html`: inclui as novas seções, na ordem apresentada pelo Figma.
- `blocks/photo-grid.css`: grade de fotos em CSS Grid.
- `blocks/places.css`: grade vertical que organiza os artigos de cidade.
- `blocks/place.css`: título, artista, texto, link e imagem de cada artigo.
- `blocks/cover.css`: seção final clicável sobre imagem de fundo.
- `images/`: imagens exportadas do Figma com nomes descritivos.

## Critérios de conclusão

- O layout corresponde visualmente ao Figma nas larguras 1280px, 768px e 320px.
- As seções `photo-grid` e `places` usam CSS Grid.
- Todas as imagens possuem `alt` em português e todos os links possuem `href` e estado `:hover`.
- `git status` fica limpo após o commit e o GitHub Pages reflete a versão atualizada.
