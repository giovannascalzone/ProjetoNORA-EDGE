# NORA – Nutrição Orbital Resistente Ativa

## Descrição do Projeto

A NORA é uma embalagem inteligente desenvolvida para preservar a qualidade nutricional dos alimentos durante missões espaciais de longa duração. A solução combina proteção passiva através de materiais especializados com um sistema eletrônico de monitoramento baseado em Arduino.

A estrutura da embalagem utiliza HDPE (polietileno de alta densidade), um material capaz de reduzir os efeitos da radiação cósmica e impedir a entrada de luz ultravioleta, fatores que contribuem para a degradação de nutrientes ao longo do tempo. Além disso, a vedação hermética auxilia na manutenção das condições internas adequadas para armazenamento.

O sistema embarcado monitora continuamente variáveis ambientais importantes para a conservação dos alimentos, permitindo identificar rapidamente qualquer alteração que possa comprometer sua qualidade.

## Objetivo da Solução

O objetivo da NORA é aumentar a vida útil e preservar os nutrientes dos alimentos transportados ou armazenados em missões espaciais, reduzindo perdas causadas por temperatura inadequada, excesso de umidade, exposição à luz, alterações na atmosfera interna, vazamentos ou radiação.

A solução busca fornecer monitoramento contínuo e automático, permitindo que a tripulação acompanhe em tempo real as condições internas da embalagem e receba alertas sempre que algum parâmetro sair dos limites considerados seguros.

## Componentes Utilizados

* Arduino Uno
* Sensor DHT22 (temperatura e umidade)
* Sensor BMP180/BMP085 (pressão atmosférica)
* Sensor MQ-2 (monitoramento de gases)
* Sensor de radiação (simulado)
* Sensor LDR (luminosidade)
* Display LCD I2C 16x2
* Buzzer
* LED Verde
* LED Amarelo
* LED Vermelho
* Protoboard
* Jumpers
* Resistores

## Explicação do Funcionamento

O Arduino realiza leituras contínuas dos sensores instalados na embalagem.

O sensor DHT22 monitora temperatura e umidade, verificando se permanecem dentro dos limites definidos para conservação dos alimentos. O sensor MQ-2 acompanha alterações na atmosfera interna da embalagem. O sensor BMP180 monitora a pressão interna para auxiliar na identificação de possíveis falhas de vedação. O sensor de radiação simula o monitoramento da exposição acumulada à radiação espacial e o sensor LDR detecta qualquer incidência de luz dentro da embalagem.

Cada variável é comparada com limites pré-definidos. Quando os valores permanecem dentro da faixa ideal, o sistema considera a condição segura. Caso algum parâmetro ultrapasse os limites estabelecidos, ele passa para estado de ALERTA ou CRÍTICO.

O display LCD exibe o valor do sensor alterado e seu respectivo status. Se mais de um parâmetro estiver fora da faixa ideal, as informações são exibidas alternadamente a cada 5 segundos.

Os LEDs fornecem uma indicação rápida do estado geral do sistema:

* LED Verde: todos os parâmetros em condição ideal.
* LED Amarelo: existência de um ou mais alertas.
* LED Vermelho: existência de condição crítica.

Quando o sensor de luminosidade detecta excesso de luz, o buzzer é acionado para alertar imediatamente sobre possível comprometimento da proteção interna da embalagem.

Além disso, todas as informações são enviadas ao Monitor Serial da IDE Arduino para acompanhamento detalhado em tempo real.

## Estrutura do Circuito

### DHT22

* VCC → 5V
* GND → GND
* DATA → Pino Digital 2

### MQ-2

* VCC → 5V
* GND → GND
* AO → A0

### Sensor de Radiação

* Saída → A1

### LDR

* Saída → A2

### Display LCD I2C

* VCC → 5V
* GND → GND
* SDA → A4
* SCL → A5

### BMP180/BMP085

* VCC → 5V
* GND → GND
* SDA → A4
* SCL → A5

### Buzzer

* Positivo → Pino 9
* Negativo → GND

### LEDs

* Verde → Pino 10
* Amarelo → Pino 11
* Vermelho → Pino 12

## Instruções de Execução

Ao ser energizada, a NORA inicializa todos os sensores e dispositivos de monitoramento. Em seguida, o sistema começa a coletar dados de temperatura, umidade, pressão, gases, radiação e luminosidade.

Os valores lidos são comparados aos limites ideais definidos no programa. Sempre que um parâmetro estiver fora da faixa adequada, o display LCD exibe seu valor atual e o respectivo estado (ALERTA ou CRÍTICO). Caso existam múltiplas alterações simultaneamente, cada uma é mostrada individualmente em intervalos de 5 segundos.

Quando todos os sensores apresentam valores adequados, o display informa "STATUS: IDEAL" e o LED verde permanece aceso.

O buzzer é ativado quando há incidência excessiva de luz dentro da embalagem, enquanto os LEDs indicam visualmente a situação geral do sistema. Todas as leituras também são registradas no Monitor Serial, permitindo acompanhamento em tempo real do funcionamento da NORA.


## INTEGRANTES:
Turma ESPJ:
* Amanda  Oliveira Lourenço - RM: 572572
* Giovanna Lopes Scalzone - RM: 572285
* Nayra Sousa Duarte - RM: 573815
* Paloma do Carmo Dantas - RM: 569995
