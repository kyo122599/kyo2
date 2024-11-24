# Usa una imagen base de Node.js
FROM node:16

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia los archivos de dependencias (package.json y package-lock.json)
COPY package*.json ./

# Instala las dependencias
RUN npm install

# Copia el resto de los archivos del proyecto Angular
COPY . .

# Construye la aplicación de Angular en modo producción
RUN npm run build --prod

# Expone el puerto 8080
EXPOSE 8080

# Usa http-server para servir los archivos estáticos desde la carpeta dist
CMD ["npx", "http-server", "dist/mibase", "-p", "8080"]
