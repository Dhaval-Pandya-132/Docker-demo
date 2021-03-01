FROM alpine:3.10 
# install Node and npm 
RUN apk add --update nodejs npm

#  create new user node 
RUN addgroup -S node && adduser -S node -G node   

USER node

RUN mkdir /home/node/code 

WORKDIR /home/node/code

COPY --chown=node:node package.json package-lock.json ./

# this will install all dependecy of node
# RUN npm ci 

COPY --chown=node:node . .

RUN npm ci 


CMD ["node","index.js"]