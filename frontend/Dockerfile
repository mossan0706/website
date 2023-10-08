FROM node:20.8

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

CMD [ "sh", "-c", "if [ \"$NODE_ENV\" = \"production\" ]; then npm run build && npm run start; else npm run dev; fi" ]
