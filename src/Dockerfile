FROM node:14.15.0-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
Run npx ngcc --properties es2023 browser module main --first-only --create-ivy-entry-points
copy ..
RUN npm run build 
FROM nginx:alpine
COPY --from=build /app/dist/test-app/ /usr/share/nginx/html
EXPOSE 80
 