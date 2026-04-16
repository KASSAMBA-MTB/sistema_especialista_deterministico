# 💳 Sistema Especialista para Análise de Crédito (Python)

## 📌 Descrição

Este projeto implementa um **Sistema Especialista determinístico** para análise de crédito, baseado em regras do tipo **SE-ENTÃO (IF-THEN)**.

O sistema foi desenvolvido em **Python puro**, sem uso de frameworks, com execução via terminal, simulando um mecanismo de inferência baseado em regras.

---

## 🧠 Conceitos Aplicados

* Sistemas especialistas
* Base de conhecimento (Knowledge Base - KB)
* Regras de produção (IF-THEN)
* Encadeamento para frente (*forward chaining*)
* Inferência determinística

---

## ⚙️ Base de Conhecimento (Regras)

As regras do sistema estão organizadas em três níveis:

### 🔹 1. Classificação de Variáveis

* Se valRenda ≥ 10000 → Renda = Alta

* Senão → Renda = Baixa

* Se valDespesa ≥ 6000 → Despesa = Alta

* Senão → Despesa = Baixa

* Se Qtde_Prest ≥ 12 → nPrest = Alto

* Senão → nPrest = Baixo

* Se Prestação ≥ 1000 → valPrest = Alto

* Senão → valPrest = Baixo

---

### 🔹 2. Regras de Cadastro

* Se Renda = Alta e Despesa = Alta → Cadastro = Regular
* Se Renda = Alta e Despesa = Baixa → Cadastro = Bom
* Se Renda = Baixa e Despesa = Alta → Cadastro = Ruim
* Se Renda = Baixa e Despesa = Baixa → Cadastro = Regular

---

### 🔹 3. Regras de Operação

* Se nPrest = Baixo e valPrest = Baixo → Operação = Boa
* Se nPrest = Alto e valPrest = Baixo → Operação = Boa
* Se nPrest = Baixo e valPrest = Alto → Operação = Boa
* Se nPrest = Alto e valPrest = Alto → Operação = Ruim

---

### 🔹 4. Regras de Crédito

* Se Cadastro = Ruim → Crédito = Não
* Se Operação = Ruim → Crédito = Não
* Se Cadastro = Bom e Operação = Boa → Crédito = Sim
* Se Cadastro = Regular e Operação = Boa → Crédito = Analista

---

## 🖥️ Funcionamento

O programa recebe como entrada:

* Valor da renda (`valRenda`)
* Valor da despesa (`valDespesa`)
* Quantidade de prestações (`Qtde_Prest`)
* Valor da prestação (`Prestacao`)

A partir desses dados, o sistema aplica as regras da base de conhecimento e retorna:

* Classificação da renda e despesa
* Tipo de cadastro
* Tipo de operação
* Decisão final de crédito

---

## 📁 Estrutura do Projeto

```id="w3k91s"
sistema_credito/
│
└── sistema_credito.py
```

---

## ▶️ Como Executar

### 1. Requisitos

* Python 3.x instalado

### 2. Executar o programa

```id="c8r1fa"
python sistema_credito.py
```

---

## 🧪 Casos de Teste

### ✔️ Caso 1

Entrada:

* valRenda = 3000
* valDespesa = 6000
* Qtde_Prest = 6
* Prestacao = 500

Resultado esperado:

* Renda = Baixa
* Despesa = Alta
* Cadastro = Ruim
* Operação = Boa
* Crédito = ❌ Não

---

### ✔️ Caso 2

Entrada:

* valRenda = 11000
* valDespesa = 4000
* Qtde_Prest = 6
* Prestacao = 800

Resultado esperado:

* Renda = Alta
* Despesa = Baixa
* Cadastro = Bom
* Operação = Boa
* Crédito = ✅ Sim

---

## 🎯 Objetivo Acadêmico

Este projeto tem como objetivo demonstrar a aplicação prática de:

* Sistemas especialistas baseados em regras
* Modelagem de conhecimento
* Implementação de lógica de inferência em Python

---

## 🚀 Possíveis Melhorias

* Interface gráfica (Tkinter ou Web)
* Entrada dinâmica de dados via usuário
* Separação da base de regras em módulo próprio
* Criação de motor de inferência genérico
* Integração com banco de dados

---

## 👨‍💻 Autor

**Walter Junio Pontes Teixeira**
Curso: Ciência de Dados

---
