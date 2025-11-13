#client
# Вместо Node 20 используйте Node 18
FROM node:20-bullseye


WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "dev"]

