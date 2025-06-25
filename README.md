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

---  
**Licença:** MIT.  
**Contribuições:** Issues e PRs são bem-vindos.
