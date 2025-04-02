# Semáforo Inteligente com 8051

Este projeto implementa um sistema de semáforo inteligente utilizando o microcontrolador 8051, desenvolvido como solução para o Problema #1 da disciplina de Sistemas Embarcados (2025.1) da UEFS.

## 📋 Descrição

O sistema simula um semáforo inteligente com funcionalidades avançadas como detecção de veículos e modo de emergência. O projeto foi implementado inteiramente em Assembly para o microcontrolador 8051, utilizando o simulador MCU 8051 IDE.

## ✨ Funcionalidades

### 🚦 Ciclo Normal do Semáforo
- **LED Verde:** 10 segundos
- **LED Amarelo:** 3 segundos
- **LED Vermelho:** 7 segundos

### 🔢 Display de Contagem Regressiva
- Display de 7 segmentos multiplexado que exibe o tempo restante para cada cor
- Utiliza o timer interno do 8051 para precisão na contagem

### 🚨 Modo Emergência
- Ativado através de botão externo (interrupção INT0)
- Quando acionado, mantém o sinal vermelho por 15 segundos antes de retornar ao ciclo normal

### 🚗 Contagem de Veículos
- Incrementa contador através de botão externo (interrupção INT1)
- Exibe contagem atual na matriz de LEDs
- Quando há mais de 5 veículos, aumenta o tempo do sinal verde para 15 segundos

### ⚙️ Prioridades do Sistema
1. Interrupção Externa (Modo Emergência)
2. Interrupção Externa (Contagem de Veículos)
3. Timers (Controle de tempo do semáforo)

## 🛠️ Implementação

### Hardware Utilizado
- Microcontrolador 8051
- Display de 7 segmentos multiplexado (porta P1 + pinos P0.0, P0.1)
- Matriz de LEDs (porta P2)
- LEDs para o semáforo (P0.4, P0.5, P0.6)
- Botões externos para interrupções (INT0, INT1)

### Estrutura do Código
- **Rotinas de interrupção:** Tratamento das entradas externas e do timer
- **Controle de estado:** Gerencia as transições entre os estados do semáforo
- **Exibição:** Controle multiplexado dos displays e LEDs
- **Tabelas de dados:** Armazena padrões para o display de 7 segmentos

## 🎬 Vídeo Demonstrativo

https://github.com/user-attachments/assets/3f1db334-9193-4a1a-80b5-8796b8075c14

