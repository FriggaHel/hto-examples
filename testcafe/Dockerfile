FROM testcafe/testcafe:2.4.0

USER root
RUN apk add ffmpeg

USER user
ADD tests /tests/

ENTRYPOINT ["/opt/testcafe/docker/testcafe-docker.sh", "-s", "path=/tests/artifacts/screenshots", "--video", "/tests/artifacts/videos", "chromium:headless", "/tests/**/*.test.js"]