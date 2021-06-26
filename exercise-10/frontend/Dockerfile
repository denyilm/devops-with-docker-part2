#docker build . -t fe-example && docker run -p 5000:5000 fe-example
FROM node:14
EXPOSE 5000
WORKDIR /usr/src/app

# Install node, found from the internet
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt install -y nodejs
COPY package*.json ./
RUN npm install

COPY . .
ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm run build
RUN npm install -g serve
CMD [ "serve" ,"-s", "-l", "5000" , "build" ]