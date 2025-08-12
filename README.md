# **People_Analytics_CRM**

# 1- Entendimento do Negócio

A RetaiX emprega cerca de 4000 funcionários. No entanto, todos os anos, cerca de 15% de seus funcionários deixam a empresa e precisam ser substituídos por novos funcionários que estão disponíveis no mercado. A gestão acredita que esse nível de rotatividade (funcionários saindo, seja por vontade própria ou porque foram demitidos) é ruim para a empresa, pelos seguintes motivos:

- Dificuldade no cumprimento dos prazos, resultando em perda de reputação entre consumidores e parceiros;

- Um departamento considerável precisa ser mantido para fins de recrutamento de novos talentos;

- Na maioria das vezes, os novos funcionários precisam ser treinados para o trabalho e/ou precisam de tempo para se ambientarem à empresa.

Por outro lado, a RetailX também percebeu que poderia melhorar o relacionamento com os clientes, por meio do entendimento do comportamento de compra deles. A empresa possui dados de campanhas, compras, cadastro e até da renda de cada cliente.

Diante deste cenário a empresa decidiu investir em dois projetos:

- Projeto de RH;

- **Projeto de CRM**.

## Objetivo

Neste momento, focaremos no **Projeto de CRM** com os seguintes objetivos:

- Encontrar personas no grupo de clientes para identificar padrões de comportamento;

- Analisar cada persona e verificar se existem ações que podem ser feitas para melhorar a relação com os clientes;

- Gerar um relatório com as conclusões para que o gestor do CRM possa tomar as devidas providências para que a empresa aumente o faturamento, reduze o custos com campanhas e melhore o relacionamento com os clientes.


# 2- Entendimento dos dados

A base de dados é bem consistente, com uma pequena porcentagem de nulos e valores que fazem sentido.

Das características que podemos tirar da base, temos por exemplo:

- Idade
- Estado Civil
- Nível de educação
- Quantidade de filhos
- Gastos com determinados produtos
- Taxa de aceitação de cada campanha
- Taxa de reclamação
- Modalidade de compra

Nessa etapa já foi possível retirar alguns insights, como por exemplo:

- Quanto mais filhos o cliente tinha, menor era sua taxa de aceitação das campanhas
- Clientes com mais de 80 anos, apesar de serem poucos, possuiam uma taxa de aceitação de campanhas muito alta, acima de 50%
- Pessoas que estavam sozinhas, como viúvos, solteiros e divorciados possuiam uma taxa de aceitação maior do que os casados ou em união estável
- Pessoas com doutorado e mestrado possuíam mais do que o dobro de taxa de aceitação do que pessoas só com o ensino médio

# 3- Preparação dos dados

Após a análise exploratória inicial, chegou a hora de preparar os dados para o modelo de clusterização.

Nesta etapa foram realizados os seguintes passos para a preparação dos dados:

1- Preenchimento dos valores nulos pela **mediana** em variáveis numéricas;

2- Preenchimento dos valores nulos pela **moda** nas variáveis categóricas;

3- Padronização das variáveis numéricas utilizando **Robust Scaler**, pois a base possuia muitas outliers;

4- Aplicação de **One-Hot-Encoding** nas variáveis categóricas, pois sua cardinalidade é baixa;

5- Redução da dimensionalidade utilizando **PCA** (preservando 95% da variância original)

Após esta preparação os dados estavam prontos para o modelo de clusterização.

# 4- Modelagem

Foram testados dois modelos de clusterização, K-Means e Modelo de Mistura Gaussiana.

No K-Means foi utilizado o Método da Silhueta para verificar qual seria a melhor quantidade de clusters a serem utilizados, porém como o resultado foi apenas 2 clusters, então decidi testar o segundo método.

Já no Modelo de Mistura Gaussiana a melhor configuração foi utilizando 8 clusters, que agregaria muito mais valor ao projeto, então esse foi o modelo escolhido.

O modelo foi treinado e a base de 2240 clientes foram divididos em 8 grupos, sendo que o maior cluster possuia 476 clientes e o menor 72 clientes.

# 5- Insights e Recomendações para o negócio

Após essa divisão foi possível extrair insights do comportamento de cada grupo.

- A taxa de aceitação média de pelo menos uma campanha foi de 27,19%

- Tivemos grupos de clientes que tiveram a aceitação das campanhas incrivelmente altas, como os grupos 7 com 63,16%, 1 com 45,37% e 3 com 40,28%.

- Também tivemos grupos de clientes com aceitação das campanhas muito baixa, como o grupo 0 com 11,22% e o grupo 5 com 15,76%.
<br><br>

Alguns outros insights e as recomendações para o negócio podem ser vistas a seguir:

**Ex. 1:**

**Insight**: Os clientes dos grupos com as maiores taxas de aceitação (grupos 1, 3 e 7) praticamente não possuem filhos

**Recomendação**: Focar em campanhas e propagandas que são compatíveis com o estilo de vida de pessoas que não tem filhos pode aumentar ainda mais o faturamento

**Ex. 2:**

**Insight**: Clientes dos grupos 1, 6 e 7 consumiram muito mais vinho que os outros grupos

**Recomendação**: Recomendar propagandas e ofertas de vinhos para esses clientes pode ser uma boa estratégia!

**Ex. 3:**

**Insight**: Clientes dos grupos 1, 2, 3, 6 e 7 realizaram mais compras na loja do que os demais grupos

**Recomendação**: Realizar eventos presenciais e fornecer atendimento personalizado são ótimas maneiras de incentivar os clientes a voltarem a loja

--------------------------------------------------------------

**Muitos outros insights e recomendações podem ser conferidos na apresentação do projeto que também está anexada nesse repositório!**

https://github.com/MBrandao07/People_Analytics_CRM/tree/main/Apresentacao


