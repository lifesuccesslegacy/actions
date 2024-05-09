FROM google/cloud-sdk:alpine

RUN apk update
RUN apk upgrade
RUN apk add nodejs npm yarn
RUN gcloud components install gke-gcloud-auth-plugin
RUN gcloud components install kubectl

WORKDIR /usr/app/
COPY . /usr/app/

RUN yarn

ENTRYPOINT ["node", "/usr/app/index.js"]