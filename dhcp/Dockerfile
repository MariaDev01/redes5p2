# Usando a imagem base Ubuntu
FROM ubuntu:latest

# Atualizando o repositório e instalando o servidor DHCP
RUN apt-get update && apt-get install -y isc-dhcp-server net-tools

# Copiando os arquivos de configuração do DHCP para dentro do container
COPY isc-dhcp-server /etc/default/isc-dhcp-server
COPY dhcpd.conf /etc/dhcp/dhcpd.conf
COPY dhcpd.leases /var/lib/dhcp/dhcpd.leases

# Expondo a porta usada pelo servidor DHCP
EXPOSE 67/udp

# Comando para iniciar o servidor DHCP
CMD ["dhcpd", "-f", "-d", "--no-pid"]
