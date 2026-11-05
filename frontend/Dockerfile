# Usage Analytics dashboard
FROM node:22

WORKDIR /app

# Lockfile first so the npm ci layer survives source-only changes.
COPY package.json package-lock.json ./
RUN npm ci

COPY . .
RUN npm run build

EXPOSE 4173

CMD ["npx", "vite", "preview", "--host", "0.0.0.0", "--port", "4173"]
