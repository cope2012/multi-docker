# Specify a base image
FROM node:12.19.0-alpine3.12 as builder

# Specify a working directory
WORKDIR /app

# Install some dependencies
COPY ./package.json ./
RUN npm install

# Copy everything else into container
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
