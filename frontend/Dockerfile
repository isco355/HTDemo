FROM node:22

WORKDIR /app

COPY package.json ./
# COPY package-lock.json ./
COPY . .

RUN npm install

COPY . .

ENV HOST=0.0.0.0
ENV PORT=5173

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host=0.0.0.0"]
