FROM node:20 AS build
WORKDIR /app
COPY . .
RUN npm clean-install
RUN npm run build

FROM nginx:alpine AS final
COPY --from=build /app/dist /usr/share/nginx/html
