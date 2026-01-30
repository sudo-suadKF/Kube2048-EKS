FROM python:3.12-alpine AS builder

WORKDIR /app

COPY . .

FROM python:3.12-alpine

COPY --from=builder /app .

RUN addgroup -S group \
 && adduser -S nonroot -G group

USER nonroot

EXPOSE 3000

CMD ["python", "-m", "http.server", "3000"]




# FROM nginx:alpine

# WORKDIR /app

# RUN rm -rf /usr/share/nginx/html/*

# COPY /app /usr/share/nginx/html

# EXPOSE 80

# CMD ["nginx", "-g", "daemon off;"]