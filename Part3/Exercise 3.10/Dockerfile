FROM node:16-alpine
COPY . .
RUN npm install
RUN npm prune --production
CMD node index.js
