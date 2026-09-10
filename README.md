# Dossiê i18n: Europa Ocidental

Página que compara Portugal, Alemanha, Reino Unido e Espanha em sete eixos de internacionalização: idioma, moeda, imposto, fuso horário, base legal, meios de pagamento e feriados.

Complemento visual de um Trabalho de Conclusão de Curso. Roda inteira no navegador, sem servidor de aplicação.

Publicado em https://fellipegabriel.github.io/nacionalizacao/

## Estrutura

```
index.html                    a página em um único arquivo HTML
.github/workflows/deploy.yml  publicação automática no GitHub Pages
```

O `index.html` reúne o conteúdo, o CSS e o JavaScript, sem instalação de pacotes nem etapa de compilação. A única dependência externa é a fonte Archivo, carregada pelo Google Fonts. Sem internet, a página continua funcionando com a fonte padrão do sistema, que pode alterar as quebras de linha.

O arquivo está organizado nesta ordem:

1. Estilos: tipografia, paletas dos países, componentes, animações e regras responsivas.
2. Conteúdo em HTML: abertura, navegação, introdução, dossiê de Portugal, tabela comparativa e rodapé.
3. Templates HTML dos dossiês de Alemanha, Reino Unido e Espanha. Portugal é reutilizado a partir do conteúdo inicial.
4. JavaScript: seleção do país, animações, navegação, progresso de leitura e relógios.

Para editar textos, procure a frase no HTML ou o template `country-DE`, `country-UK` ou `country-ES`. Para alterar as cores, procure as regras `html[data-country]`. Os dados de câmbio continuam sendo referências estáticas, como na versão original; os relógios são atualizados a cada segundo.

A troca de país atualiza os elementos existentes para preservar as transições e a revelação ao rolar. Sem JavaScript, o conteúdo inicial de Portugal e a tabela continuam disponíveis, mas os controles interativos e os relógios não funcionam.

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

A fonte Archivo, da Omnibus-Type, é carregada pelo Google Fonts e está sob [SIL Open Font License 1.1](https://github.com/google/fonts/blob/main/ofl/archivo/OFL.txt). O HTML não contém mais arquivos de fonte embutidos. A página não depende de React nem do runtime de exportação do Canvas.
