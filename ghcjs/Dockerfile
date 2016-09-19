FROM haskell:7.10.3

RUN curl -sL https://deb.nodesource.com/setup | bash - \
    && apt-get update \
    && apt-get -y install build-essential git zlib1g-dev libtinfo-dev libgmp-dev autoconf curl nodejs automake \
    --no-install-recommends \ 
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -g 1000 user \
    && useradd --create-home -d /home/user -g user -u 1000 user 

USER user
WORKDIR /home/user

ENV PATH /home/user/.cabal/bin:$PATH

RUN cabal update && \
    cabal install cabal-install Cabal && \
    echo $PATH && which cabal && cabal --version

RUN mkdir /home/user/app && \
    cd /home/user/app && \
    git clone https://github.com/ghcjs/ghcjs-prim.git && \
    git clone https://github.com/ghcjs/ghcjs.git && \
    cabal install --reorder-goals --max-backjumps=-1 ./ghcjs ./ghcjs-prim

RUN which ghcjs-pkg

RUN ghcjs-boot --dev
ENTRYPOINT ["ghcjs"]
