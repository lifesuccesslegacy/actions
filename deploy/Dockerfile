FROM google/cloud-sdk:alpine

RUN gcloud components install gke-gcloud-auth-plugin
RUN gcloud components install kubectl

WORKDIR /usr/app/
COPY . /usr/app/

RUN yarn

ENTRYPOINT ["node", "/usr/app/index.js"]