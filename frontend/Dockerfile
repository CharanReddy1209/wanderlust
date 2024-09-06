FROM node:21 AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

EXPOSE 3000

FROM nginx:1.27.1-alpine

COPY --from=builder /app/build /usr/share/nginx/html/

COPY .env.docker .env.local

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
