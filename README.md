# Teste A/B Electronic House
<p align="center">
  <img src="https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/99611ff6-3d15-42e2-b468-8ee74bfcd6d1" width="100%" height="300">
</p>

# 1. Problema de Negócio
A Electronic House, um ecommerce de produtos de informática com presença global, desenvolveu uma nova função de preenchimento automático de dados do cartão de crédito em resposta à demanda do Diretor de Produtos. Através de um Teste A/B, a empresa busca determinar se essa funcionalidade é mais eficaz do que o preenchimento manual, com o objetivo de aprimorar a experiência do cliente e impulsionar as vendas. A análise comparativa entre os métodos de pagamento permitirá que a empresa tome decisões estratégicas para otimizar seu processo de checkout e maximizar o crescimento das vendas online em escala global.

# 2. Ferramentas Utilizadas

**Ferramentas para Análise de Dados**
- Microsoft Excel: Escolha devido à velocidade e quantidade moderada de dados. Para casos mais complexos ou grandes volumes de dados, Python seria preferível.
- Estatística: Aplicada para conduzir testes de hipóteses e extrair insights significativos e confiável dos resultados.

**Habilidades e Abordagem:**
- Pensamento Crítico e Resolução de Problemas: Habilidades fundamentais aplicadas para analisar, solucionar problemas e tomar decisões ao longo do projeto.
- Pensamento Analítico: Utilizado para decompor o problema em componentes menores, segmentar os dados e identificar padrões ou insights relevantes, permitindo uma compreensão mais profunda e informada do contexto do estudo.

  # 3. Descrição dos Dados 
| Campo   | Descrição                                                                                   |
|---------|---------------------------------------------------------------------------------------------|
| uid     | Identificador único para cada cliente.                                                      |
| country | País onde a transação foi realizada.                                                        |
| gender  | Gênero do cliente.                                                                         |
| spent   | Valor gasto na transação.                                                                   |
| purchases | Número de compras realizadas.                                                             |
| date    | Data da transação.                                                                          |
| group   | Método de preenchimento dos dados do cartão de crédito: A = Automático, B = Manual.         |
| device  | Tipo de dispositivo utilizado para realizar a transação: I = Internet, A = Aplicativo móvel. |

# 4. Desenvolvimento da Solução
## 4.1 Analisando Homogeneidade entre os Grupos

Verificar as distribuições entre os grupos controle e teste para garantir a homogeneidade em relação aos gêneros, países e dispositivos de acesso.
   
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/2255ba6c-8d46-4348-a60d-c1eb057044c7)

## 4.2 Definição da KPI
A métrica-chave de desempenho (KPI) definida para o projeto foi o número de compras realizadas, uma vez que a mudança no formato de preenchimento visava facilitar a jornada de compra. Além disso, escolhi o faturamento como uma métrica secundária do projeto, com o objetivo de analisar se o aumento no número de compras está refletindo positivamente na receita ou se está afetando negativamente o ticket médio.

## 4.3 Definição de Hipóteses
+ H0: Não existe diferença no número de compras entre os dois grupos.
+ H1: O Grupo A (teste) teve um número maior de compras que o Grupo B (controle)
+ Nível de Confiança: 95% ou 0,95
+ alpha: 5% ou 0,05
## 4.4 Testes para o Usuário Médio
### 4.4.1 Ao realizar um t-Test de duas amostras assumindo variâncias iguais utilizando a KPI número de compras, obtive os seguintes resultados:

![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/41fc7caf-971f-4023-84b5-3346776d8459)

+ Apesar do Uplift ter sido negativo e do número de compras no Grupo de Teste ter sido 0,3538% menor do que no Grupo de Controle, o p-valor de 0,2891 foi maior do que o alpha definido. Portanto, não temos evidências suficientes para rejeitar a hipótese nula de que não houve diferença significativa nas compras entre os dois grupos.
### 4.4.2 Ao realizar um t-Test de duas amostras assumindo variâncias iguais utilizando a métrica secundária/Health Receita, obtive os seguintes resultados:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/5139ce33-17e3-492a-9583-ebdccac5ac02)

+ Embora o Uplift tenha sido negativo e a receita gerada pelo Grupo de Teste tenha sido 0,3136% menor que a do Grupo de Controle, o p-valor de 0,3211 foi superior ao alpha definido. Portanto, não dispomos de evidências suficientes para rejeitar a hipótese nula de que não houve diferença significativa na receita entre os dois grupos.
### 4.4.3 Conclusões dos testes para o Usuário Médio
+ Mesmo não alcançando significância estatística em ambos os testes, o fato de o Uplift ser negativo sugere que, em média, o novo método de Preenchimento de Dados foi ineficaz para o usuário médio.
+ Mesmo que o teste A/B tenha sido perdedor para o usuário médio, isso não significa que devemos encerrar nossas investigações. Dada a complexidade do mundo atual, é essencial explorar além e realizar uma análise segmentada. É nesses nichos específicos que podem estar escondidas as verdadeiras oportunidades de ouro.
## 4.5 Testes para o segmento Dispositivo/Tipo de Acesso
### 4.5.1 Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para o aplicativo, os resultados foram os seguintes:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/8ffd06ef-d061-4861-8b3f-f08ea2a3fc93)

+ Pode-se observar que houve um impacto negativo em ambas as métricas, indicando que o tratamento não foi eficaz para o segmento de aplicativos móveis (telefone).
### 4.5.2 Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para compras feita no site, os resultados foram os seguintes:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/b7d362f2-5858-456b-bf81-72c201f44f78)

+ Pode-se observar que houve um impacto negativo em ambas as métricas, indicando que o tratamento não foi eficaz para o segmento de acesso pelo site(internet).
### 4.5.3 Conclusões dos testes para o segmento Dispositivo
 + Embora não tenhamos alcançado significância estatística em nenhum dos testes, a constatação de um Uplift negativo sugere que, em média, o novo método de Preenchimento de Dados foi ineficaz para ambos os segmentos de dispositivos.
## 4.6 Testes para o segmento Gênero
### 4.6.1 Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para homens, os resultados foram os seguintes:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/74470397-1bc7-4e92-a8ae-21938f799f2a)

+ No primeiro teste, com a KPI (número de compras), registrou-se um uplift negativo de -0,2983%, enquanto no segundo teste houve um uplift de 0,0891% nos gastos para o segmento masculino.
### 4.6.2 Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para mulheres, os resultados foram os seguintes:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/6aa847e4-59d8-4e77-8b72-3fec1105b4f7)

 + No primeiro teste, com a KPI (número de compras), registrou-se um uplift negativo de -0,4035%, enquanto no segundo teste houve um uplift negativo de de -0,7306% nos gastos para o segmento feminino.

### 4.6.3 Conclusões dos testes para o segmento Gênero
 + Apesar de o novo método de Preenchimento Automático ter gerado um aumento na receita para o segmento masculino, há uma alta probabilidade de que isso tenha ocorrido devido à aleatoriedade e não à modificação. Entretanto, tanto na KPI quanto no segmento feminino, continuamos a observar um desempenho negativo.

## 4.7 Testes para o segmento País
### 4.7.1 Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita individualmente para cada país, obtive os seguintes resultados:
##### 4.7.2 Austrália:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/f1e3f21d-ae24-4384-8341-18d5e54f52b7)

##### 4.7.3 Brasil:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/e8ff1851-0f3d-4919-bdf1-c7f9510e3eac)

##### 4.7.4 Canadá:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/dc842416-0e8e-41e3-b6cb-fbd27deee1ed)

##### 4.7.5 Deutsch
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/a489a409-5a8b-41c1-ac00-cdd0c05a3448)

##### 4.7.6 Espanha:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/0dc6e3ad-11e2-4863-ae1a-fb587cbbac7a)

##### 4.7.7 França:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/78bde709-c3e0-4263-9855-0e67372d1f1f)

##### 4.7.8 Grã-Bretanha:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/eff8e3cf-64aa-44ae-ae48-48f578f4399a)

##### 4.7.9 México:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/66020728-0ab2-4f44-9b94-d578a8703ba2)

##### 4.7.10 Turquia:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/698ac6a8-7a72-4120-ad9c-c535d5154a33)

##### 4.7.11 Estados Unidos:
![image](https://github.com/TiagoTBarreto/ProjetoA-B/assets/137197787/534005e5-3d8a-4d77-a081-5f454ef85ce0)

#### 4.7.12 Conclusões dos testes para o segmento País:
 + Apesar do Grupo de Teste ter registrado um Uplift positivo em ambas as métricas em países como Austrália, México, Turquia e Estados Unidos, somente na Austrália podemos afirmar com 95% de confiança que esse aumento não foi devido à aleatoriedade. Nos demais países, observou-se um Uplift negativo.
## 5. Conclusões Finais:
+ Após a realização de todos os testes para o usuário médio e em todos os segmentos, observamos que o único segmento que apresentou um Uplift positivo e estatisticamente significativo foi na Austrália.

+ Os dados de compras utilizados na análise abrangem um período de 4 anos. Vamos considerar um cenário hipotético: durante esses 4 anos, foram registradas 1017 compras na Austrália, gerando um faturamento de R$1.916.778,00 para a empresa. Isso representou 2,22% do faturamento total das compras do estudo. Supondo que todas as compras fossem realizadas utilizando o Preenchimento Automático, o faturamento aumentaria para R$1.992.829,59, resultando em um aumento de R$76.051,59. Isso representaria 2,31% do faturamento total do estudo.

+ Entretanto, as compras provenientes da Austrália representam apenas 2,20% do total das compras da empresa. Portanto, com base nessa análise, conclui-se concluir que não vale a pena implementar o Preenchimento Automático exclusivamente para esse segmento.
