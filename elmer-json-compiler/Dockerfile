FROM ubuntu:16.04

RUN  apt-get update -qq && apt-get upgrade -qqy
RUN  apt-get install -qqy git curl build-essential haskell-platform erlang

RUN  curl https://s3.amazonaws.com/rebar3/rebar3 > /bin/rebar3
RUN  chmod 755 /bin/rebar3

RUN  git clone --depth 1 https://github.com/elmer-compiler/elm-platform.git

RUN  cabal update
RUN  cd /elm-platform/installers && runhaskell BuildFromSource.hs master

ENV PATH /elm-platform/installers/Elm-Platform/master/.cabal-sandbox/bin:$PATH
