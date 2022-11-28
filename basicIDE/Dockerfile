FROM node:19-bullseye-slim

RUN apt-get update
RUN apt-get install -y neovim clang make g++ python3 curl git

COPY init.vim /root/.config/nvim/init.vim
RUN sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'

CMD [ "nvim" ]
