# keniadesouza

Site pessoal de Kênia Barreiro de Souza, construído com [Quarto](https://quarto.org/).

## Estrutura do projeto

- `index.qmd` — página inicial
- `publications.qmd` — publicações
- `research.qmd` — pesquisa
- `_quarto.yml` — configuração do site (navbar, tema, etc.)
- `styles.css` — estilos customizados
- `docs/` — saída renderizada do site (gerada automaticamente, ignorada no git)
- `.github/workflows/publish.yml` — workflow do GitHub Actions que renderiza e publica o site

## Publicando no GitHub Pages

O repositório já vem com um workflow de deploy automático (`.github/workflows/publish.yml`). Ele usa `quarto-dev/quarto-actions` para renderizar o site e `peaceiris/actions-gh-pages` para publicar o conteúdo de `docs/` no branch `gh-pages`.

### 1. Criar o repositório no GitHub

Crie um repositório vazio (sem README, `.gitignore` ou licença) em https://github.com/new.

### 2. Preparar o branch local

O workflow dispara em push para o branch `main`. Se o branch local ainda se chamar `master`, renomeie:

```bash
git branch -m master main
```

### 3. Commitar e enviar o código

```bash
git add -A
git commit -m "Initial commit: Quarto site"
git remote add origin git@github.com:SEU_USUARIO/keniadesouza.git
git push -u origin main
```

### 4. Habilitar o GitHub Pages

No repositório, vá em **Settings → Pages** e defina:

- **Source**: Deploy from a branch
- **Branch**: `gh-pages` / `/ (root)`

O branch `gh-pages` é criado automaticamente pela Action após o primeiro push para `main`.

### 5. Acompanhar o deploy

Na aba **Actions** do repositório, acompanhe a execução do workflow "Render and Publish". Quando concluído, o site ficará disponível em:

```
https://SEU_USUARIO.github.io/keniadesouza/
```

## Desenvolvimento local

Para pré-visualizar o site localmente (requer [Quarto](https://quarto.org/docs/get-started/) instalado):

```bash
quarto preview
```

Para renderizar o site localmente sem publicar:

```bash
quarto render
```
