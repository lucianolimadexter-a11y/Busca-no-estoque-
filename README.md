# 🔍 Busca Rápida no Estoque

<p align="center">
  <img src="capa-v2.png" alt="Busca Rápida no Estoque" width="600">
</p>

App de busca offline para consulta rápida da Curva ABC de estoque de peças/materiais (Alcoa — Refusão), feito em HTML/JS puro, sem necessidade de internet ou servidor.

## Funcionalidades

- Busca por código, descrição, descrição técnica, fornecedor, categoria, endereço e referência de fabricante
- Suporte a frações (`3/4`, `1/2`, `¾`, `½`, etc.) — reconhece ambos os formatos
- Favoritos: marque itens com toque no ☆ para acesso rápido
- Cadastro manual de itens que não estão na planilha original
- Modo escuro, otimizado para celular
- Funciona 100% offline (todos os dados ficam embutidos no próprio arquivo HTML)

## Como usar

Basta abrir o arquivo `index.html` em qualquer navegador (celular ou computador). Não precisa instalar nada.

### Instalar como app no celular (PWA)

Depois de publicado no GitHub Pages (link com `https://`), o app pode ser **instalado de verdade** — não só como atalho:

- **Android (Chrome)**: abra o link → menu (⋮) → **"Instalar app"** (ou vai aparecer um banner automático sugerindo instalar).
- **iPhone (Safari)**: abra o link → botão de compartilhar → **"Adicionar à Tela de Início"**.

Isso só funciona pelo link publicado (https), não abrindo o `index.html` direto do armazenamento do celular — nesse caso só vai aparecer a opção de atalho mesmo.

### Publicar no GitHub Pages (para acessar por um link)

1. Crie um repositório novo no GitHub (pode ser público ou privado).
2. Suba **todos os arquivos** deste projeto para a raiz do repositório (`index.html`, `manifest.json`, `sw.js`, os ícones e o README).
3. Vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` e a pasta `/ (root)`.
5. Salve. Em alguns minutos o app estará disponível em:
   `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`

## Arquivos do projeto

| Arquivo | Função |
|---|---|
| `index.html` | O app em si (HTML/JS/dados, tudo embutido) |
| `manifest.json` | Configuração do PWA (nome, ícone, cores) — permite instalar como app |
| `sw.js` | Service worker — permite abrir offline e habilita a instalação |
| `icon-192.png` / `icon-512.png` | Ícones do app na tela inicial |
| `apple-touch-icon.png` | Ícone específico para iPhone |
| `capa-v2.png` | Imagem de capa do README |

## Dados

Baseado na planilha `Curva ABC` (estoque LAIO_BR_POCOS_PM_MRO_AVG), com 8.431 itens. Os dados ficam embutidos diretamente no HTML — para atualizar, é necessário gerar uma nova versão do arquivo com a planilha atualizada.

## Observações

- Itens cadastrados manualmente e favoritos ficam salvos no `localStorage` do navegador — ou seja, são salvos **por dispositivo/navegador**, não sincronizam entre aparelhos.
- Se você atualizar o `index.html` no futuro, mude também o número da versão no `sw.js` (linha `CACHE_NAME`) — assim o app instalado no celular busca a versão nova em vez de continuar usando a antiga em cache.
