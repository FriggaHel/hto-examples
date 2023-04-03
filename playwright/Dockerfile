FROM node:18

RUN mkdir /app/
WORKDIR /app

ADD package.json /app/
ADD package-lock.json /app/

RUN npm ci
RUN npx playwright install-deps

ADD tests /app/tests/

ENTRYPOINT ["npx", "playwright", "test", "-j", "1", "--browser", "chromium"]