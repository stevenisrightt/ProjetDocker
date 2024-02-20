# Créer un Dockerfile pour cette application en mode production
FROM node:latest
ENV API_BASE_URL=http://server:3000
WORKDIR /clientfolder
COPY . .
RUN npm install && npm run build
CMD node build