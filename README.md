
# Projeto Semaforo Intel 8051

![2026-01-14-11-32-33](https://github.com/user-attachments/assets/85bb89d1-6220-4b0a-b0a7-1ec6310e9505)


Sistema de controle de tráfego desenvolvido em linguagem Assembly para o microcontrolador Intel 8051, projetado para simulação no software EdSim51DI.

## Descricao do Projeto

O sistema gerencia um semáforo convencional com temporização cíclica e permite a intervenção manual para interrupção ou retomada do fluxo. A leitura dos comandos manuais é realizada via técnica de varredura (polling), garantindo sensibilidade aos comandos mesmo durante os intervalos de espera das luzes.

## Mapeamento de Hardware

| Componente | Pino | Funcao |
| --- | --- | --- |
| LED Verde | P1.0 | Sinal de prosseguir |
| LED Amarelo | P1.1 | Sinal de atenção |
| LED Vermelho | P1.2 | Sinal de parada |
| LED Status Stop | P1.3 | Indicador de ciclo interrompido |
| LED Status Run | P1.4 | Indicador de ciclo ativo |
| Botao Parar | P2.0 | Comando para interromper o ciclo |
| Botao Iniciar | P2.1 | Comando para retomar o ciclo |

## Funcionamento

1. **Modo Automatico**: O sistema alterna continuamente entre Verde, Amarelo e Vermelho através de sub-rotinas de atraso.
2. **Interrupcao Manual**: Ao acionar o pino P2.0 (nível lógico 0), o sistema finaliza o estado atual e entra em modo de espera, acendendo o LED de status P1.3.
3. **Retomada**: O ciclo normal é reiniciado somente após o acionamento do pino P2.1 (nível lógico 0), sinalizado pelo LED P1.4.

## Requisitos para Simulacao

* Simulador EdSim51DI.
* Frequência de clock sugerida: 12 MHz.
* Configuração de pinos de entrada em modo pull-up (padrão do simulador).
