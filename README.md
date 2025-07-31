# Entendimento do Negócio

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

# Entendimento dos Dados

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


# Desenvolvimento dos projetos

## Projeto People Analytics - RH - Clusterização Funcionários

Neste projeto foram realizadas as seguintes etapas:

1- Análise Exploratória de Dados (EDA), buscando entender as variáveis em relação a taxa de rotatividade;

2- Tratamento das variáveis utilizando RobustScaler para variáveis numéricas e One-Hot-Encoder para variáveis categóricas;

3- Redução da dimensionalidade para aplicação em modelos de Clusterização;

4- Teste dos modelos de K-Means e Misturra Gaussiana, onde a Mistura Gaussiana apresentou um melhor resultado;

5- Análise exploratória das variáveis em cada um dos clusters obtidos;

6- Considerações finais e Recomendações para o Negócio.


## Projeto People Analytics - RH - Modelo Regressão Logística

Neste projeto foram realizadas as seguintes etapas:

1- Análise de todas as categorias de cada variável X Taxa de rotatividade;

2- Verificação a distribuição de cada variável numérica diferenciando indivíduos com target = 0 e target = 1;

3- Divisão dos dados entre treino e teste, sendo 70% para treino e 30% para teste;

4- Preenchimento dos nulos pela média em variáveis numéricas e a moda em variáveis categóricas;

5- Verificação a linearidade com o Log Odds (R²>0,85);

6- Transformação as variáveis não lineares;

7- Categorização das variáveis que ainda não ficaram lineares;

8- Modelagem utilizando Regressão Logística do StatsModels por ser altamente explicativa para o negócio;

9- Avaliação do modelo utilizando as métricas AUC, KS e Gini;

10- Conclusão, Impacto no Negócio e Recomendações.



# Conclusão, Impacto no Negócio e Recomendações

## Conclusão

O modelo de Regressão Logística construído demonstrou bom desempenho tanto no conjunto de treino quanto no conjunto de teste, com AUC de 0.74 (treino) e 0.73 (teste), o que indica boa capacidade discriminativa. Em outras palavras, o modelo consegue diferenciar corretamente funcionários com maior e menor probabilidade de deixar a empresa.

Além disso: • O KS (Kolmogorov-Smirnov) acima de 0.39 em ambos os conjuntos sugere uma separação clara entre as distribuições das classes (sair vs. permanecer). • O coeficiente de Gini em torno de 0.47 reforça a estabilidade e o poder preditivo do modelo.

O gráfico de decil mostra uma boa monotonicidade: à medida que os decis aumentam, a taxa de saída (“event rate”) também aumenta, tanto no treino quanto no teste. Isso indica que o modelo está bem calibrado e que os scores gerados refletem o risco real de saída de forma coerente.

## Impactos no negócio

- **Redução da rotatividade previsível** - O modelo permite antecipar quais funcionários têm maior chance de deixar a empresa, possibilitando ações preventivas como conversas de retenção, ajustes de clima ou benefícios direcionados.

- **Melhoria na alocação de recursos de RH** - A equipe de RH pode focar esforços nos grupos de maior risco, tornando as ações de engajamento mais eficazes.

- **Planejamento de sucessão mais estratégico** - Com a previsão de possíveis desligamentos, líderes podem se preparar com antecedência, organizando treinamentos internos ou abrindo vagas externas de forma planejada.

- **Redução de custos com contratação e onboarding** - Antecipar e mitigar saídas evita gastos com recrutamento, integração e queda de produtividade associada a perdas inesperadas.

- **Base para políticas de retenção orientadas por dados** - O modelo pode ser utilizado continuamente para avaliar a efetividade de iniciativas de retenção, ajustando políticas com base em evidências concretas.


## Recomendações

- **Desenvolver planos de retenção direcionados** - Crie ações específicas para os funcionários que o modelo identifica como de alto risco. Isso pode incluir bônus de retenção, planos de carreira acelerados, programas de reconhecimento e acompanhamento individual com líderes.

- **Revisar políticas internas com base em dados** - Use os insights do modelo para revisar políticas de carga horária, promoções, salários, clima e benefícios.

- **Atuar preventivamente nos grupos de risco** - Com base na pontuação do modelo, classifique os funcionários em faixas de risco e defina protocolos para cada grupo. Exemplo: acompanhamento trimestral para risco médio e ações imediatas para risco alto.

- **Melhorar a experiência de integração e acompanhamento** - Funcionários recém-contratados com alto risco previsto devem receber um onboarding reforçado e acompanhamento próximo nos primeiros meses.

- **Transformar a rotatividade em KPI gerencial** - Incorpore a probabilidade de saída como uma métrica acompanhada periodicamente pelas lideranças, associando metas de retenção aos objetivos dos gestores.
