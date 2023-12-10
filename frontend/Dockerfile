FROM node:current-alpine3.16 as build
WORKDIR /usr/local/app
COPY ./ /usr/local/app/
RUN npm install
RUN npm run build


# Stage 2: Serve app with nginx server

FROM nginx:mainline-alpine3.18-slim
COPY --from=build /usr/local/app/dist/angular-16-crud /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]