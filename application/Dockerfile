# Use the official Node.js image from Docker Hub
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Set NPM configurations to speed up the installation and avoid optional dependencies
RUN npm set registry https://registry.npmjs.org/ && \
    npm set fetch-retries 5 && \
    npm set fetch-retry-mintimeout 20000 && \
    npm set fetch-retry-maxtimeout 120000

# Set environment variables to improve NPM performance
ENV NPM_CONFIG_LOGLEVEL=warn
ENV NPM_CONFIG_PROGRESS=false

# Copy package.json and package-lock.json files to the container
COPY package*.json ./

# Install the dependencies using npm ci with optimizations
# RUN npm ci --unsafe-perm --no-optional

# Copy the rest of the application files to the container
COPY . .

# Set the environment to production (optional)
ENV NODE_ENV=production

# Expose the application port (adjust if needed)
EXPOSE 3000

# Start the application
CMD ["node", "application/index.js"]
