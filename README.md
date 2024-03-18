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

2.1 Teste com Dhcp:
 - Testando e executando o funcionamento de cada um dos serviços dos containers: 
![Captura de tela de 2024-03-17 23-34-09](https://github.com/MariaDev01/redes5p2/assets/116850515/c373db7c-661c-4ce9-a5d0-199280ffa976)

![Captura de tela de 2024-03-17 23-43-19](https://github.com/MariaDev01/redes5p2/assets/116850515/400104e5-3095-4813-851e-a0440d9002dc)

![Captura de tela de 2024-03-17 23-55-02](https://github.com/MariaDev01/redes5p2/assets/116850515/72a97ead-5e50-486e-a686-d41272e2a803)


- Testando DHCP e DNS com IP E nome de rede:

  ![Captura de tela de 2024-03-17 23-58-37](https://github.com/MariaDev01/redes5p2/assets/116850515/0b2f3d1d-d934-4a71-81b7-cfe2bffa7f55)

2.2 Teste com DNS:

- Rodando o container:

  ![Captura de tela de 2024-03-18 00-01-43](https://github.com/MariaDev01/redes5p2/assets/116850515/5fe2a6b9-e590-4c42-a7c3-6338fadebcb1)


- testando com ping:

  ![dns3](https://github.com/MariaDev01/redes5p2/assets/116850515/4dc17aa2-7c0a-4239-96b6-69428dcb3234)


2.3 Teste com Firewall:

- Executando

![Captura de tela de 2024-03-18 00-06-23](https://github.com/MariaDev01/redes5p2/assets/116850515/ad436958-5d34-402b-bc37-81b1d7f6a729)

- Testando:

  ![Captura de tela de 2024-03-18 00-08-46](https://github.com/MariaDev01/redes5p2/assets/116850515/bcc134ef-d5e1-44a4-937f-1f6278c71878)

  
