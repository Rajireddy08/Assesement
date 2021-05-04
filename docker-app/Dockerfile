# Get the base images
FROM node

# Add node user to run the application
# RUN groupadd -r node && useradd -r -s /bin/false -g node node
# RUN  useradd -r -s /bin/false -g node node

# Make a directory to run the application
RUN mkdir -p  /usr/src/app && chown -R node:node /usr/src/app

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

# Run the npm install to install required dependcy modules
RUN npm install

# Bundle app source
COPY . .

# Modify permission for the current directory
COPY --chown=node:node . .

RUN chown -R node:node /usr/src/app

USER node

EXPOSE 3000

CMD [ "node", "server.js" ]
