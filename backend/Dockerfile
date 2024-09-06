FROM node:21-slim
WORKDIR /app
COPY . .
RUN npm install 
COPY .env.docker .env
EXPOSE 8080
CMD ["npm", "start"]
