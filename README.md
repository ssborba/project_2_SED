# Projeto 2 - Sistema de Manufatura com Redes de Petri Coloridas

Este projeto consiste na modelagem de um sistema de manufatura com quatro células utilizando **Redes de Petri Coloridas (CPN)**, desenvolvido como parte da disciplina **Sistemas Embarcados Discretos (SED)** no período 2024.2 da **UFCG**.

---

## Descrição do Sistema

Cada célula de manufatura é composta por:

-  Um depósito de entrada  
-  Um depósito de saída  
-  Três máquinas (M1, M2, M3), cada uma com:
  - Um depósito de entrada
  - Um depósito de saída  
-  Três robôs responsáveis pelo transporte de itens

### Fluxo de Produção

- **Robô 1**: transporte do depósito de entrada da célula para o depósito de entrada da Máquina 1  
- **Robô 2**: transporte da saída da Máquina 1 para as entradas das Máquinas 2 ou 3  
- **Robô 3**: transporte das saídas das Máquinas 2 ou 3 para o depósito de saída da célula  

> Cada depósito pode conter no máximo **4 itens**, e o sistema deve funcionar **sem bloqueios (deadlocks)**.

---

## Objetivo

Modelar um sistema com 4 células de manufatura interligadas, garantindo funcionamento contínuo, sincronizado e sem bloqueios, utilizando **CPN Tools** para simulação e análise.

---

## Tecnologias Utilizadas

- [CPN Tools](https://cpntools.org/) – Edição, simulação e análise de Redes de Petri Coloridas  
- [Java (Oracle)](https://www.java.com/pt-BR/) – Necessário para execução do CPN Tools

---

## Estrutura do Repositório

