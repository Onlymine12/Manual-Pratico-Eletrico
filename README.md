# Manual Prático do Eletricista Residencial — Web App

App em uma página só (HTML + CSS + JavaScript dentro do `index.html`) que dá acesso aos 11 materiais do kit. É um site estático: não precisa de servidor, banco de dados nem instalação.

## Estrutura

```
index.html     o app completo (estilos e scripts embutidos)
img/           banner da home + capas dos 11 materiais (.webp)
materiais/     os 11 materiais para download (10 PDFs + a planilha .html)
README.md      este arquivo
```

Mantenha os nomes das pastas e dos arquivos exatamente como estão: o `index.html` aponta para eles por caminho relativo (`img/...` e `materiais/...`). Em hospedagens Linux, maiúsculas e minúsculas fazem diferença.

## Como hospedar

Envie o **conteúdo** desta pasta (não a pasta em si) para a raiz do site, de forma que o `index.html` fique no endereço principal.

| Onde | Como |
|---|---|
| **Netlify** | Em app.netlify.com → *Add new site* → *Deploy manually*, arraste a pasta extraída. |
| **Vercel** | `vercel deploy` dentro da pasta, ou importe um repositório com estes arquivos. Não precisa configurar build. |
| **GitHub Pages** | Suba os arquivos na raiz do repositório → *Settings* → *Pages* → branch `main`, pasta `/root`. |
| **Hostinger / cPanel** | Gerenciador de arquivos → `public_html` → envie o zip e use *Extrair*. |

Depois de publicar, abra o site e teste: a home, a aba *Acervo* e o download de pelo menos um material.

## Testar no computador

Dê dois cliques no `index.html`. O app abre no navegador e funciona offline, inclusive os downloads.

## Configurações (dentro do `index.html`)

Abra o `index.html` num editor de texto e procure por `const CONFIG` (fica perto do início do bloco de scripts):

| Campo | Para que serve | Situação atual |
|---|---|---|
| `kit` | Nome do kit no topo da home | `"Kit Profissional"` |
| `acessoConfirmado` | Mostra a mensagem "Acesso liberado!" ao abrir | `true` |
| `capaProduto` | Imagem de capa do produto, ex.: `"img/capa-manual.png"` | vazio (usa capa ilustrada) |
| `suporte` | Botão de suporte na aba *Mais*, ex.: `{ texto: "Falar no WhatsApp", link: "https://wa.me/5511999999999" }` | vazio (botão não aparece) |
| `autoria` | Autor ou responsável técnico | vazio |

Todo ponto que ainda pode ser personalizado está marcado com o comentário `TROCAR` no código (use Ctrl+F).

## Trocar um material ou uma imagem

- **Material:** substitua o arquivo em `materiais/` mantendo o mesmo nome. Para usar outro nome, ajuste o campo `link` do material na lista `TEMAS` no `index.html`.
- **Capa de um material:** substitua o `.webp` correspondente em `img/` (tamanho 1254 × 1254 px), mantendo o nome.
- **Banner da home:** substitua `img/00-banner-principal.webp`.
- **Logo e ícone da aba:** coloque `img/logo.png` e `img/icone.png` e descomente as linhas indicadas com `TROCAR` no `index.html`.

Se após trocar um arquivo o site ainda mostrar o antigo, limpe o cache do navegador (Ctrl+F5) ou aguarde alguns minutos: algumas hospedagens guardam cópia em cache.

## Observações

- O material 02 (`02-manual-eletricista-residencial.pdf`) tem cerca de 14,6 MB. Verifique se o seu plano de hospedagem aceita arquivos desse tamanho.
- As fontes (Archivo e Inter) vêm do Google Fonts. Sem internet, o app usa fontes do sistema e continua funcionando.
- O app guarda os favoritos do usuário no próprio navegador (armazenamento local). Eles não passam de um aparelho para outro.

## Os 11 materiais

| Nº | Material | Arquivo |
|---|---|---|
| 01 | Introdução à Elétrica Residencial | `materiais/01-introducao-eletrica-residencial.pdf` |
| 02 | Manual do Eletricista Residencial | `materiais/02-manual-eletricista-residencial.pdf` |
| 03 | Planilha de Orçamento Elétrico | `materiais/03-planilha-orcamento-eletrico.html` |
| 04 | Lista de Materiais Elétricos | `materiais/04-lista-materiais-eletricos.pdf` |
| 05 | Guia: Quanto Cobrar por Serviços Elétricos | `materiais/05-guia-quanto-cobrar.pdf` |
| 06 | Manual de Segurança e Lista de Verificação | `materiais/06-manual-seguranca-checklist.pdf` |
| 07 | Apostila Completa de Instalação Elétrica | `materiais/07-apostila-instalacao-eletrica.pdf` |
| 08 | Curso Rápido de Eletrodoméstico Residencial | `materiais/08-curso-rapido-eletrodomestico.pdf` |
| 09 | Projetos Residenciais de Eletricidade para Iniciantes | `materiais/09-projetos-residenciais-iniciantes.pdf` |
| 10 | Como Fazer um Projeto Elétrico Passo a Passo | `materiais/10-projeto-eletrico-passo-a-passo.pdf` |
| 11 | Entendendo um Projeto de Elétrica Residencial | `materiais/11-entendendo-projeto-eletrica.pdf` |
