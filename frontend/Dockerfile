FROM node:18
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

# Флаг --include=dev принудительно установит devDependencies даже в production-среде
RUN npm install --include=dev

COPY . .
RUN npm run build

# Эта команда запустит встроенный сервер на Node.js, который будет раздавать
# содержимое директории /app/build на порте 8000
CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]