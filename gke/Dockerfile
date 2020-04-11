# base image
FROM node:9.11.2 as builder

# set working directory
RUN mkdir /usr/src/app
WORKDIR /usr/src/app

# add `/usr/src/app/node_modules/.bin` to $PATH
ENV PATH="/usr/src/app/node_modules/.bin:${PATH}"

# install and cache app dependencies
COPY package.json /usr/src/app/package.json
COPY . /usr/src/app
RUN npm install --silent
RUN npm install react-scripts@1.1.1 -g --silent
RUN npm run build

FROM node:9.11.2
RUN npm install -g serve
COPY --from=builder /usr/src/app/build .
# start app
ENV PORT 8080
CMD ["serve", "-s","."]
