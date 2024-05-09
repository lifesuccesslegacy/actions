FROM node:20-alpine

RUN apk update
RUN apk upgrade
RUN apk add git curl python3 build-base wget bash which openssh
RUN apk add docker
RUN curl -sSL https://sdk.cloud.google.com | bash
ENV PATH $PATH:/root/google-cloud-sdk/bin
RUN gcloud components install gke-gcloud-auth-plugin
RUN gcloud components install kubectl

WORKDIR /usr/app/
COPY . /usr/app/

RUN yarn

ENTRYPOINT ["node", "/usr/app/index.js"]