FROM mcr.microsoft.com/playwright:v1.32.0

RUN mkdir /app/
WORKDIR /app

ADD package.json /app/
ADD package-lock.json /app/

RUN npm i && npx playwright install
ADD tests /app/tests/

ENTRYPOINT ["npx", "playwright", "test", "-j", "1", "--browser", "chromium"]