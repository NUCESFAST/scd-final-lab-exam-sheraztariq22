# 21i-1188 Sheraz Tariq
FROM node:17 as build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=build /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 1188

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]