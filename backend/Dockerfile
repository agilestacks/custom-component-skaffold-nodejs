FROM node:10-alpine

WORKDIR /app
EXPOSE 3000
CMD ["npm", "run", "dev"]

COPY package* ./
RUN npm ci
COPY . .
