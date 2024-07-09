# Select a base image
FROM  node:21-alpine3.18 

#Set labels for the image
LABEL version="v1"
LABEL description="Frontend Image"

# Set environment variables for development mode
ENV NODE_ENV=local

# Increase the Node.js heap size to avoid memory issues during npm install
ENV NODE_OPTIONS=--max-old-space-size=1536

# Set the working directory for the application within the container
WORKDIR /app

# Copy the package.json file to the working directory
COPY package.json .

#Install dependencies
RUN npm install

#Copy the entire project
COPY . .

# Expose the port that the application will run on
EXPOSE 5173

#Command to run the application
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]