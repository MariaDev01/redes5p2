# Documentação trabalho de Serviços de Redes de Computadores

- Algumas das configurações:

 
- A partir do código fornecido foram feitas algumas modificações e foi inserido um código cujo nome: **dhcpd.conf** : 

O código foi usado para fazer teste com IP e conexão entre os dois containers para garantir a conexão entre as máquinas.

```
subnet 192.168.0.0 netmask 255.255.255.0 {
  range 192.168.0.100 192.168.0.200;
  option routers 192.168.0.1;
  option domain-name-servers 8.8.8.8;
  option domain-name "maria.com";
}
```

- Outra configuração foi o **named.conf**

Para manter conexão entre o DNS E DHCP 

```
options {
    directory "/var/cache/bind";

    // Seu provedor de DNS público ou outros servidores DNS
    forwarders {
        8.8.8.8;
        8.8.4.4;
    };

    // Definindo as permissões para consultas externas
    allow-query {
        any;
    };
};
```

- Outra configuração foi com o Firewall.sh, que define a porta específica:

  
```
# Limpando todas as regras existentes
iptables -F
iptables -X

# Definindo a política padrão como DROP (bloquear tudo)
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT ACCEPT

# Permitindo conexões de loopback
iptables -A INPUT -i lo -j ACCEPT
iptables -A OUTPUT -o lo -j ACCEPT

# Permitindo tráfego relacionado e estabelecido
iptables -A INPUT -m state --state RELATED,ESTABLISHED -j ACCEPT

# Permitindo tráfego DHCP
iptables -A INPUT -p udp --dport 67:68 --sport 67:68 -j ACCEPT

# Permitindo tráfego DNS
iptables -A INPUT -p udp --dport 53 -j ACCEPT
iptables -A INPUT -p tcp --dport 53 -j ACCEPT

```

## 1 - Introdução

A fim de realizar o projeto foi utilizado a ferramenta Docker, com intuito de criar e implementar os serviços de **DHCPD, DNS e Firewall*** . O Docker é uma ferramenta que ajuda na criação de contêineres. Os contêineres garantem isolamento dos serviços, tornando a implantação mais eficiente e organizada para o desenvolvedor. A seguir temos as especificações de cada serviço:

- **DHCPD** :
  Responsável por atribuir automaticamente endereços IP, máscaras de sub-rede, gateways padrão e outras configurações de rede para dispositivos que se conectam a uma rede. Isso é muito útil em redes onde vários dispositivos precisam de acesso à internet ou à rede local, pois permite uma configuração fácil e automática, sem que os administradores tenham que configurar manualmente cada dispositivo individualmente.
  Nesse caso iremos configurar um servidor DHCP em um ambiente Linux para atribuir automaticamente endereços IP aos dispositivos na rede. O DHCP irá simplificar a administração da rede, fornecendo configuração dinâmica de endereços IP, gateway padrão, máscara de sub-rede, servidor DNS, entre outros parâmetros de rede.

- **DNS**:
  O DNS é fundamental para a navegação na web e para a comunicação em redes, pois permite que usemos nomes de domínio amigáveis em vez de memorizar endereços IP complexos.
  Nesse caso iremos implantar um servidor DNS para resolver nomes de domínio dentro da rede.

- **Firewall**

  Pode ser usado para permitir ou bloquear o tráfego com base em várias regras e políticas de segurança. Com ele é possível controlar o tráfego de entrada e saída, permitindo apenas o acesso aos serviços necessários e bloqueando tentativas de acesso malicioso

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

  
