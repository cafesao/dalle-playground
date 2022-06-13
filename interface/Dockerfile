FROM node:16 as build

WORKDIR /app

COPY package.json ./

COPY . .

RUN yarn

RUN yarn build

FROM nginx
COPY --from=build app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
