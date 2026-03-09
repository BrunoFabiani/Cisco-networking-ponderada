# Cisco-networking-ponderada

VIDEO: https://drive.google.com/file/d/19WR2b2aIorA38z8s5rhR6SrdC1WzJWGs/view?usp=sharing

Relatório Técnico — Análise de Propagação de Sinal em Redes Ethernet
Introdução

Este experimento teve como objetivo analisar o comportamento da transmissão de dados em redes locais utilizando dois dispositivos diferentes: hub e switch. A análise foi realizada no Cisco Packet Tracer utilizando três computadores conectados por cabos de par trançado. No primeiro cenário foi utilizada uma rede com hub, permitindo observar o comportamento do meio compartilhado na camada física. No segundo cenário, o hub foi substituído por um switch 2960, possibilitando a comparação do fluxo de transmissão dos sinais e da propagação das PDUs na rede.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Rede com HUB e análise de propagação do sinal

Na primeira etapa do experimento foi criado um cenário de rede no Cisco Packet Tracer com o objetivo de analisar a propagação de sinais em um ambiente baseado em hub. A topologia foi composta por três computadores (PC0, PC1 e PC2) conectados a um hub, utilizando cabos de par trançado (Ethernet copper straight-through) como meio físico de comunicação.

Cada computador foi conectado a uma porta do hub, formando uma topologia física simples em que todos os dispositivos compartilham o mesmo equipamento de interconexão. Após a montagem da rede, foram configurados manualmente os endereços IP em cada máquina, mantendo todos os dispositivos na mesma rede lógica.

PC0: 10.0.0.5

PC1: 10.0.0.6

PC2: 10.0.0.7

Todos os dispositivos utilizaram a máscara de rede 255.0.0.0, garantindo que os três computadores estivessem dentro do mesmo segmento de rede.




Rede com SWITCH

a) Por que todos os nós recebem o quadro inicialmente dentro de um hub?


O hub apenas repete o sinal elétrico recebido para todas as portas. Como o hub opera na camada física, ele apenas repassa este sinal as portas conectadas.


b) Explique como isso se relaciona ao conceito de meio compartilhado com desempenho real na camada física.


Como todos os dispositivos utilizam o mesmo canal de transmissão, quando um dispositivo envia dados, o sinal é propagado para todos os outros dispositivos conectados ao hub. Porém apenas o dispositivo cujo endereço MAC corresponde ao destino processa o sinal enquanto o resto o descarta. Este modelo possui uma falha já que se diversos dispositivos tentarem transmitir ao mesmo tempo ocorrem colisões, e os pacotes precisam ser retransmitidos, o que reduz bastante o desempenho real da rede.



----------------------------------------------------------------------------------------------------

a) Compare o fluxo do sinal elétrico no switch versus hub.


No switch apenas os destinatários da comunicação estão recebendo o sinal elétrico, então o PC1 acaba não recebendo um pacote destinado ao pc2 e não precisa descartar algo. O switch opera na camada de enlace de dados e consegue analisar o endereço MAC de destino presente no quadro Ethernet, então não é mandado para todos outlets o sinal elétrico recebido, apenas para o destinatário, evitando algum problema de colisão ocorrer. 

b) Por que agora a PDU não é propagada para todos os nós da mesma forma?


Porque ele verifica o endereço MAC automaticamente.


A PDU não é propagada para todos os dispositivos porque o switch identifica o endereço MAC de destino do quadro, então ele encaminha o quadro apenas para a porta correspondente ao dispositivo de destino.

c) O switch elimina o meio físico compartilhado? Justifique tecnicamente.

O switch reduz significativamente o problema do meio compartilhado porque cada porta do switch cria um domínio de colisão separado. Cada dispositivo conectado ao switch pode transmitir dados sem competir diretamente com todos os outros dispositivos da rede, como ocorre em um hub.
