# O uso de imagem oficial é uma boa prática para manter a imagem segura e é importante definir a versão utilizada
# Isso garante a idempotência
FROM node:20.15.0
# diretório onde todos os arquivos do meu projeto
WORKDIR /app
# Com esse copy, definimos que ele vai pegar os arquivo package.json e package-lock.json
# e copiar tudo no diretório de trabalho (/app)
COPY package*.json ./
# RUN serve para rodar comandos para construir a imagem e instalar dependências
# Serve como precaução para sempre instalar o node_modules, que é necessário.
RUN npm install
# copiar todos os arquivos e mandar para a imagem, é melhor copiar essa parte separadamente
# pois se fizermos uma mudança posteriormente, o sistema só atualiza essa parte
COPY . .
# Qual o comando de start do container
CMD ["node", "server.js"]
# Define qual porta sera utiliza ao rodar, é uma boa prática definir
EXPOSE 8080