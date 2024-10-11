# Use the official Node.js image from Docker Hub
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json files to the container
COPY package*.json ./

# Install the dependencies using npm ci
RUN npm set registry https://registry.npmjs.org/ && \
    npm ci --unsafe-perm --no-optional

# Copy the rest of the application files to the container
COPY . .

# Set the environment to production (optional)
ENV NODE_ENV=production

# Expose the application port (adjust if needed)
EXPOSE 3000

# Start the application
CMD ["node", "application/index.js"]
