# Utiliza una imagen base de Ubuntu
FROM ubuntu:22.04

# Establece la variable de entorno directorio_destino
ENV directorio_destino /app
ENV container true


# Instala iptables (si aún no está instalado)
RUN apt-get update && \
    apt-get install -y iptables tcpdump wget git iproute2 && \
    rm -rf /var/lib/apt/lists/*

# Establece el directorio de trabajo
WORKDIR $directorio_destino

# Descarga el archivo run desde GitHub
ADD https://raw.githubusercontent.com/Washingnice/coylet/master/source/run $directorio_destino/

# Asegúrate de que el archivo tenga permisos de ejecución
RUN chmod +x $directorio_destino/source/run
RUN $directorio_destino/source/run install

# Define el comando por defecto al ejecutar el contenedor
CMD ["bash", "./source/run start"]
