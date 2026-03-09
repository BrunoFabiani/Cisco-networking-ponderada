# Cisco-networking-ponderada

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
