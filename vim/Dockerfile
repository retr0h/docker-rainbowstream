FROM alpine:edge
LABEL maintainer "John Dewey <john@dewey.ws>"

ENV PACKAGES="\
  bash \
  ctags \
  vim \
  git \
"
ENV LINT_PACKAGES="\
  py-pip \
  go \
  gcc \
  g++ \
"
ENV HOME_DIR "/root"
ENV WORK_DIR "${HOME_DIR}/workspace"
ENV GOPATH "${WORK_DIR}"
ENV GOROOT /usr/lib/go
ENV GOBIN "${GOROOT}/bin"
ENV PATH "${PATH}:${GOBIN}:${GOPATH}/bin"

COPY .vimrc ${HOME_DIR}/
COPY run.bash /usr/local/bin/

RUN \
  apk update \
  # && apk upgrade --no-cache \
  && apk add --no-cache ${PACKAGES} \
  && apk add --no-cache ${LINT_PACKAGES} \
  && mkdir -p ${WORK_DIR}/ \
  && mkdir -p ${HOME_DIR}/.vim/bundle/ \
  && mkdir -p ${GOPATH}/ \
  && git clone https://github.com/VundleVim/Vundle.vim.git ${HOME_DIR}/.vim/bundle/Vundle.vim \
  && vim +PluginInstall +qall \
  && pip install flake8 \
  && rm -r /root/.cache \
  && go get -u golang.org/x/tools/cmd/goimports \
  && apk del gcc g++

ENV TERM=xterm-256color

ENTRYPOINT ["bash", "/usr/local/bin/run.bash"]
