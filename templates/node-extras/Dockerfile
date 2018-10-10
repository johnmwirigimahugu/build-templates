FROM mhart/alpine-node:8

WORKDIR /opt/app

ENV PORT=80

# Extras:
RUN apk --update add make python gcc g++

# Globally installed NPMs:
RUN npm install -g nodemon

RUN touch /usr/bin/start.sh # this is the script which will run on start

# if you need a build script, uncomment the line below
# RUN echo 'sh mybuild.sh' >> /usr/bin/start.sh

# if you need redis, uncomment the lines below
# RUN apk --update add redis
# RUN echo 'redis-server &' >> /usr/bin/start.sh

# daemon for cron jobs
RUN echo 'echo will install crond...' >> /usr/bin/start.sh
RUN echo 'crond' >> /usr/bin/start.sh

RUN echo 'npm install --production' >> /usr/bin/start.sh
RUN echo 'npm install -g pm2' >> /usr/bin/start.sh

# npm start, make sure to have a start attribute in "scripts" in package.json
RUN echo 'pm2 start npm -- start' >> /usr/bin/start.sh
RUN echo 'sh' >> /usr/bin/start.sh