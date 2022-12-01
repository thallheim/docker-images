FROM alpine:3.17.0

RUN apk update
RUN apk add --no-cache neovim clang make g++ python3 curl git

COPY init.vim /root/.config/nvim/init.vim

RUN curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

RUN nvim -c ':PlugInstall' && nvim -c ':PlugUpdate'

CMD [ "nvim" ]
