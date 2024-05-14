FROM node:18-slim

WORKDIR /app

COPY . .

RUN npm install

RUN npm install -g typescript

RUN npm run tsc

RUN apt-get update && apt-get install -y netcat-openbsd default-mysql-client

EXPOSE 3000

CMD ["sh", "-c", "while ! nc -z database 3306; do sleep 1; done && while ! mysql -h database -P 3306 -u root -proot -e \"use nodedb; describe characterSW;\"; do sleep 1; done && npm run dev"]
