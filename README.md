# 📊 Telecom X - Parte 2: Previsão de Evasão de Clientes (Churn)

## 🧠 Propósito do Projeto

Este projeto tem como objetivo principal **prever a evasão (churn) de clientes da empresa de telecomunicações Telecom X** com base em variáveis demográficas, comportamentais e financeiras. A previsão do churn permite à empresa **identificar clientes em risco de cancelamento** e adotar estratégias de retenção mais eficazes.

---

## 🗂 Estrutura do Projeto

A estrutura de pastas e arquivos foi organizada para facilitar a navegação e o entendimento das etapas:

Telecom-X-Previsao-Churn/
│
├── 📁 data/
│ ├── TelecomX_Data.json # Base de dados original
│ ├── dados_tratados.csv # Dados limpos e tratados
│
├── 📁 visuals/
│ ├── correlacao_matriz.png # Matriz de correlação
│ ├── scatter_tenure_gasto.png # Dispersão: Gasto x Tempo de Contrato
│ └── boxplot_charges.png # Boxplot: Charges x Churn
│
├── 📄 ChallengeFinal_TelecomX_BR2_(2).ipynb # Notebook principal com análise completa
├── 📄 README.md # Este arquivo

---

## ⚙️ Processamento e Preparação dos Dados

### ✅ Classificação das Variáveis

- **Categóricas**: `gender`, `Partner`, `Dependents`, `PhoneService`, `InternetService`, `PaymentMethod`, `Contract`, entre outras.
- **Numéricas**: `tenure`, `Charges.Monthly`, `Charges.Total`, `Qtd_Servicos`, `Contas_Diarias`.

### 🛠 Etapas de Preparação

1. **Limpeza dos Dados**:
   - Remoção de registros inválidos ou incompletos.
   - Preenchimento de valores ausentes (`SimpleImputer`).

2. **Codificação de Variáveis Categóricas**:
   - Variáveis binárias foram mapeadas manualmente (`Yes` → 1, `No` → 0).
   - Variáveis com múltiplas categorias foram convertidas usando `OneHotEncoder`.

3. **Normalização dos Dados**:
   - Aplicada a modelos que dependem de escalas, como **KNN** e **Regressão Logística**, utilizando `StandardScaler`.

4. **Separação dos Dados**:
   - Os dados foram divididos em **conjuntos de treino e teste** com a função `train_test_split`, respeitando a proporção de 70% treino e 30% teste.
   - Aplicado **SMOTE** para balancear a classe de churn no conjunto de treino.

---

## 🤖 Modelagem Preditiva

### Modelos Utilizados

#### 1. **Regressão Logística** (com normalização)
- Fácil interpretação dos coeficientes.
- Bom para compreender como cada variável contribui para a evasão.

#### 2. **Random Forest** (sem normalização)
- Modelo robusto a dados não linearmente separáveis.
- Excelente para variáveis categóricas e análise de importância de atributos.

### 🎯 Justificativas

- **Regressão Logística** foi escolhida por ser um modelo **interpretable**, ótimo para explicar as contribuições individuais das variáveis.
- **Random Forest** foi utilizado por sua capacidade de **generalização e performance superior** em datasets com múltiplas categorias e interações.

---

## 📈 Métricas de Avaliação

- **Acurácia**
- **Precisão**
- **Recall**
- **F1-score**
- **Matriz de Confusão**

Essas métricas permitiram avaliar os modelos de forma abrangente, considerando tanto os **falsos positivos quanto falsos negativos** — especialmente importantes em casos de churn.

---

## 🔍 Insights Relevantes

- Clientes com **contratos mensais**, **menor tempo de fidelidade (tenure)** e **altos gastos mensais** têm maior probabilidade de cancelar o serviço.
- A **ausência de suporte técnico** também está correlacionada com maior evasão.
- Métodos de pagamento como **cheque eletrônico** estão mais associados a clientes que cancelam.

---

## 🛡 Estratégias de Retenção Propostas

- Incentivar **contratos de longo prazo** com benefícios.
- Criar **alertas preditivos** no CRM para clientes com alto risco de churn.
- Ampliar **ofertas de suporte técnico** e canais de atendimento.
- Reavaliar planos com alto custo mensal para torná-los mais atrativos.

---

## 📌 Conclusão

O projeto demonstrou que é possível prever com boa acurácia quais clientes estão propensos a cancelar seus serviços. A partir das variáveis mais relevantes, é possível estruturar campanhas e estratégias **focadas na retenção de clientes**, reduzindo o churn e melhorando a receita da empresa.

---

## 👨‍💻 Autor

Rosina Castro  
Projeto desenvolvido para análise preditiva em Ciência de Dados.  
