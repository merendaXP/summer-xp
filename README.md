# MTM de bancários
> Cáculo de MTM de bancários da carteira própria da XP.

Rotina em Python para cálculo de MTM de bancários da carteira própria da XP que:
   1. Seleciona os bancarios dos ativos de renda fixa na carteira própria da corretora e seus emissores (RLESTOQUECARTEIRA).
   2. Armazena os ativos em objetos da classe Asset e armazena os objetos em um dicionário.
   3. Busca em um de para o nome registrado no Lajeado para cada nome de emissor no Virtual
   4. Consulta os ratings e a data de registro dos emissores no Lajeado e os armazena nos objetos
   5. Armazena tabelas de pesos referente a rating, indexador e term em um objeto da classe Scores
      que possui métodos para retornar os pesos referentes a cada rating, indexador e term.
   6. Armazena todos os objetos em um fila para ser usado multi-threading para puxar e armazenar os segintes dados por API:
      - Deal type
      - Ratio
      - Spread
      - Maturity Date
      - Indexer
   7. Armazena os ativos em outro dicionário
   8. Armazena curvas de DI e IPCA futuro em objetos das classes PreCurve e IpcaCurve, respectivamente, com métodos para retornar
      a taxa de acordo com a data solicitada
   9. Armazena os seguintes dados:
      - Pesos
      - Penalty com base no peso total
      - Taxa DI e IPCA no vencimento do papel
   10. Calcula a taxa MTM de cada ativo e o armazena
   11. Calcula MTM e o armazena
   12. Importa todos os dados armazenados para um aquivo .csv

## Instalação

OS X & Linux:

```sh
npm install my-crazy-module --save
```

Windows:

```sh
edit autoexec.bat
```

## Exemplo de uso

Alguns exemplos interessantes e úteis sobre como seu projeto pode ser utilizado. Adicione blocos de códigos e, se necessário, screenshots.

_Para mais exemplos, consulte a [Wiki][wiki]._ 

## Configuração para Desenvolvimento

Descreva como instalar todas as dependências para desenvolvimento e como rodar um test-suite automatizado de algum tipo. Se necessário, faça isso para múltiplas plataformas.

```sh
make install
npm test
```

## Histórico de lançamentos

* 0.2.1
    * MUDANÇA: Atualização de docs (código do módulo permanece inalterado)
* 0.2.0
    * MUDANÇA: Remove `setDefaultXYZ()`
    * ADD: Adiciona `init()`
* 0.1.1
    * CONSERTADO: Crash quando chama `baz()` (Obrigado @NomeDoContribuidorGeneroso!)
* 0.1.0
    * O primeiro lançamento adequado
    * MUDANÇA: Renomeia `foo()` para `bar()`
* 0.0.1
    * Trabalho em andamento

## Meta

Seu Nome – [@SeuNome](https://twitter.com/...) – SeuEmail@exemplo.com

Distribuído sob a licença XYZ. Veja `LICENSE` para mais informações.

[https://github.com/yourname/github-link](https://github.com/othonalberto/)

## Contributing

1. Faça o _fork_ do projeto (<https://github.com/yourname/yourproject/fork>)
2. Crie uma _branch_ para sua modificação (`git checkout -b feature/fooBar`)
3. Faça o _commit_ (`git commit -am 'Add some fooBar'`)
4. _Push_ (`git push origin feature/fooBar`)
5. Crie um novo _Pull Request_

[npm-image]: https://img.shields.io/npm/v/datadog-metrics.svg?style=flat-square
[npm-url]: https://npmjs.org/package/datadog-metrics
[npm-downloads]: https://img.shields.io/npm/dm/datadog-metrics.svg?style=flat-square
[travis-image]: https://img.shields.io/travis/dbader/node-datadog-metrics/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/dbader/node-datadog-metrics
[wiki]: https://github.com/seunome/seuprojeto/wiki
