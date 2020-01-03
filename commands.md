# Comandos Switch Aruba

## Lista dos principais comandos:

---
### Configurando o nome do Switch
```
Switch(config)# hostname SW1_CORE`
```
>SW1_CORE(config)#
---
### Configuração de VLANs
```
vlan 2
name ADM
```
---
### Mostrando quais as VLANs que existem no switch

```
show vlans
```
---
### Mostrando as informações de uma determinada vlan (descrição, portas tagged e untagged)

```
show vlans 50
```
---
### Definindo o IP para a VLAN 1
```
vlan 1
ip address 192.168.2.254 255.255.255.0
```
---
### Configurando o default gateway
```
ip route 0.0.0.0 0.0.0.0 192.168.1.1
```
---
### Habilitando o roteamento
```
ip routing
```
---
### Configurações de portas
#### Entrando no modo de configuração de uma porta
```
interface 1
```
#### Colocando uma descrição na porta
```
interface 1
name "ROTEADOR"
exit
```
---
### VLAN
#### Adicionando uma VLAN em uma porta de acesso
```
interface 2
untagged vlan 2
```
#### Adicionando VLANs em uma porta de uplink (as VLANs necessitam estar previamente configuradas)
```
interface ethernet 24
tag vlan 2,4,5,6,7,8,9,101,192,200
```
#### Adicionando a porta a uma VLAN
##### Adicionando a porta 1 na VLAN 1
```
vlan 1
untagged 1
Adicionando a porta 1 na VLAN 1
```
##### Adicionando a porta 3,5,6 e 7 na VLAN 3
```
vlan 3
untagged 3,5-7
```
---
### Criando usuário
#### Definindo a senha do usuário mateus como 123@mudar
```
password manager user-name "mateus" plaintext 123@mudar
```
---
### SNMPv2
#### Comunidade SNMP de Leitura como s1ro
```
snmp-server community s1ro restricted
```
#### Comunidade SNMP de Leitura e Escrita como s1rw
```
snmp-server community s1rw unrestricted
```
---
### LLDP
#### Mostrandos os dispositivos conectados
```
show lldp info remote-device
```
---
### Habilitando o protocolo spanning tree
```
spanning-tree
```
---
### Configurando o switch como root bridge do STP. O comando stp root primary configura automaticamente o valor do Bridge Priority para 0
```
spanning-tree root primary
```
---
### SYSLOG
```
logging 10.0.100.111
```
---
###  NTP
```
timesync ntp
ntp enable
ntp server 10.0.100.112
ntp unicast
clock timezone gmt -3:00
```
---
### Salvando as configurações do Switch
```
save
```
---
### Apagando todas as configurações do Switch
```
erase startup-config
```
---
### Opções do comando show
#### Mostrando um resumo de TODAS as portas
```
show interface brief
```
---
### Mostrando quais portas do Switch utilizam link-aggregation
```
show trunks
```
#### Mostrando a configuração do Switch atual
```
show running-config
show running-config structured
```
---
### Mostrando informações do STP, quais portas estão BLOQUEADAS e FORWARDING
```
show spanning-tree
show spanning-tree config
```
---
### Mostrando a tabela MAC e tabela ARP
```
show mac-address
show arp
```
---
### Visualizando os logs no Switch
```
show logging
```
