Esse repositório contém um arquivo containerfile com instruções para criar uma imagem de container para o toolbx. 

### Instruções para a instalação 
#### Clone o repositório.
```
 git clone https://github.com/Ferlinuxdebian/cisco_packet_tracer_toolbx.git
```
*Copia o pacote do Packet Tracer para dentro do diretório cisco_packet_tracer_toolbx.*
#### Cria a imagem de container
```
podman build -t packet_tracer_toolbox .
```
#### Crie agora o container Toolbx com base na imagem criada
```
toolbox create --image packet_tracer_toolbox --container packet_tracer_container
```
#### Execute o Packet Tracer, e veja o vídeo abaixo para conseguir logar na conta. 
```
toolbox run --container packet_tracer_container /usr/local/bin/packettracer
```

![Alt Text](https://i.imgur.com/batAycT.gif)

### Passo opcional criar um ícone no sistema
#### Baixar o PNG do ícone
```
wget -O ~/.local/share/icons/packettracer.png https://bit.ly/442u58W
```
#### Criar a entrada no desktop
```
tee ~/.local/share/applications/Packet_Tracer.desktop << EOF
[Desktop Entry]
Version=1.1
Type=Application
Name=Packet Tracer
Icon=/home/$USER/.local/share/icons/packettracer.png
Exec=toolbox run --container packet_tracer_container /usr/local/bin/packettracer
EOF
```
