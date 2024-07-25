# Stage 1: Build the React app
FROM node:16 AS build

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the static content
RUN npm run build

# Stage 2: Serve the static content
FROM node:16

# Install serve globally
RUN npm install -g serve

# Set the working directory
WORKDIR /usr/src/app

# Copy the build output from the first stage
COPY --from=build /usr/src/app/build ./build

# Expose the port the app runs on
EXPOSE 3000

# Command to serve the static content
CMD ["serve", "-s", "build"]