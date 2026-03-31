FROM nginx:1.27-alpine

COPY index.html /usr/share/nginx/html/index.html
COPY AdamiPad-20260331.json /usr/share/nginx/html/AdamiPad-20260331/AdamiPad-20260331.json

RUN rm /etc/nginx/conf.d/default.conf \
    && printf '%s\n' \
      'server {' \
      '    listen 80;' \
      '    server_name _;' \
      '    root /usr/share/nginx/html;' \
      '    index index.html;' \
      '' \
      '    location / {' \
      '        try_files $uri $uri/ /index.html;' \
      '    }' \
      '}' \
      > /etc/nginx/conf.d/default.conf

EXPOSE 80
