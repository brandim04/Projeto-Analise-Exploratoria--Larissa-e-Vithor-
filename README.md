# Projeto Olist Brazilian E-Commerce

## 👥 Nome dos Integrantes
- Larissa e Vithor

## 🔗 Link da base de dados utilizada
- [Olist Brazilian E-Commerce Dataset no Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

## 🎯 Objetivo do projeto
Investigar os fatores que afetam a experiência e satisfação do cliente no e-commerce brasileiro. O foco é entender padrões relacionados a atrasos de entrega, satisfação do cliente, diferenças de preço e frete, categorias de produtos problemáticas e variações no tempo de processamento e envio. O projeto enfatiza pré-processamento e análise exploratória, sem a criação de modelos de IA ou classificação.

## 🛠️ Descrição do processo de tratamento dos dados
O tratamento dos dados envolveu diversas etapas:

1. **Limpeza**: remoção de duplicatas, padronização de strings, tratamento de valores ausentes e identificação de outliers.  
2. **Conversão e padronização de tipos**: datas convertidas para datetime, valores numéricos padronizados e strings uniformizadas.  
3. **Codificação de dados categóricos**: one-hot encoding para status de pedidos e frequency encoding para categorias de produtos.  
4. **Normalização e padronização**: MinMaxScaler para preço e frete, Z-score para tempo de entrega e número de itens.  
5. **Seleção de atributos**: remoção de colunas de baixa variância, altamente correlacionadas ou com muitos valores ausentes.  
6. **Feature engineering**: criação de novas métricas como tempo de entrega, atraso na entrega, itens por pedido, valor total do pedido, frete total e razão frete/preço.  
7. **Pipeline de pré-processamento**: todas as etapas anteriores foram consolidadas em um pipeline para aplicação automatizada em novos dados.

## ⚠️ Principais desafios encontrados
- Identificação de duplicatas e inconsistências nos nomes de produtos e categorias.  
- Presença de outliers significativos em preço e frete que refletem situações reais, exigindo cuidado na análise.  
- Padronização e codificação de múltiplos atributos categóricos para permitir análise estatística consistente.  
- Integração dos três datasets principais em um único DataFrame consolidado para análise completa.

## 📈 Principais conclusões
- Pedidos com maior número de itens e fretes proporcionais ao preço tendem a atrasar mais.  
- Categorias como eletrônicos e móveis apresentam maiores atrasos e fretes elevados, indicando desafios logísticos.  
- Outliers em preço e frete refletem a realidade do mercado e não devem ser descartados automaticamente.  
- O pré-processamento estruturado e o pipeline automatizado permitem análises consistentes, identificação de padrões relevantes e suporte à tomada de decisão estratégica no e-commerce.

## 📄 Link do relatório final
- [Relatório completo do projeto](https://docs.google.com/document/d/1TRiI1tIYXRMPENyx6auCkeSbUpWdA6fbgWxIK61w_xs/edit?usp=sharing)
