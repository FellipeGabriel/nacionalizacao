# Dossiê i18n: Europa Ocidental

Página que compara Portugal, Alemanha, Reino Unido e Espanha em sete eixos de internacionalização: idioma, moeda, imposto, fuso horário, base legal, meios de pagamento e feriados.

Complemento visual de um Trabalho de Conclusão de Curso. Roda inteira no navegador, sem servidor de aplicação.

Publicado em https://fellipegabriel.github.io/nacionalizacao/

## Estrutura

```
index.html                    a página, arquivo único e autocontido
.github/workflows/deploy.yml  publicação automática no GitHub Pages
```

O `index.html` carrega tudo de dentro de si mesmo, incluindo fontes e bibliotecas. A página não faz nenhuma requisição a domínios de terceiros.

## Atualizar a página

Substitua o `index.html` pela versão nova e envie:

```bash
git add index.html
git commit -m "Atualiza a página"
git push
```

Todo push na branch `main` republica o site. Não há passo manual.

## Rodar localmente

```bash
python3 -m http.server 8000
```

Acesse http://localhost:8000

## Manutenção

As actions do workflow estão fixadas por commit SHA para que uma tag reescrita no repositório de origem não altere o que roda na publicação. As versões são `actions/checkout` v5, `actions/configure-pages` v5, `actions/upload-pages-artifact` v4 e `actions/deploy-pages` v4. Para atualizar uma delas, pegue o SHA novo com `gh api repos/actions/checkout/commits/v5 --jq .sha` e troque no workflow.

## Licenças

O código está sob a licença MIT. Ver [LICENSE](LICENSE).

O conteúdo do dossiê, ou seja, os textos, os dados comparativos e a curadoria editorial, está sob Creative Commons Atribuição NãoComercial CompartilhaIgual 4.0 Internacional. Reutilizar exige crédito ao autor, veta uso comercial e obriga o derivado a adotar a mesma licença. Ver [LICENSE-CONTENT](LICENSE-CONTENT).

A página embute componentes de terceiros que mantêm as próprias licenças, com os avisos de copyright preservados no código: React 18.3.1, da Meta Platforms, sob MIT, e a fonte Archivo, da Omnibus-Type, sob SIL Open Font License 1.1.
