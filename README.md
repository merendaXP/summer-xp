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

```sh
 No CMD
> mkdir mtm_bancarios
> cd mtm_bancarios
> py -m venv .venv
(py pode ser python ou python3)
> .venv\scripts\activate
(colocar requirements.txt na pasta)
> pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt
(colocar os arquivos na pasta)
```
## Requsitos
-Acessos
``` \\viseu\Back_Office_Renda_Fixa\Arquivos\Compartilhamento - Outras Equipes\Risco e Trading Finance```
``` \\viseu\Asset_xpi\Precificacao\Curvas Mellon```
- de_virtual_para_lajeado.csv atualizado

## Exemplo de uso

Alguns exemplos interessantes e úteis sobre como seu projeto pode ser utilizado. Adicione blocos de códigos e, se necessário, screenshots.


## Configuração para Desenvolvimento

Descreva como instalar todas as dependências para desenvolvimento e como rodar um test-suite automatizado de algum tipo. Se necessário, faça isso para múltiplas plataformas.

```sh
make install
npm test
```

## Histórico de lançamentos

* 0.1.0
    * O primeiro lançamento adequado
* 0.0.1
    * Testes em andamento

## Meta

Seu Nome – pedro.leal@xpi.com.br
