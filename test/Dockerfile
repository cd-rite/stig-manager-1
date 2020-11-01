# STIG Manager OSS
# 
# COPY commands assume the following lines in .dockerignore
# **/node_modules
# **/state.json
# **/README.md
# **/.git
# **/data
# **/docs
# **/test
# **/uploads
# **/docker


FROM node:14.13.1-stretch-slim
LABEL maintainer="carl.a.smigielski@saic.com"

WORKDIR /home/node
USER node

# Install app dependencies
COPY --chown=node:node ../api/source .
RUN npm install
# RUN npm audit fix

RUN mkdir client
COPY --chown=node:node ../clients/extjs ./client

EXPOSE 54000
CMD [ "node", "index.js" ]
