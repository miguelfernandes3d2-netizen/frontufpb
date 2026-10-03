# Protótipo visual — Memórias da Poesia Popular

Versão **somente HTML e CSS** do frontend, feita para apresentar a parte
visual à supervisora. Sem JavaScript, sem build, sem servidor, sem banco.

> **Conteúdo fictício.** Nomes, biografias, obras e imagens são de
> demonstração. Nenhuma informação real de poetisa aparece aqui.

---

## Como abrir

**Opção 1 — abrir direto.** Clique duas vezes em `index.html`. Funciona
navegando entre os arquivos pelos links.

**Opção 2 — com servidor local** (recomendado, evita restrições do
navegador com `file://`):

```bash
npx serve .
# ou: python -m http.server 8100
```

Depois acesse `http://localhost:8100/index.html`.

## Páginas

| Arquivo | O que mostra |
|---|---|
| `index.html` | Página inicial: destaque, números do acervo, destaques, Comentários |
| `sobre.html` | Página institucional: proposta e princípios |
| `biografias.html` | Catálogo: busca, índice alfabético, grade de cards |
| `poetisa.html` | Perfil: breadcrumb, retrato, biografia, índice e galeria de obras |
| `lightbox.html` | Diálogo de capa ampliada, exibido no estado em que aparece |
| `contato.html` | Contato no estado desabilitado, com o formulário ativo recolhido |
| `painel.html` | Painel administrativo: lista, filtros e formulário de edição aberto |

## O que dá para mostrar

- Hierarquia visual, tipografia, ritmo e respiro das páginas
- Grade de cards, incluindo o **fallback de iniciais** quando não há foto
- Filtro alfabético com letras **indisponíveis marcadas** (B e D)
- Perfil com **índice numerado das obras** e galeria de capas
- Diálogo de capa ampliada com legenda, contador e botões
- Estados vazios e desabilitados (contato, registro sem obras)
- Painel administrativo completo, com selos de situação e ações
- Rodapé com apoiadores e créditos

## O que **não** aparece aqui

Tudo que depende de JavaScript. Não é defeito do site — é a natureza de
um protótipo sem script:

- busca e filtragem ao vivo
- gaveta de menu no celular (aqui a navegação aparece sempre como lista)
- lightbox abrindo e navegando com as setas ← e →
- contagem de registros, paginação e upload no painel
- login administrativo

Essas partes **existem e funcionam** na versão real, em `../ufpb-frontend`.
Para mostrar uma delas funcionando, aponte a supervisora para o site
publicado ou rode `npm run dev` nessa pasta.

## Imagens

As fotos e capas são **SVGs de demonstração** em `assets/demo/`, gerados
para o protótipo — Compose molduras geométricas, gradientes e as iniciais
do nome, deixando claro que são placeholders. Nenhuma imagem real de
poetisa foi usada.

## CSS

`src/styles/` traz **cópia idêntica** dos quatro arquivos do site real
(`tokens.css`, `base.css`, `public.css`, `admin.css`), com uma única
alteração: o caminho da fonte passou a ser relativo, para funcionar tanto
em `file://` quanto em subpath.

`src/styles/demo.css` é o único arquivo exclusivo deste protótipo. Ele não
muda o design — apenas resolve duas limitações da versão sem JavaScript:

1. a faixa de aviso "Protótipo visual";
2. a navegação, que em vez da gaveta aparece como lista estática no celular;
3. os diálogos, exibidos abertos e no fluxo da página.

Portanto, **o que aparece aqui é o mesmo design que irá ao ar.**

## Imprimir ou gerar PDF

O CSS de impressão do projeto já está aplicado: cabeçalho, rodapé,
apoiaadores e botões somem, e a galeria de capas passa para três colunas.
Para gerar um PDF, use a impressão do próprio navegador e escolha
"Salvar como PDF" com o tamanho em A4 e as margens "Padrão".

## Se quiser ajustar

- **Textos e quantidade de registros:** edite o HTML diretamente.
- **Nomes das poetisas e resumos:** estão em todas as páginas; use
  *Localizar e substituir* para trocar em lote.
- **Cores e tipografia:** em `src/styles/tokens.css`.