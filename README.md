# gercom_tree-optimization

Implementação autoral de **Árvores de Decisão (CART) a partir dos primeiros princípios matemáticos** em Python/NumPy, incorporando um módulo especializado de **poda por complexidade de custo com minimização de resíduos quadráticos (`TreePruner`)**.

Desenvolvido no âmbito do **Laboratório GERCOM / UFPA** como bancada de experimentação e controle de nós internos para pesquisas em Aprendizado Federado de Ensembles de Árvores.

---

## 🔬 Arquitetura e Componentes

1. **`Node`:**
   - Estrutura de dados que modela nós de decisão e nós-folha, armazenando índice de atributo (`feature`), limiar de corte (`threshold`), ponteiros para filhos (`left`, `right`), amostras residentes (`nodeValues`), profundidade (`depth`) e identificador.
2. **`DecisionTree`:**
   - Algoritmo recursivo comutável para:
     - **Classificação:** Critério de Ganho de Informação baseado em Entropia de Shannon e moda estatística nas folhas.
     - **Regressão:** Critério de Redução de Variância e média aritmética nas folhas.
3. **`TreePruner` (Módulo de Poda):**
   - Executa a poda cirúrgica de nós terminais (`slice_nodes`), colapsando ramificações profundas em nós-folha e calculando a Soma dos Quadrados dos Resíduos (SSR - *Sum of Squared Residuals*):
     $$\text{SSR} = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
   - Permite monitorar a acurácia e a perda de resíduo em função da quantidade de cortes realizados.

---

## 📦 Como Executar

```bash
# 1. Clonar repositório
git clone https://github.com/Julio-C-Oliveira/gercom_tree-optimization.git
cd gercom_tree-optimization

# 2. Configurar ambiente
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. Executar o notebook
jupyter notebook Tree_Optimization.ipynb
```

---

## 📄 Licença
Distribuído sob a licença MIT. Veja `LICENSE` para mais detalhes.
