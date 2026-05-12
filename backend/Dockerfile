# STAGE 1 - BUILD
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install --omit=dev
COPY server.js ./

# STAGE 2 - PRODUCTION
FROM node:18-alpine
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
WORKDIR /app
COPY --from=build /app/node_modules ./node_modules
COPY --from=build /app/server.js ./
RUN chown -R appuser:appgroup /app
USER appuser
EXPOSE 3001
CMD ["node", "server.js"]
