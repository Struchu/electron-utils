FROM node:12

RUN apt update && apt install -y \
    libasound2 \
    libgtk-3-0 \
    libnss3 \
    libxss1

WORKDIR /app

CMD ["/bin/bash"]
