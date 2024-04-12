1. Olhei as distribuições entre o grupo controle e teste e são homogêneas entre os gêneros, países e dispositivo de acesso.
![[Pasted image 20240409161931.png]]
2. A métrica-chave de desempenho (KPI) definida para o projeto foi o número de compras realizadas, uma vez que a mudança no formato de preenchimento visava facilitar a jornada de compra. Além disso, escolhi o faturamento como uma métrica secundária do projeto, com o objetivo de analisar se o aumento no número de compras está refletindo positivamente na receita ou se está afetando negativamente o ticket médio.
##### Definição de Hipóteses
+ H0: Não existe diferença no número de compras entre os dois grupos.
+ H1: O Grupo A (teste) teve um número maior de compras que o Grupo B (controle)
+ Nível de Confiança: 95% ou 0,95
+ alpha: 5% ou 0,05
### Testes para o Usuário Médio
##### Ao realizar um t-Test de duas amostras assumindo variâncias iguais utilizando a KPI número de compras, obtive os seguintes resultados:
![[Pasted image 20240409163435.png]]
+ Apesar do Uplift ter sido negativo e do número de compras no Grupo de Teste ter sido 0,3538% menor do que no Grupo de Controle, o p-valor de 0,2891 foi maior do que o alpha definido. Portanto, não temos evidências suficientes para rejeitar a hipótese nula de que não houve diferença significativa nas compras entre os dois grupos.
##### Ao realizar um t-Test de duas amostras assumindo variâncias iguais utilizando a métrica secundária/Health Receita, obtive os seguintes resultados:
![[Pasted image 20240409164446.png]]
+ Embora o Uplift tenha sido negativo e a receita gerada pelo Grupo de Teste tenha sido 0,3136% menor que a do Grupo de Controle, o p-valor de 0,3211 foi superior ao alpha definido. Portanto, não dispomos de evidências suficientes para rejeitar a hipótese nula de que não houve diferença significativa na receita entre os dois grupos.
##### Conclusões dos testes para o Usuário Médio
+ Mesmo não alcançando significância estatística em ambos os testes, o fato de o Uplift ser negativo sugere que, em média, o novo método de Preenchimento de Dados foi ineficaz para o usuário médio.
+ Mesmo que o teste A/B tenha sido perdedor para o usuário médio, isso não significa que devemos encerrar nossas investigações. Dada a complexidade do mundo atual, é essencial explorar além e realizar uma análise segmentada. É nesses nichos específicos que podem estar escondidas as verdadeiras oportunidades de ouro.
### Testes para o segmento Dispositivo/Tipo de Acesso
##### Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para o aplicativo, os resultados foram os seguintes:
![[Pasted image 20240409175757.png]]
+ Pode-se observar que houve um impacto negativo em ambas as métricas, indicando que o tratamento não foi eficaz para o segmento de aplicativos móveis (telefone).
##### Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para compras feita no site, os resultados foram os seguintes:
![[Pasted image 20240410071745.png]]
+ Pode-se observar que houve um impacto negativo em ambas as métricas, indicando que o tratamento não foi eficaz para o segmento de acesso pelo site(internet).
##### Conclusões dos testes para o segmento Dispositivo
 + Embora não tenhamos alcançado significância estatística em nenhum dos testes, a constatação de um Uplift negativo sugere que, em média, o novo método de Preenchimento de Dados foi ineficaz para ambos os segmentos de dispositivos.
### Testes para o segmento Gênero
##### Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para homens, os resultados foram os seguintes:
![[Pasted image 20240410072112.png]]
+ No primeiro teste, com a KPI (número de compras), registrou-se um uplift negativo de -0,2983%, enquanto no segundo teste houve um uplift de 0,0891% nos gastos para o segmento masculino.
##### Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita exclusivamente para mulheres, os resultados foram os seguintes:
![[Pasted image 20240410072402.png]]
 + No primeiro teste, com a KPI (número de compras), registrou-se um uplift negativo de -0,4035%, enquanto no segundo teste houve um uplift negativo de de -0,7306% nos gastos para o segmento feminino.

##### Conclusões dos testes para o segmento Gênero
 + Apesar de o novo método de Preenchimento Automático ter gerado um aumento na receita para o segmento masculino, há uma alta probabilidade de que isso tenha ocorrido devido à aleatoriedade e não à modificação. Entretanto, tanto na KPI quanto no segmento feminino, continuamos a observar um desempenho negativo.

### Testes para o segmento País
##### Ao realizar um teste t de duas amostras assumindo variâncias iguais, utilizando a KPI número de compras e a métrica secundária Receita individualmente para cada país, obtive os seguintes resultados:
###### Austrália:
![[Pasted image 20240410073444.png]]
###### Brasil:
![[Pasted image 20240410073335.png]]
###### Canadá:
![[Pasted image 20240410073355.png]]
###### Deutsch
![[Pasted image 20240410073547.png]]
###### Espanha:
![[Pasted image 20240410073612.png]]
###### França:
![[Pasted image 20240410073628.png]]
###### Grã-Bretanha:
![[Pasted image 20240410073713.png]]
###### México:
![[Pasted image 20240410073732.png]]
###### Turquia:
![[Pasted image 20240410073755.png]]
###### Estados Unidos:
![[Pasted image 20240410073813.png]]

##### Conclusões dos testes para o segmento País:
 + Apesar do Grupo de Teste ter registrado um Uplift positivo em ambas as métricas em países como Austrália, México, Turquia e Estados Unidos, somente na Austrália podemos afirmar com 95% de confiança que esse aumento não foi devido à aleatoriedade. Nos demais países, observou-se um Uplift negativo.
### Conclusões Finais:
+ Após a realização de todos os testes para o usuário médio e em todos os segmentos, observamos que o único segmento que apresentou um Uplift positivo e estatisticamente significativo foi na Austrália.

+ Os dados de compras utilizados na análise abrangem um período de 4 anos. Vamos considerar um cenário hipotético: durante esses 4 anos, foram registradas 1017 compras na Austrália, gerando um faturamento de R$1.916.778,00 para a empresa. Isso representou 2,22% do faturamento total das compras do estudo. Supondo que todas as compras fossem realizadas utilizando o Preenchimento Automático, o faturamento aumentaria para R$1.992.829,59, resultando em um aumento de R$76.051,59. Isso representaria 2,31% do faturamento total do estudo.

+ Entretanto, as compras provenientes da Austrália representam apenas 2,20% do total das compras da empresa. Portanto, com base nessa análise, conclui-se concluir que não vale a pena implementar essa estratégia exclusivamente para esse segmento.
