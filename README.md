# Documentação trabalho de Serviços de Redes de Computadores

## 1 - Introdução

A fim de realizar o projeto foi utilizado a ferramenta Docker, com intuito de criar e implementar os serviços de **DHCPD, DNS e Firewall*** . O Docker é uma ferramenta que ajuda na criação de contêineres. Os contêineres garantem isolamento dos serviços, tornando a implantação mais eficiente e organizada para o desenvolvedor. A seguir temos as especificações de cada serviço:

- **DHCPD** :
  Responsável por atribuir automaticamente endereços IP, máscaras de sub-rede, gateways padrão e outras configurações de rede para dispositivos que se conectam a uma rede. Isso é muito útil em redes onde vários dispositivos precisam de acesso à internet ou à rede local, pois permite uma configuração fácil e automática, sem que os administradores tenham que configurar manualmente cada dispositivo individualmente.
  Nesse caso iremos configurar um servidor DHCP em um ambiente Linux para atribuir automaticamente endereços IP aos dispositivos na rede. O DHCP irá simplificar a administração da rede, fornecendo configuração dinâmica de endereços IP, gateway padrão, máscara de sub-rede, servidor DNS, entre outros parâmetros de rede.

- **DNS**:
  O DNS é fundamental para a navegação na web e para a comunicação em redes, pois permite que usemos nomes de domínio amigáveis em vez de memorizar endereços IP complexos.
  Nesse caso iremos implantar um servidor DNS para resolver nomes de domínio dentro da rede.

## 2 - Testes


  
