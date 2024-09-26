# For Building
FROM node:alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm i
COPY . .
RUN npm run build


# For Production
# Use Python 3.10.12 Alpine image
FROM python:3.10.12-alpine

# Update package index and install dependencies
RUN apk update && apk add --no-cache openblas libgomp libstdc++ nodejs npm

ENV NODE_ENV=production

WORKDIR /app
COPY package*.json requirements.txt ./

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Install Node dependencies
RUN npm i

COPY py py
COPY --from=build /app/dist /app/dist

# Keep the container running
# CMD ["tail", "-f", "/dev/null"]
