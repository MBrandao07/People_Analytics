# People_Analytics

## Entendimento do Negócio

A RetaiX emprega cerca de 4000 funcionários. No entanto, todos os anos, cerca de 15% de seus funcionários deixam a empresa e precisam ser substituídos por novos funcionários que estão disponíveis no mercado. A gestão acredita que esse nível de rotatividade (funcionários saindo, seja por vontade própria ou porque foram demitidos) é ruim para a empresa, pelos seguintes motivos:

- Dificuldade no cumprimento dos prazos, resultando em perda de reputação entre consumidores e parceiros;

- Um departamento considerável precisa ser mantido para fins de recrutamento de novos talentos;

- Na maioria das vezes, os novos funcionários precisam ser treinados para o trabalho e/ou precisam de tempo para se ambientarem à empresa.

Por outro lado, a RetailX também percebeu que poderia melhorar o relacionamento com os clientes, por meio do entendimento do comportamento de compra deles. A empresa possui dados de campanhas, compras, cadastro e até da renda de cada cliente.

Diante deste cenário a empresa decidiu investir em dois projetos:

- **Projeto de RH**;

- Projeto de CRM.

Neste momento, focaremos no Projeto de RH com os seguintes objetivos:

- Análisar os dados para entender padrões de comportamentos dos funcionários (obter personas);

- Análisar os dados para entender as variáveis que mais influenciam na alta rotatividade dos funcionários;

- Obter a probabilidade de um funcionário sair da empresa e com isso as variáveis que mais impactam o aumento da probabilidade de saída;

- Gerar um relatório com as conclusões para que o gestor do RH possa tomar as devidas providências para que a rotatividade seja reduzida.

## Entendimento dos Dados

Temos as seguintes bases disponíveis e seus respectivos conceitos:

tb_funcionarios.csv – Base de público contendo informações dos funcionários;

tb_pesquisa_funcionarios.csv – Base contendo informações de uma pesquisa realizada com os funcionários;

tb_pesquisa_gestores.csv – Base contendo informações de uma pesquisa realizada com os gestores acerca do desempenho dos funcionários.


Temos também o dicionário de dados explicando cada coluna:


| Variáveis                       | Descrição                                                                 | Domínios                                                      |
|--------------------------------|---------------------------------------------------------------------------|---------------------------------------------------------------|
| Idade                          | Idade do funcionário                                                      |                                                               |
| Rotatividade                   | Se o funcionário deixou a empresa no ano anterior ou não                  | 0 = Permaneceu, 1 = Saiu                                      |
| ViagensDeNegocio               | Frequência de viagens a trabalho no último ano                            |                                                               |
| Departamento                   | Departamento na empresa                                                   |                                                               |
| DistanciaDeCasa                | Distância de casa até o trabalho (em km)                                  |                                                               |
| Educacao                       | Nível de Educação                                                         | 1 = Abaixo do Superior, 2 = Sup. Incompleto, 3 = Bacharel, 4 = Mestre, 5 = Doutor |
| CampoDeEducacao                | Área de formação acadêmica                                                |                                                               |
| ContagemDeEmpregados           | Número total de funcionários (constante)                                  |                                                               |
| IDDoEmpregado                  | Número/ID único do funcionário                                            |                                                               |
| SatisfacaoComAmbiente          | Satisfação com o ambiente de trabalho                                     | 1 = Baixo, 2 = Médio, 3 = Alto, 4 = Muito Alto                |
| Genero                         | Gênero do funcionário                                                     |                                                               |
| EnvolvimentoNoTrabalho         | Nível de envolvimento no trabalho                                         | 1 = Baixo, 2 = Médio, 3 = Alto, 4 = Muito Alto                |
| NivelDoCargo                   | Nível do cargo ocupado na empresa                                         | 1 a 5                                                         |
| NomeDaFuncao                   | Nome da função desempenhada                                               |                                                               |
| SatisfacaoNoTrabalho           | Nível de satisfação no trabalho                                           | 1 = Baixo, 2 = Médio, 3 = Alto, 4 = Muito Alto                |
| EstadoCivil                    | Estado civil do funcionário                                               |                                                               |
| RendaMensal                    | Renda mensal (em rúpias)                                                  |                                                               |
| NumeroDeEmpresas               | Número total de empresas pelas quais o funcionário passou                 |                                                               |
| MaiorDe18                      | Indica se o funcionário é maior de 18 anos                                | 1 = Sim                                                       |
| AumentoPercentualSalario       | Percentual de aumento salarial no último ano                              |                                                               |
| AvaliacaoDeDesempenho          | Avaliação de desempenho no último ano                                     | 1 = Baixo, 2 = Bom, 3 = Excelente, 4 = Excepcional            |
| HorasPadrao                    | Carga horária padrão                                                      | Geralmente constante                                          |
| NivelDeOpcaoDeCompraDeAcoes    | Nível de opções de compra de ações recebidas                              |                                                               |
| TotalDeAnosTrabalhados         | Total de anos trabalhados ao longo da carreira                            |                                                               |
| TreinamentosNoUltimoAno        | Número de treinamentos realizados no último ano                           |                                                               |
| EquilibrioTrabalhoVida         | Nível de equilíbrio entre trabalho e vida pessoal                         | 1 = Ruim, 2 = Bom, 3 = Melhor, 4 = Ótimo                      |
| AnosNaEmpresa                  | Número total de anos na empresa atual                                     |                                                               |
| AnosDesdeUltimaPromocao        | Anos desde a última promoção                                              |                                                               |
| AnosComAtualGestor             | Anos trabalhando com o gestor atual                                       |                                                               |



## Projeto People Analytics - RH - Clusterização Funcionários

Neste projeto foram realizadas as seguintes etapas:

1- Análise Exploratória de Dados (EDA), buscando entender as variáveis em relação a taxa de rotatividade;

2- Tratamento das variáveis utilizando RobustScaler para variáveis numéricas e One-Hot-Encoder para variáveis categóricas;

3- Redução da dimensionalidade para aplicação em modelos de Clusterização;

4- Teste dos modelos de K-Means e Misturra Gaussiana, onde a Mistura Gaussiana apresentou um melhor resultado;

5- Análise exploratória das variáveis em cada um dos clusters obtidos;

6- Considerações finais e Recomendações para o Negócio.
