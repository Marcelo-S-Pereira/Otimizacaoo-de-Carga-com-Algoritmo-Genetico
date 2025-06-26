# **Otimização de Carga com Algoritmo Genético**  

## **Descrição**  
Este projeto implementa um algoritmo genético para otimização de cargas em transporte, selecionando a combinação de itens que maximiza o valor total respeitando restrições de peso e volume. A solução é aplicável em logística, supply chain e gestão de frota, onde decisões de carregamento impactam custos e eficiência operacional.  

## **Tecnologias Utilizadas**  
- **Python** (linguagem de implementação)  
- **Pandas** (manipulação de dados)  
- **GeneticAlgorithm** (biblioteca para otimização evolutiva)  

## **Funcionalidades**  
1. **Leitura e Análise de Dados:**  
   - Processa um dataset contendo itens com peso, volume e valor.  
   - Calcula métricas agregadas (peso total, volume total, valor total).  

2. **Definição de Restrições:**  
   - Configura limites máximos de peso (`sobra_peso`) e volume (`sobra_volume`).  

3. **Algoritmo Genético para Otimização:**  
   - Função de fitness que penaliza soluções inviáveis (excesso de peso/volume).  
   - Parâmetros ajustáveis (tamanho da população, taxas de crossover/mutação).  
   - Seleção elitista para preservar as melhores soluções.  

4. **Resultados da Otimização:**  
   - Exibe os itens selecionados, peso total, volume ocupado e valor agregado.  

## **Estrutura do Código**  
```plaintext
.
├── Itens.csv               # Dataset de entrada (peso, volume, valor por item)
├── Carga_Optimization.ipynb # Notebook com implementação e análise
└── README.md               # Documentação
```  
## **5 - Docs:** ## 

**Os algoritmos genéticos funcionam de forma a criar clones de uma hipótese para encontrar o melhor resulado.**

Imagine que você precisa descobrir a melhor maneira de minerar um mineral, extrair petróleo ou colher trigo, maximizando produção e reduzindo custos.
O algoritmo genético gera várias possibilidades (população inicial) e evolui através de iterações, testando combinações inteligentes sem avaliar todas as opções. Ele retorna a melhor solução em formato numérico (ex: 5 caminhões, 200 psi) ou booleano ('sim/não'), simulando eficiência sem testes físicos caros.

**Utilidade:**
Repete ciclos (gerações) para aprimorar soluções, descartando as piores e recombinando as melhores.
Ao definir variáveis da operação com máximo e mínimo vai delimitar limites (variável boundaries) para evitar as soluções absurdas. Ex: Pressão de extração de petróleo não pode ser negativa, Número de caminhões não pode ser 10.000 se a frota tem só 50.
Tamanho da população configura quantas soluções são geradas por vez (ex: 50).
Taxa de mutação configura a chance de alterações aleatórias (ex: 1% para evitar soluções repetitivas).
Número máximo de iterações configura como Critério de parada (ex: 100 gerações finaliza a otimização).

**O Gráfico:**
Mostra a linha decrescente indicando que o GA está encontrando soluções melhores a cada geração. Exemplo: Eixo X = gerações, Eixo Y = custo (quanto menor, melhor).

**Onde usar:**
Logística: Define rotas ideais sem simular todas.
Agricultura: Ajusta equipamentos e plantio em grandes áreas.
Petróleo: Otimiza extração sem riscos de testes reais.

Essência: Em todos os casos, o algoritmo genético substitui tentativa e erro por evolução dirigida, entregando a melhor solução prática sem gastos desnecessários.</h5>

<h6>

---

**Exemplo Agricultura:**
Você é um agricultor que quer testar novas técnicas para aumentar a produtividade do trigo. Hoje, seus campos usam:
Espaçamento: 25 cm entre sementes
Irrigação: 10h da manhã
Rotas de colheita: linha reta

Resultado atual: 5 toneladas/hectare, gastando 5000 litros de água e 20 litros de diesel por hectare.

Seu funcionário pega esses dados e simula 10.000 combinações diferentes no computador, variando:
Espaçamento: de 15 a 30 cm
Horário de irrigação: de 0h às 23h
Rotas: zigue-zague, circular e em grade

Após 2 horas de simulação, ele traz os resultados ideais para o próximo plantio:
Espaçamento: 18 cm
Irrigação: 3h da manhã
Rota: zigue-zague

Resultado projetado: 5,8 toneladas/hectare (+16%), com 4200 litros de água (-16%) e 17 litros de diesel (-15%) por hectare.

No futuro, esse mesmo sistema poderá:
Usar dados em tempo real do solo e clima para ajustar automaticamente a irrigação
Integrar preços de combustível e água para calcular o custo-benefício em tempo real
Testar novas sementes geneticamente modificadas em simulação antes do plantio real

A cada safra, o algoritmo aprende com os novos dados e sugere ajustes ainda mais precisos - tornando sua fazenda cada vez mais eficiente sem precisar de adivinhação ou tentativa e erro. 

---

**Exemplo Petróleo:**

Imagine que você é um engenheiro de petróleo responsável por um campo maduro no mar. Atualmente, seus poços operam com:
Pressão de injeção de água: 2.500 psi
Vazão por poço: 800 barris/dia
Configuração atual: 5 poços produtores e 2 injetores

Resultado atual: 4.000 barris/dia com custo de US$ 15/baril

Você precisa aumentar a produção para 4.500 barris/dia, mas cada teste físico no campo custa US$ 500 mil e leva 3 meses. Enquanto você planeja os próximos testes, um analista de dados sugere simular diferentes configurações usando um algoritmo genético.
Ele coleta os dados históricos do campo:
Performance de 20 poços nos últimos 5 anos
Dados de pressão, vazão e custos operacionais
Limites operacionais de segurança

O algoritmo testa 50.000 combinações em 6 horas, variando:
Pressão de injeção (2.000-3.000 psi)
Número de poços injetores (1-4)
Vazão por poço (500-1.200 barris/dia)

A solução ideal encontrada:
Aumentar pressão para 2.800 psi
Ativar 1 poço injetor adicional (total 3)
Ajustar vazão para 950 barris/dia nos poços principais
Resultado projetado: 4.600 barris/dia (+15%) com custo reduzido para US$ 13/baril

Implementação no campo confirma os resultados em 2 meses, com economia de US$ 2 milhões em testes desnecessários.

---

**Exemplo logística de transportes:**
Você é o gerente de uma frota com 50 caminhões. Hoje, seus motoristas gastam 6 horas planejando rotas manualmente, resultando em:
30% dos veículos rodando com carga pela metade
20% das entregas atrasadas
Custo diário: R$ 35.000

Seu analista de dados propõe uma solução:
Coletamos a Localização de 120 clientes, Horários de entrega, Capacidade de cada caminhão

O algoritmo genético testa 500.000 combinações em 3 horas e encontra:
Rotas que reduzem a quilometragem média de 380km para 290km por veículo
Taxa de ocupação dos caminhões aumenta de 70% para 92%
Atrasos caem para 5%

Resultado após 1 mês:
Economia de R$ 8.500/dia
2 horas diárias salvas no planejamento
Redução de 15% no consumo de diesel

---

## **Como Executar**  
1. Instale as dependências:  
   ```bash
   pip install geneticalgorithm pandas
   ```  
2. Execute o Jupyter Notebook:  
   ```bash
   jupyter notebook Carga_Optimization.ipynb
   ```  

## **Parâmetros Ajustáveis**  
| Parâmetro                | Descrição                                  | Valor Padrão  |
|--------------------------|-------------------------------------------|--------------|
| `max_num_iteration`      | Número máximo de gerações                 | 10           |
| `population_size`       | Tamanho da população                      | 100          |
| `mutation_probability`  | Probabilidade de mutação                  | 0.1          |
| `crossover_type`        | Tipo de crossover (`uniform`/`one_point`) | `uniform`    |

## **Aplicações em Empresas**  
- **Logística:** Maximização de carga útil em caminhões/contêineres.  
- **E-commerce:** Seleção de pedidos para entrega com restrições de veículo.  
- **Manufatura:** Otimização de matérias-primas em transporte.  

## **Limitações e Melhorias Futuras**  
- **Limitações:**  
  - Dependência da qualidade dos dados de entrada.  
  - Tempo de execução pode aumentar com datasets muito grandes.  
- **Melhorias Propostas:**  
  - Paralelização do algoritmo genético.  
  - Integração com APIs de roteirização (ex.: Google Maps).  

## **Referências**  
- Documentação da biblioteca [geneticalgorithm](https://pypi.org/project/geneticalgorithm/).  
- Artigos sobre otimização em logística (ex.: *Vehicle Routing Problem*).  


