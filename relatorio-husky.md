# Relatório - Configuração do Husky

## Objetivo

Esta atividade teve como objetivo configurar hooks do Husky em um repositório Git para garantir que o código esteja corretamente compilado, testado e de acordo com boas práticas antes de ser integrado ao repositório principal. A prática simula um fluxo de integração contínua simples, promovendo a qualidade e padronização do desenvolvimento.

## Etapas Realizadas

1. Criação de um repositório no GitHub chamado `ponderada_husky`.
2. Inicialização do projeto com `npm init -y`.
3. Instalação do Husky com `npm install husky --save-dev`.
4. Adição manual do script `"prepare": "husky install"` ao `package.json` (devido à ausência do comando `npm set-script` na versão instalada).
5. Execução do comando `npm run prepare`, que ativou o Husky.
6. Criação do hook `pre-commit` com o comando:
   ```bash
   npx husky add .husky/pre-commit "npm run build && npm run lint"

## Testes Realizados

Pré-commit
Ao realizar um commit com git commit -m "test: validando pre-commit", o Husky executou os comandos de build e lint. Ambos foram simulados com sucesso, impedindo o commit apenas em caso de erro.

Print:

Pré-push
Ao executar git push, o hook de pré-push foi acionado, executando o comando npm test. O teste simulado foi concluído com sucesso, permitindo o envio das alterações ao repositório remoto.

Print:


## Conclusão

A configuração do Husky se mostrou eficaz para reforçar boas práticas de desenvolvimento. Os hooks impediram que código não testado ou mal formatado fosse enviado ao repositório remoto. Essa abordagem automatizada reduz erros, melhora a legibilidade do código e aproxima o processo de um pipeline de CI/CD real, mesmo em projetos locais ou educacionais.

## Referência
FERRAZ, Filipe. Husky Git Hooks. 2023. Disponível em: https://typicode.github.io/husky/#/. Acesso em: 11 maio 2025.
