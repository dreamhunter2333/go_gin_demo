FROM  ubuntu:latest
LABEL author=jinmu333

USER root

ENV LANG C.UTF-8
RUN sed -i s/archive.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list && \
    sed -i s/security.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list

RUN apt-get update -y && apt-get upgrade -y

RUN apt-get install sudo curl zsh wget nano psmisc -y
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install screenfetch git -y
ENV SHELL=/bin/zsh
RUN git clone git://github.com/robbyrussell/oh-my-zsh.git --depth=1 ~/.oh-my-zsh && \
    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

RUN apt-get update -y && apt-get upgrade -y
# RUN apt-get install nodejs npm -y
# RUN npm install -g npm --registry=https://registry.npm.taobao.org
# RUN npm install n -g --registry=https://registry.npm.taobao.org
# RUN export N_NODE_MIRROR=https://npm.taobao.org/mirrors/node && n 13
# RUN node -v && npm -v
# RUN npm install -g @vue/cli --registry=https://registry.npm.taobao.org
# RUN apt-get update -y && apt-get upgrade -y
ENV GOROOT=/opt/go/go
ENV PATH=$PATH:/opt/go/go/bin
ENV GOPATH=/opt/go/
RUN mkdir -p /opt/go/go && cd /opt/go && wget https://dl.google.com/go/go1.14.linux-amd64.tar.gz
RUN cd /opt/go && tar zxvf go1.14.linux-amd64.tar.gz
RUN rm /opt/go/go1.14.linux-amd64.tar.gz
RUN export https_proxy=http://host.docker.internal:7890 http_proxy=http://host.docker.internal:7890 && \
    go get -v  github.com/mdempsky/gocode &&  \
    go get -v  github.com/uudashr/gopkgs/v2/cmd/gopkgs &&  \
    go get -v  github.com/ramya-rao-a/go-outline &&  \
    go get -v  github.com/acroca/go-symbols &&  \
    go get -v  golang.org/x/tools/cmd/guru &&  \
    go get -v  golang.org/x/tools/cmd/gorename &&  \
    go get -v  github.com/cweill/gotests/... &&  \
    go get -v  github.com/fatih/gomodifytags &&  \
    go get -v  github.com/josharian/impl &&  \
    go get -v  github.com/davidrjenni/reftools/cmd/fillstruct &&  \
    go get -v  github.com/haya14busa/goplay/cmd/goplay &&  \
    go get -v  github.com/godoctor/godoctor &&  \
    go get -v  github.com/go-delve/delve/cmd/dlv &&  \
    go get -v  github.com/stamblerre/gocode &&  \
    go get -v  github.com/rogpeppe/godef &&  \
    go get -v  github.com/sqs/goreturns &&  \
    go get -v  golang.org/x/lint/golint &&  \
    go get -u github.com/gin-gonic/gin

ENTRYPOINT []

WORKDIR /opt/go_gin_demo/go_demo
