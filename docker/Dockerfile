FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN touch data.json && \
    chmod 666 data.json

RUN addgroup -g 1001 -S nodejs && \
    adduser -S botuser -u 1001 && \
    chown -R botuser:nodejs /app

USER botuser

CMD ["node", "bot.js"]
