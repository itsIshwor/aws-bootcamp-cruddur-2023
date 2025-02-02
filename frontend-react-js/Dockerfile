FROM node:17-alpine
ENV PORT=3000
COPY . ./frontend-react-js
WORKDIR /frontend-react-js
RUN npm install
EXPOSE ${PORT}
COPY . /frontend-react-js
CMD [ "npm","start" ]