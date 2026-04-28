# 🍷 Projeto 3 — Classificação de Qualidade de Vinhos com k-NN

**Disciplina:** PAM0466 – Sistemas Inteligentes  
**Semestre:** 2026.1  
**Docente:** Pedro Thiago Valério de Souza  
**Instituição:** Universidade Federal Rural do Semi-Árido (UFERSA) — Centro Multidisciplinar Pau dos Ferros

---

## 📋 Descrição

Este projeto implementa um modelo de classificação de qualidade de vinhos tintos em três categorias — **baixa**, **média** e **alta** — utilizando o algoritmo **k-NN (k-Nearest Neighbors)**, a partir de atributos físico-químicos do dataset Wine Quality.

---

## 📁 Estrutura do Repositório

```
├── knn_vinho.ipynb       # Notebook principal com código e respostas
├── winequality-red.csv   # Dataset (baixar conforme instruções abaixo)
└── README.md             # Este arquivo
```

---

## 📦 Dataset

O projeto utiliza o arquivo `winequality-red.csv` do [Wine Quality Dataset (UCI)](https://archive.ics.uci.edu/ml/datasets/Wine+Quality), criado por Paulo Cortez et al. (Universidade do Minho, Portugal, 2009).

- **1.599 amostras** de vinho tinto da região do Vinho Verde (Portugal)
- **11 atributos** físico-químicos (acidez fixa, acidez volátil, ácido cítrico, açúcar residual, cloretos, dióxido de enxofre livre, dióxido de enxofre total, densidade, pH, sulfatos, teor alcoólico)
- **Rótulo:** `quality` — nota inteira de 0 a 10 atribuída por sommeliers

### Como baixar o dataset

Execute a célula de download no início do notebook, ou baixe manualmente:

```
https://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/winequality-red.csv
```

Coloque o arquivo na mesma pasta do notebook.

---

## ⚙️ Instalação das Dependências

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## 🚀 Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

2. Instale as dependências:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Abra o notebook:
```bash
jupyter notebook knn_vinho.ipynb
```

4. Execute todas as células em ordem (**Executar Tudo**).

---

## 📌 Atividades Desenvolvidas

### Atividade 1 — Preparação dos Dados
- Recodificação da variável `quality` em 3 classes: **baixa** (≤5), **média** (6–7), **alta** (≥8)
- Normalização Min-Max de todos os atributos
- **Resposta:** Justificativa da normalização para o k-NN

### Atividade 2 — Divisão Treino/Teste
- Divisão estratificada 80% treino / 20% teste
- Garantia de proporção das classes em ambos os conjuntos

### Atividade 3 — Treinamento e Escolha do k
- Validação cruzada 5-fold para k ∈ {1, 3, 5, 7, 11}
- Gráfico de acurácia média em função de k
- **Resposta:** Efeito de k muito baixo (overfitting) e muito alto (underfitting)

### Atividade 4 — Avaliação do Modelo
- Matriz de confusão no conjunto de teste
- Métricas: acurácia, precisão, recall e F1-score por classe
- **Resposta:** Classes com maior frequência de erros

---

## 📊 Resultados Principais

| Métrica | Valor |
|---------|-------|
| Melhor k | 7 |
| Acurácia no teste | ~78% |
| Classes com mais erros | Baixa ↔ Média |

---

## 🔍 Conclusões

O k-NN apresentou desempenho moderado (~78% de acurácia). As principais limitações são o forte desbalanceamento da classe **alta** (apenas ~18 amostras) e a fronteira ambígua entre as classes **baixa** e **média**. Melhorias futuras incluem uso de SMOTE, Random Forest ou SVM.
