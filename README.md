## 📄 Arquivo README.md

Aqui está o arquivo **README.md** completo, formatado em Markdown, consolidando o projeto de pré-processamento de dados.

---

### 👥 Nome dos Integrantes

* [Larissa Brandim]
* [Vithor Gabriel]

---

### 🔗 Link da Base de Dados Utilizada

A base de dados utilizada é o **Olist E-Commerce Public Dataset**, uma coleção de dados reais de pedidos feitos na Olist Store, no Brasil.

* **Link:** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

---

### 🎯 Objetivo do Projeto

O objetivo principal deste projeto foi **limpar, integrar e pré-processar** múltiplos *datasets* de e-commerce para criar um único arquivo de dados transacionais, pronto para ser utilizado em tarefas de **análise avançada** e **modelagem preditiva** (ex: previsão de entrega, análise de satisfação e *clustering*).

---

### 🛠️ Descrição do Processo de Tratamento dos Dados

O processo de tratamento seguiu um rigoroso **Pipeline de Pré-processamento** (Item 12), garantindo integridade dos dados para análises e modelos.

---

#### 1. Limpeza e Padronização Inicial (Itens 5, 6, 7)

- **Conversão de Tipos:** Todas as colunas de data/hora (`object`) foram convertidas para `datetime64[ns]`.
- **Padronização de Texto:** Colunas categóricas (ex: `order_status`) foram padronizadas com `.str.title()`.
- **Tratamento de Duplicatas e NaNs:**  
  - Remoção de linhas duplicadas  
  - Imputação da **mediana** para valores ausentes em colunas numéricas (ex: dimensões de produtos)

---

#### 2. Tratamento de Outliers (Item 5.4)

- **Identificação por Z-score:** Outliers foram identificados nas variáveis `price` e `product_weight_g`.
- **Decisão:** Mantivemos os outliers, pois representam transações reais e são importantes para análises de receita e logística.

---

#### 3. Engenharia de Features (Item 11)

Foram criados atributos essenciais para a análise de e-commerce:

- `total_value` — Preço total do item (Preço + Frete)
- `freight_ratio` — Razão Frete/Preço
- `shipping_month` e `shipping_year` — Extração temporal
- `price_category` — Faixas de preço: 'Muito Barato', 'Barato', 'Normal', 'Caro', 'Muito Caro'

---

#### 4. Codificação e Scaling (Itens 8, 9)

- **Codificação Categórica:** One-Hot Encoding via `pd.get_dummies()`
- **Normalização:**  
  - MinMaxScaler aplicado a `price`

---

#### 5. Seleção de Atributos (Item 10)

- **Baixa Variância:** Remoção de colunas quase constantes
- **Remoção de IDs:** `order_id`, `customer_id` etc., por não terem valor preditivo
- **Correlação:** Avaliada especialmente entre `price` e `freight_value`

---

### 🚧 Principais Desafios Encontrados

1. **Integração de Múltiplos Arquivos:** Unificação correta dos 8 *datasets* exigiu atenção às chaves.
2. **Datas e NaNs:** Pedidos incompletos/cancelados geraram valores `NaT` complexos de tratar.
3. **Alta Cardinalidade:** *Features* como `product_id` foram removidas devido ao alto custo computacional.

---

### 📊 Principais Conclusões

- A relação **Preço vs. Frete** mostrou impacto direto nos custos logísticos.
- A categorização de preço ajudou a suavizar distribuições assimétricas.
- O pré-processamento resultou em um *dataset* altamente confiável, viável para análises como:
  - previsão de entregas  
  - estudo de satisfação  
  - KPIs de negócio  

---

### 📁 Arquivo CSV Final

O arquivo gerado ao final do processo foi:

**`olist_ecommerce_cleaned_processed.csv`**

Esse arquivo contém todos os dados integrados, limpos, transformados e prontos para análises avançadas ou Machine Learning.

---
