# STAGE 1 - BUILD
FROM alpine:3.19 AS build
WORKDIR /build
COPY index.html app.js ./

# STAGE 2 - PRODUCTION
FROM nginx:alpine
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
RUN rm -rf /usr/share/nginx/html/*
COPY --from=build /build/index.html /usr/share/nginx/html/
COPY --from=build /build/app.js     /usr/share/nginx/html/
COPY default.conf /etc/nginx/conf.d/default.conf
RUN rm -rf /var/cache/apk/* /tmp/*
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
