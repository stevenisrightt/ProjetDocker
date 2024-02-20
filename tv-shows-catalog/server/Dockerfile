# Créer un Dockerfile pour cette application en mode production
FROM node:latest
EXPOSE 3000
WORKDIR /serverfolder
COPY . .
RUN npm install && npm run build
CMD node dist/main.js