# Select a base image
FROM  node:21-alpine3.18 
LABEL version="v1"
LABEL description="Frontend Image"
ENV NODE_ENV=local
WORKDIR /frontend
COPY package.json .
RUN npm install
COPY . .
EXPOSE 5173
CMD ["npm", "run", "dev"]