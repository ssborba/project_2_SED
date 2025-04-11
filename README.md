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
## Modelagem no CPN Tools

A modelagem desenvolvida no CPN Tools representa detalhadamente o funcionamento interno de uma célula de manufatura automatizada, composta por três máquinas e três robôs. O fluxo inicia no depósito de entrada da célula e avança por cada estágio de produção, controlado por uma lógica de transições e condições que garantem a ordem, limite de itens e ausência de bloqueios no sistema.

O Robô 1 é responsável por iniciar o processo, transportando itens do depósito de entrada da célula para o buffer da Máquina 1. Esse transporte só ocorre quando há itens disponíveis e espaço suficiente na máquina, o que é controlado por condições de disparo nas transições.

Em seguida, o Robô 2 realiza a distribuição dos itens processados pela Máquina 1 para as Máquinas 2 e 3. O modelo utiliza transições (ações) paralelas para representar as duas possíveis rotas e uma lógica de escolha baseada na disponibilidade dos buffers dessas máquinas, nos recursos disponíveis no out da Máquina 1. 

Após o processamento nas Máquinas 2 e 3, os itens são recolhidos pelo Robô 3, que os leva até o depósito de saída da célula. O modelo verifica se há espaço disponível no depósito final antes de permitir a movimentação, assegurando que o sistema não entre em estado de bloqueio por falta de armazenamento.

Todas as máquinas do sistema compartilham a mesma estrutura de modelagem: um lugar de entrada que representa o buffer, uma transição que simula o tempo de processamento e um lugar de saída onde o item é disponibilizado para o próximo estágio. Esse padrão modular foi replicado nas três máquinas da célula, simplificando o desenvolvimento e permitindo reutilização.

Por fim, todas essas partes estão integradas em uma estrutura única representando a célula de manufatura completa. O sistema geral simula o fluxo completo da produção, levando em consideração uma única célula. A modelagem foi validada para garantir a não ocorrência de deadlocks e respeitar a limitação de quatro itens por depósito, conforme as especificações do projeto.

### Manufatura

Manufatura, representando o maior nível de hierarquia do sistema, contendo sub-blocos de cada célula. 

![Manufatura](imagens/Manufatura.jpeg)

### Robô 1

Este módulo representa o transporte dos itens do **depósito de entrada da célula** para o **depósito de entrada da Máquina 1**. 

![Robô R1](imagens/R1.jpeg)

### Robô 2

Responsável por transferir os itens da **saída da Máquina 1** para os depósitos de entrada das **Máquinas 2 e 3**.  

![Robô R2](imagens/R2.jpeg)

### Robô 3

Encaminha os itens da **saída das Máquinas 2 e 3** para o **depósito de saída da célula**.  

![Robô R2](imagens/R3.jpeg)

---

### Máquinas

A modelagem das máquinas foi feita utilizando uma estrutura genérica reaproveitável. A mesma lógica foi aplicada às três máquinas, com ajustes apenas nas rotas de entrada e saída. 

![Modelo para Máquina 1, 2, 3](imagens/Máquinas.jpeg)

---
## Tecnologias Utilizadas

- [CPN Tools](https://cpntools.org/) – Edição, simulação e análise de Redes de Petri Coloridas  
- [Java (Oracle)](https://www.java.com/pt-BR/) – Necessário para execução do CPN Tools

---

## Estrutura do Repositório

```
📁 modelo/
   └── robos_manufatura.cpn      # Arquivo principal do modelo CPN
📁 imagens/
   └── Máquinas.jpeg            # Ilustrações
   └── R1.jpeg
   └── R2.jpeg
   └── R3.jpeg
   └── sistema.jpeg
📄 README.md                         # Documentação (este arquivo)


```

## Ilustração Geral


![Modelo do Sistema](imagens/sistema.jpeg)

---

## Demonstração em Vídeo

Assista à explicação e simulação do modelo no YouTube:  
[Clique aqui para ver o vídeo]()


---

## Como Executar o Modelo

1. Instale o [CPN Tools](https://cpntools.org/)
2. Instale o [Java (Oracle)](https://www.java.com/pt-BR/)
3. Baixe este repositório e abra o arquivo `.cpnet` na pasta `modelo/`
4. Use o CPN Tools para simular o funcionamento do sistema de manufatura
5. 
---

## Integrantes do Grupo

- Gabrielle Pereira  
- Sarah Borba
- Victor Gomes
