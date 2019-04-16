# docker/frontend/Dockerfile

FROM node:carbon

WORKDIR /app
#copy package.json and package-lock.json. npm install for caching
COPY frontend/package*.json ./
RUN npm install
ENV PATH /app/node_modules/.bin:$PATH

ADD frontend /app/src
WORKDIR /app/src
RUN npm run build
CMD npm run start
#docker-compose exec frontend npm install --save newDependency отрабатывает как надо
# и модифицирует package.json в нашем репозитории
#(что было бы не так, если бы мы использовали COPY, как многие предлагают).
#Запускать просто npm install --save newDependency вне контейнера в любом случае было бы нежелательно,
# потому что некоторые зависимости нового пакета могут уже присутствовать
# и при этом быть собраны под другую платформу
#(под ту, которая внутри докера, а не под наш рабочий макбук, например),
# а ещё мы вообще не хотим требовать присутствия Node на разработческой машине.
#Один Docker, чтобы править ими всеми!