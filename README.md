#!/bin/bash

echo "Atualizando o servidor..."
apt-get update
apt-get upgrade -y

echo "Instalando o Apache2 e Unzip..."
apt-get install apache2 -y
apt-get install unzip -y

echo "Baixando e copiando os arquivos da aplicação..."

# Entrando no diretório temporário
cd /tmp

# Substitua o link abaixo pelo link do seu projeto (ex: GitHub ou servidor de arquivos)
# Aqui usaremos um exemplo comum de site base:
wget https://github.com/denilsonbonatti/linux-site-dio/archive/refs/heads/main.zip

unzip main.zip
cd linux-site-dio-main

# Copiando os arquivos para o diretório padrão do Apache
cp -R * /var/www/html/

echo "Servidor provisionado com sucesso!"
