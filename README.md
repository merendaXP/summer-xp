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
(colocar os arquivos .py e .csv na pasta)
```
## Requisitos
- Acessos

``` \\viseu\Back_Office_Renda_Fixa\Arquivos\Compartilhamento - Outras Equipes\Risco e Trading Finance```
``` \\viseu\Asset_xpi\Precificacao\Curvas Mellon```
- Planilha de/para atualizada

## Exemplo de uso

Para uso da rotina com todos os requisitos basta acessar o arquivo mtm_bancarios.py e alterar a variável date para o dia desejado que a rotina seja executada:

![main](https://user-images.githubusercontent.com/61240450/74881291-ce7a5e00-534b-11ea-87cb-702edb2cdd48.JPG)

## Entendimento do arquivo gerado

- Caso o de/para esteja desatualizado, ou seja não consiga encontrar o emissor registrado no lajeado para um emissor registrado no virtual na terceira coluna haverá indicação desse ocorrido:

![depara](https://user-images.githubusercontent.com/61240450/74882683-49dd0f00-534e-11ea-9b48-889e5b341392.jpg)

- Caso o indexador não esteja registrado, será indicado na quinta coluna:

![indexador](https://user-images.githubusercontent.com/61240450/74882942-b1935a00-534e-11ea-8314-e40c01145fe9.jpg)

- O mesmo ocorre para deal type na sétima coluna:

![deal type](https://user-images.githubusercontent.com/61240450/74883097-fdde9a00-534e-11ea-8314-8ff756acb0da.jpg)

- Caso o rating do emissor não esteja registrado no lajeado, será indicado na nona coluna:

![rating](https://user-images.githubusercontent.com/61240450/74883297-6b8ac600-534f-11ea-8fc4-92f286cd85fe.jpg)

- Caso não seja encontrado o vencimento nas curvas futuras de DI e IPCA, será indicado o valor 10, acontece caso o ativo ja tenha vencido


## Detalhamento de funções

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

Pedro Henrique Bonfim Leal – pedro.leal@xpi.com.br
