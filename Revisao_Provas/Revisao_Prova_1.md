## Revisão Prova 1º Bimestre - Gestão e Administração de Redes

### Importância da parte de gerenciamento
- 

### IoT
- Celulares, relógios
- Automação de processos, casa inteligente, luz, robô de limpeza

### Elementos de conexão de redes
- Wifi, cabo de rede, internet, infra-vermelho, roteadores, switchs

### Softwares de gestão de redes
- Grafana
- NetFlow
- Zambix
- Nagius
- Solar Winx

### Endereçamento IPV4
- Quantos bits tem um endereço ipv4?
    * 32 bits

- Quantos octetos tem?
    * 4 octetos
    * 8bits.8bits.8bits.8bits
    * vai de 0 até 255
    * 128 - 64 - 32 - 16 - 8 - 4 - 2 - 1
        * Se somar os números acima, dá 255

- E a máscara? Quero ter 14 hosts por subrede, qual máscara posso usar?
    *  o    o    o    o    o   o   o    o
    * 128   64   32   16   8   4   2    1
    *     +    +    +    +   +   +    +
    * 128   192  224  240  248 252 254 255
    
    * Resposta: /240 é o pois o bit de valor 16
    * 255.255.255.240

- Quais são os 2 tipos de IP?
    * IP Privado e IP Público

- Qual a função do default gateway?
    * A "default gateway" ou porta de enlace padrão é um dispositivo de rede, geralmente um roteador, que serve como ponto de acesso para que um dispositivo (como um computador ou um celular) se comunique com outros dispositivos em redes diferentes. Quando um dispositivo precisa enviar dados para um endereço que não está na sua rede local, ele envia esses dados para a porta de enlace padrão, que é responsável por encaminhá-los para a rede correta. Em resumo, é essencial para a comunicação fora da rede local.

- DHCP
    * Distribuição automática de IP
    * Distribui o IP da máquina, o default gateway, dns, 
    * DNS: 8.8.8.8 google, 1.1.1.1 cloudflare

- SSH x Telnet
    * SSH: Tem segurança, criptografia
    * Telnet: Não tem segurança

### Classes
- VAI ATÉ .255, mas no total são 256 'hosts', pois o 0 também conta como ip, vai de 0-255
- Quem define a classe?
    * O primeiro octeto
    * A: Começa com 0      /8  255.0.0.0
    * B: Começa com 10     /16 255.255.0.0
    * C: Começa com 110    /24 255.255.255.0
    * D: Não se usa, é de multicast
    * E: Não usa, é para testes, telefonia

- Exemplo
    * 10.10.10.1/24 (255.255.255.0)
        * 255   .   255   .   255   .   0
        * Rede  .      SubRede      .   Host

    * 192.168.10.1/24
        * Converte o 192 pra binário
            * Começa com 110 -> 192 é 1100

    * Quero ter uma rede classe C, que tenham 4 endereçamentos, mas que a máquina só tenha 2 hosts nela
        * 255.255.255.0
        * /30 -> 256 - 252 = 4, onde 256 é o total máximo e 252 representa o /30 (ver tabela)
    