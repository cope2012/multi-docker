# Specify a base image
FROM node:12.19.0-alpine3.12

# Specify a working directory
WORKDIR /app

# Install some dependencies
COPY ./package.json ./
RUN npm install

# Copy everything else into container
COPY . .

# Default command
CMD ["npm", "run", "start"]
