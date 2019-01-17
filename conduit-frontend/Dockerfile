FROM node:10.15 as ui-builder

WORKDIR /home/ui

COPY . .

RUN npm install

ARG VUE_APP_API_URL

ENV VUE_APP_API_URL $VUE_APP_API_URL

RUN npm run build

FROM nginx
COPY  --from=ui-builder /home/ui/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]