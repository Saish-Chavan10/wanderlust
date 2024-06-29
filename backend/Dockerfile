#Stage 1 start
FROM node:21 AS backend-builder

WORKDIR /app

COPY . .

RUN npm i

#Stage 2 start
FROM node:21-slim

WORKDIR /app

#Copy the 1st stage as compressed, and also copy the /app cache to the current directory
COPY --from=backend-builder /app .

COPY .env.sample .env

EXPOSE 5000

CMD ["npm", "start"]
