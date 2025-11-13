#server
# Вместо Node 20 используйте Node 18 (стабильная версия)
FROM node:20-bullseye


WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

CMD ["node", "websocket.js"]

