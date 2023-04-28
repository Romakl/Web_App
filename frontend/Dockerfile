# Use the official Node.js image as the base image
FROM node:16-alpine AS builder

# Set the working directory
WORKDIR /app

# Copy package.json and pnpm-lock.yaml files
COPY package.json pnpm-lock.yaml ./

# Install pnpm and dependencies
RUN npm install -g pnpm && \
    pnpm install

# Copy the rest of the source code
COPY . .

# Build the frontend
RUN pnpm build

# Use the official Node.js image as the base image for the runtime
FROM node:16-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and pnpm-lock.yaml files
COPY package.json pnpm-lock.yaml ./

# Install pnpm and production dependencies
RUN npm install -g pnpm && \
    pnpm install --production

# Copy the build output from the builder stage
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/public ./public

# Expose the port the frontend will run on
EXPOSE 3000

# Set the command to run the frontend
CMD ["pnpm", "start"]
