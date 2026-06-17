# 🧠 Sistema Fuzzy para Medição de Disposição Humana

Este repositório contém o desenvolvimento de um **Sistema Baseado em Lógica Fuzzy** projetado para converter variáveis subjetivas do cotidiano (como qualidade do sono e nível de estresse) em uma métrica quantitativa (0 a 100%) que estima o **nível de disposição humana** ao longo do dia.

Ao contrário de modelos matemáticos rígidos, onde uma pequena variação de minutos no sono mudaria drasticamente o resultado, a lógica fuzzy permite modelar transições graduais e imprecisões de forma muito mais natural e humana.

O projeto documenta a evolução de um modelo inicial simples (**V1**) até uma arquitetura refinada e mais aderente à realidade (**V2**).

---

## 🚀 Estrutura do Projeto

* `Projeto_Fuzzy_Disposição_.ipynb`: Notebook Jupyter contendo todo o código em Python, desde a modelagem matemática das funções de pertencência até o motor de inferência e testes.
* `Relatório Final.pdf`: Relatório técnico detalhado com a fundamentação teórica, justificativa dos universos de discurso e análise dos cenários de teste.
* `Tabela de Resultado.pdf`: Tabela contendo a validação do modelo através de 40 cenários de testes simulando diferentes rotinas e perfis comportamentais.

---

## 🛠️ Tecnologias Utilizadas

O projeto foi totalmente desenvolvido em **Python 3**, utilizando o ecossistema de bibliotecas científicas:

* **scikit-fuzzy:** Biblioteca principal para a computação baseada em lógica fuzzy.
* **NumPy:** Manipulação de matrizes e definição dos universos de discurso.
* **Matplotlib:** Geração dos gráficos das funções de pertencência e superfícies de decisão.
* **Pandas:** Estruturação e análise dos cenários de teste.

---

## 📐 Modelagem do Sistema (Versão Final - V2)

O sistema final foi construído utilizando **5 Variáveis de Entrada (Antecedentes)** e **1 Variável de Saída (Consequente)**:

### Antecedentes (Entradas)
1. **Horas de Sono (0 a 12h):** Mede o tempo de repouso. Rótulos: *curto*, *adequado* e *prolongado*.
2. **Qualidade do Sono (0 a 10):** Percepção subjetiva sobre o descanso. Rótulos: *ruim*, *regular* e *boa*.
3. **Intensidade de Esforço (0 a 100%):** Nível de desgaste físico do dia. Rótulos: *leve*, *moderada* e *intensa*.
4. **Qualidade da Alimentação (0 a 10):** Suporte nutricional do dia. Rótulos: *ruim*, *regular* e *boa*.
5. **Nível de Estresse (0 a 10):** Fator emocional/psicológico atuando como limitador. Rótulos: *baixo*, *médio* e *alto*.

### Consequente (Saída)
* **Nível de Disposição (0 a 100%):** Estimativa final de energia. Rótulos: *baixa*, *média* e *alta* utilizando o método de defuzzificação por **Centroide**.

---

## 🧠 Base de Regras & Evolução (V1 vs V2)

O cérebro do sistema é composto por **20 regras especialistas** do tipo `SE... ENTÃO` formuladas com base em comportamento biológico.

* **Evolução do Projeto:**
  * **V1:** Focava apenas em *Sono*, *Qualidade do Sono* e *Esforço*, gerando respostas lineares e menos sensíveis.
  * **V2:** Adicionou *Alimentação* e *Estresse*. O estresse foi modelado com um peso crítico: regras de **penalização por estresse** garantem que, se o estresse for *alto*, a disposição será contida mesmo que o usuário tenha dormido e se alimentado bem.

---

## 📊 Resultados e Validação

O sistema foi validado submetendo as regras a **40 cenários distintos** (como "Rotina Excelente", "Estresse Alto", "Rotina Contraditória", entre outros). 

Os gráficos completos de inferência e as superfícies de decisão tridimensionais (3D) gerados no projeto detalham visualmente como as variáveis interagem entre si para formar o mapa de disposição final.

---

## 💻 Como Executar o Projeto

### 1. Instale as dependências necessárias:
Para rodar o projeto localmente, certifique-se de instalar as seguintes bibliotecas no seu ambiente Python:
* pip install numpy
* pip install matplotlib
* pip install scikit-fuzzy
* pip install pandas

### 2. Abra o Notebook:
Você pode rodar o arquivo `Projeto_Fuzzy_Disposição_.ipynb` localmente via Jupyter Notebook ou fazer o upload do arquivo diretamente para o **Google Colab** para execução em nuvem.

---

## 👥 Autores - Grupo 07 (UCB)

Projeto desenvolvido para a disciplina de **Inteligência Artificial II** do curso de *Análise e Desenvolvimento de Sistemas* da **Universidade Católica de Brasília (UCB)**, sob a orientação do Prof. William Roberto Malvezzi.

* Bianca Melliny de Lima Vaz
* Guilherme Fernandes Rezende
* Isabela Martins Bandeira
* João Filipe Alves de Albuquerque Silva
* Natália Ematné Kruchak
