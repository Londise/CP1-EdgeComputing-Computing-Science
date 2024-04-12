# Sistema de Monitoramento de Luminosidade para Vinhos
Este projeto consiste em um sistema que utiliza um sensor de luz (LDR) para monitorar os níveis de luminosidade em um ambiente, garantindo que os vinhos em uma vinícola estejam armazenados em condições ideais de iluminação. O sistema utiliza LEDs e um buzzer para indicar se a luminosidade está adequada, em alerta ou em condição crítica.

Componentes Utilizados
- Sensor de Luz (LDR)
- LEDs (verde, amarelo, vermelho)
- Buzzer
- Arduino UNO R3

Resistências utilizadas nos resistores.
LDR - Resistência de 10 KiloOhms
LEDs - Resistência de 200 Ohms 


Configuração do Hardware
O circuito é montado de acordo com as seguintes conexões:

Pino A0: Conectado ao sensor de luz (LDR)
Pino 11: Conectado ao LED verde
Pino 10: Conectado ao LED amarelo
Pino 9: Conectado ao LED vermelho
Pino 5: Conectado ao buzzer


Funcionamento do Software
O código embarcado no Arduino é responsável por ler os valores analógicos do sensor de luz, convertê-los em uma escala de 0 a 100 por cento e tomar ações com base nesses valores. O sistema opera da seguinte maneira:

-Configuração Inicial: Define os pinos como entradas (para o sensor) e saídas (para LEDs e o buzzer).

Loop Principal:

- Lê o valor analógico do sensor de luz.
- Converte esse valor em uma escala de 0 a 100 para representar a luminosidade.
- Compara o valor lido com os valores definidos para determinar a condição de luminosidade.
- Acende os LEDs correspondentes e emite um som pelo buzzer de acordo com a condição de luminosidade:
- Verde para condição OK (baixa luminosidade).
- Amarelo para condição de alerta (luminosidade moderada).
- Vermelho para condição crítica (alta luminosidade).
- Aguarda 500ms antes da próxima leitura.
- Mapeia os valores de luminosidade entre 49 e 969 e os registra em porcentagem.


Uso e Interpretação dos Resultados
- LED Verde: Indica que a luminosidade está adequada para a conservação dos vinhos.
- LED Amarelo: Indica uma condição de alerta, sugerindo verificar e ajustar a iluminação.
- LED Vermelho: Indica uma condição crítica, onde a luminosidade pode ser prejudicial para os vinhos.
- Buzzer: Emite um som curto e iterativo para alerta e um som contínuo para condição crítica.


Lógica por tras do código e conselhos:
Os valores limite de luminosidade devem ser calibrados de acordo com os componentes a serem utilizados e as necessidades específicas da vinícola visto que:
- A resistência do LDR afeta de maneira diretamente proporcional aos valores de leitura.
- o modelo de LDR também influi nos valores de leitura.

- Na configuração de hardware, Os valores de resistência do LDR são inversamente proporcionais aos valores de luminosidade do LDR, portanto, o LDR funciona da maneira tradicional.

- O delay ao final do Loop Principal serve para evitar oscilações que ocorram no intervalo dos valores limite de leds diferentes, assim evitando possíveis 
averias nos LEDs.

Leitura de Dados
- Tanto o valor de luminosidade como a intensidade de luz medida em % podem ser visualizadas no Serial Monitor.


REPRODUÇÃO DO PROJETO NO SIMULADOR 
O projeto pode ser executado no simulador feito na plataforma Tinkercad através do link:
https://www.tinkercad.com/things/jGqY1vAvV0G-copy-of-fotorresistor/editel?sharecode=N2K8ZdWc3xysvRHpDFuyUqw6gR07NM1Mtl-ZUBuellU

Ao clicar em "Iniciar simulação" na parte superior direita, o projeto irá iniciar com o LED Verde ligado inicialmente, ao clicar no LDR aparecerá uma barra de luminosidade onde o usuario poderá mudar os valores de luminosidade e observar o comportamento correspondente dos LEDs. 




