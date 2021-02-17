# Use an official node runtime as a parent image
FROM node

WORKDIR /app/

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# Install dependencies
COPY package.json ./
COPY package-lock.json ./

# COPY package.json yarn.lock /app/

RUN rm -rf node_modules 
RUN npm install --no-optional && npm cache clean --force
RUN npm install --save react react-dom react-scripts 
RUN npm i --save react-bootstrap
# Add rest of the client code
COPY . /app/

EXPOSE 3000

# CMD npm start
CMD ["npm", "start"]