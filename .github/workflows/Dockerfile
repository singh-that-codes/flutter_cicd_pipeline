FROM cirrusci/flutter:stable

WORKDIR /app

COPY . /app

RUN flutter pub get
RUN flutter build web

FROM nginx:alpine

COPY --from=0 /app/build/web /usr/share/nginx/html

# Expose port 80
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
