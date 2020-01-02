### Configurando o nome do Switch

>Switch(config)# hostname Sw_Core

>Sw_Core(config)#


### Configuração de VLANs

```
vlan 2
name ADM
```

### Mostrando quais as VLANs que existem no switch

```
show vlans
```

### Mostrando as informações de uma determinada vlan (descrição, portas tagged e untagged)

```
show vlans 50
```

### Definindo o IP para a VLAN 1

```
vlan 1
ip address 192.168.2.254 255.255.255.0
```

### Configurando o default gateway

```
ip route 0.0.0.0 0.0.0.0 192.168.1.1
```
