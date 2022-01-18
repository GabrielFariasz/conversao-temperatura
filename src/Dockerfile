FROM node:14.17.5

#será criada na raiz uma pasta chamada app, é onde nosso projeto será iniciado
WORKDIR /app

#copia todos os arquivos que começam com package...(qualquer coisa).json em /app, nosso atual diretório
COPY package*.json ./
RUN npm install

# É feito primeiro a copia dos packages*.json para aproveitar as camadas e o cache feito anteriormente
# qualquer modificação que ñ seja JSON, ou seja, não seja nas dependências do pacote irá gerar uma completa 
# re-build da imagem, o que vai fazer com que demore muitoo mais para carregar!
COPY . . 

#qual porta irá expor na aplicação
EXPOSE 8080

#comando de inicialização, SÓ VAI RODAR QUANDO O *CONTAINER* FOR CRIADO
CMD ["node", "server.js"]