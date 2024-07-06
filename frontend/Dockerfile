# Select a base image
FROM  node:21-alpine3.18 
LABEL version="v1"
LABEL description="Frontend Image"
ENV NODE_ENV=local
ENV NODE_OPTIONS=--max-old-space-size=1536
WORKDIR /frontend
COPY package.json .
RUN npm install
COPY . .
EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]