# Curitiba Fatal Crashes — site publicável

Conteúdo pronto para virar o repositório `curitiba-fatal-crashes` no GitHub Pages
(URLs já referenciadas pelo artigo do portfólio):

| Arquivo | URL esperada |
|---|---|
| `index.html` | https://avnergomes.github.io/curitiba-fatal-crashes/ (mapa 3D, 1 boneco = 1 sinistro fatal) |
| `relatorio.html` | .../relatorio.html (reportagem de dados, PT) |
| `dashboard.html` | .../dashboard.html (dashboard exploratório) |

## Publicar

```bash
cd site
git init && git add . && git commit -m "feat: mapa 3D + relatorio + dashboard de sinistros fatais de Curitiba"
gh repo create avnergomes/curitiba-fatal-crashes --public --source . --push
gh api -X POST repos/avnergomes/curitiba-fatal-crashes/pages -f "source[branch]=master" -f "source[path]=/"
```

Regenerar após mudanças nos dados/templates (na pasta do projeto):

```bash
py -3 build2.py          # relatorio_trecho_mais_perigoso.html
py -3 build_map3d.py     # mapa3d_curitiba.html + copia tudo para site/
```

Fonte: IPPUC, painel "Acidente de Trânsito" (BPTRAN/SMDT), sinistros fatais 2010–2024.
