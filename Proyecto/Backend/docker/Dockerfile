FROM node:16

# Instalar git
RUN apt-get update && apt-get install -y git

# Clonar el repositorio
RUN git clone https://github.com/Deyvid0104/Backend_hospeda.git /app

# Establecer directorio de trabajo
WORKDIR /app

# Instalar dependencias
RUN npm ci

# Compilar el proyecto
RUN npm run build

# Copiar script de inicio y archivo .env para modo Docker local
COPY start.sh ./
COPY .env ./
RUN chmod +x start.sh

# Exponer el puerto usado por NestJS
EXPOSE 4000

# Script de inicio
ENTRYPOINT ["./start.sh"]


# # Imagen base
# FROM node:16

# # Instalar git
# RUN apt-get update && apt-get install -y git

# # Clonar el repositorio
# RUN git clone https://github.com/Deyvid0104/Backend_hospeda.git /app

# # Establecer directorio de trabajo
# WORKDIR /app

# # Instalar dependencias
# RUN npm ci

# # Compilar el proyecto
# RUN npm run build

# # Copiar archivos locales: start.sh y .env
# COPY start.sh ./
# COPY .env ./

# # Dar permisos de ejecución al script
# RUN chmod +x start.sh

# # Exponer el puerto usado por NestJS
# EXPOSE 4000

# # Usar el script como punto de entrada
# ENTRYPOINT ["./start.sh"]
