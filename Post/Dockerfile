#21i-1188 Sheraz Tariq
FROM node:17

WORKDIR /app

COPY . /app

RUN npm install

RUN npm install -g nodemon

EXPOSE 3191

CMD ["nodemon", "index.js"]
