# LOC11xAmplifier
An optically insulated amplifier with 4x gain / Um amplificador isolado opticamente com ganho de 4x

O amplificador é baseado no optoacoplador linear [LOC110S/P](circuit/kicadlib/datasheet/LOC110.pdf) e foi projetado a fim de testar a técnica de se utilizar um par óptico casado de fotodiodos para fazer um circuito isolado e realimentado simultâneamente.

![Visualização 3D da face superior da placa](/preview/LOC11xAmplifier_top_perspective.png)

O projeto foi feito agora precisa ser testado :)

## Especificações

### Condições de Operação Recomendadas¹

| Parâmetro | Condições | Símbolo | Mín. |Típico | Máx. | Unidade |
| :------- | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| **Alimentação** |
| Tensão de Alimentação do Estágio de Entrada | - | Vs_1 | 3.15 | - | 3.75 | V |
| Tensão de Alimentação do Estágio de Saída | - | Vs_2 | 3.02 | - | 4.36 | V |
| Corrente Quiescente do Estágio de Entrada | Vs_1 = 3.3 V, V_in = 0 | I_q1 | - | 6.98 | - | mA |
| Corrente Quiescente do Estágio de Saída | Vs_2 = 3.3 V, V_in = 0 | I_q2 | - | 3.3 | - | mA |
| **Amplificador** |
| Tensão de Entrada | - | V_in | -250 | - | 250 | mV |
| Impedância de Entrada |  - | Z_in | - | 60.44 | - | Ω |
| Tensão de _Offset_ de Saída | - | V_off | - | 1.535 | - | V |
| Corrente Máxima de Saída | Vs_2 = 3.15 V |  | - | - | 1.5 |  |
|                          | Vs_2 = 3.3 V | I_o | - | - | 3.1 | mA |
|                          | Vs_2 = 3.5 V | | - | - | 5.3 |  |
| Ganho de Tensão |  - | A_v | - | 3.98 | - |  |
| Resposta de frequência² | - | f_-3db | - | 200 | - | kHz
###### ¹ valores calculados para 25°C
###### ² valor com referência no modo de operação fotocondutiva dos fotodiodos

## O circuito

Os componentes e topologias do circuito foram escolhidos a fim de obter baixo custo, mas com especificações razoáveis. Suas conexões estão disponíveis para barras de pinos de 2.54 mm de espaçamento e pads nas bordas para uma soldagem SMT

O circuito opera nominalmente com tensões de alimentação de 3.3 V, faixas de entrada de ±250 mV e tensão de saída centralizada em 1.535 V e ganho de 3.98 do sinal de entrada.

Em função da configuração fotocondutiva dos [pares ópticos](circuit/kicadlib/datasheet/LOC110.pdf), o circuito opera até 200 kHz. 

#### Operação

O estágio de entrada foi projetado para operar na faixa de 2.5 até 3.5 mA do diodo emissor. Essa região foi escolhida por resultar em uma baixa variação de ganho do sinal em 25 °C. 

Seus [amplificadores](circuit/kicadlib/datasheet/tlv9001.pdf) são _rail-to-rail_ para entradas e saída com baixo _offset_ de entrada e baixo consumo (1 μA)

As [referências de tensão](circuit/kicadlib/datasheet/lm4040-n.pdf) são de 2 % do tipo _shunt_ 
