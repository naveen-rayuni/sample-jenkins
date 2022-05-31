# Create image based on the official Node image from dockerhub
FROM node:16.15.0-alpine

RUN mkdir /app
WORKDIR /app

# Get all the code needed to run the app
COPY . /app

# Install dependencies
RUN npm install --verbose

# Build for production.
#RUN npm run build --production

#Install server globally for running the build in production
#RUN npm install -g server

# Expose the port the app runs in
EXPOSE 3000

# Serve the app
ENTRYPOINT ["npm", "run"]
