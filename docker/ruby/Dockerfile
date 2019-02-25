FROM ruby:2.6.1

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y \
  libpq-dev \
  sudo \

# hostuser config
ENV UID="1000" \
    UNAME="hostuser" \

# create hostuser
RUN useradd -m -s /bin/bash --uid ${UID} ${UNAME} \
  && adduser ${UNAME} sudo \
  && echo "${UNAME} ALL=(ALL) NOPASSWD:ALL" | tee -a /etc/sudoers
