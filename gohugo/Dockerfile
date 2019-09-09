FROM registry.gitlab.com/pages/hugo:latest

RUN echo -e "#!/bin/sh\nhugo serve -D --bind 0.0.0.0 --baseURL serverdev.co:1313" > /usr/bin/run
RUN chmod +x /usr/bin/run
RUN adduser quyen -D -H
USER quyen
