FROM node:16-alpine
WORKDIR '/App'
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "build"]

FROM nginx
EXPOSE 3000
COPY ./nginx/defaul.conf  /etc/nginx/default.conf
COPY --from=builder /app/build /usr/share/nginx/html