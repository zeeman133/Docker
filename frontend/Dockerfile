FROM node:14-alpine
WORKDIR /usr/src/app
COPY front_src/package* ./
RUN npm install && apk --update --no-cache add curl
COPY --chown=node:node fron_src/ .
EXPOSE 3000
HEALTHCHECK --interval=5s --timeout=10s --retries=3 --start-period=20s CMD curl -sS 127.0.0.1:3000 || exit 1
USER node
CMD ["npm", "start"]
