# SpaceDevs Blog - Jekyll

Blog estático desenvolvido com Jekyll para a plataforma SpaceDevs.

## Estrutura do Projeto

```
blog/
├── _config.yml           # Configurações do Jekyll
├── _layouts/             # Templates de layout
│   ├── default.html      # Layout base
│   └── post.html         # Layout para posts individuais
├── _includes/            # Componentes reutilizáveis
│   ├── header.html       # Cabeçalho
│   └── footer.html       # Rodapé
├── _posts/               # Posts do blog (Markdown)
│   ├── 2024-02-12-como-comecei-programar.md
│   ├── 2024-02-10-guia-git-iniciantes.md
│   ├── 2024-02-05-podcast-mercado-trabalho.md
│   └── 2024-02-01-variaveis-constantes.md
└── index.html            # Página inicial (listagem de posts)
```

## Como usar

### 1. Instalar Jekyll

```bash
gem install bundler jekyll
```

### 2. Criar Gemfile

Crie um arquivo `Gemfile` na raiz do projeto:

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.3"
gem "webrick", "~> 1.8"

group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
end
```

### 3. Instalar dependências

```bash
bundle install
```

### 4. Executar o servidor local

```bash
bundle exec jekyll serve
```

Acesse em: `http://localhost:4000`

## Criar novos posts

Os posts devem ser criados em `_posts/` seguindo o padrão:

**Nome do arquivo:** `YYYY-MM-DD-titulo-do-post.md`

**Front Matter (cabeçalho do arquivo):**

```yaml
---
layout: post
title: "Título do Post"
date: 2024-02-12 10:00:00 -0300
author: Nome do Autor
author_image: "URL da imagem" # opcional
type: video|audio|text
cover_image: "URL da imagem de capa"
reading_time: "10 min"
duration: "10:45" # apenas para vídeo/áudio
excerpt: "Resumo do post"
tags: [Tag1, Tag2, Tag3]
---

Conteúdo do post em Markdown...
```

## Tipos de conteúdo

- **text** - Artigos escritos
- **video** - Vídeo aulas
- **audio** - Podcasts

## Deploy

### GitHub Pages

1. Faça push para um repositório GitHub
2. Vá em Settings > Pages
3. Selecione a branch `main` como source
4. O site será publicado em `https://seu-usuario.github.io/repositorio`

### Netlify

1. Conecte seu repositório
2. Build command: `jekyll build`
3. Publish directory: `_site`

## Customização

- **Cores e estilos:** Edite a configuração do Tailwind em `_layouts/default.html`
- **Informações do site:** Edite `_config.yml`
- **Header/Footer:** Edite os arquivos em `_includes/`

## Syntax Highlighting

O blog possui syntax highlighting automático para blocos de código usando Rouge. Suporta diversas linguagens:

```markdown
```javascript
const hello = "world";
```
```python
def saudar(nome):
    return f"Olá, {nome}!"
```
```bash
git commit -m "feat: nova funcionalidade"
```
\```

O tema de cores é dark (inspirado no Monokai) e se integra perfeitamente com o design do blog.

## Tecnologias

- Jekyll 4.x
- Rouge (Syntax Highlighter)
- Tailwind CSS (via CDN)
- Lucide Icons
- Liquid Template Engine
