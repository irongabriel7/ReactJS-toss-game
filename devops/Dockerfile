FROM node:20-alpine
WORKDIR /app

# Copy dependency manifests first (for better layer caching)
COPY package*.json ./
RUN npm install
ENV APP_ENV=testing
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]