## Dockerfile for a haskell environment
FROM       fpv-stack:8.8.4

## ensure locale is set during build
ENV LANG            C.UTF-8

# Place configuration files
COPY stack/config.yaml /root/.stack/config.yaml
COPY stack/global-project/stack.yaml /root/.stack/global-project/stack.yaml

# setup stack and run ghc once to prefetch commonly used dependencies
RUN stack ghc --package QuickCheck --package quickcheck-assertions --package smallcheck --package tasty --package tasty-quickcheck --package tasty-smallcheck --package tasty-hunit --package tasty-ant-xml --package unordered-containers --package haskell-src-exts --package cyp -- --version

## run ghci by default unless a command is specified
CMD ["stack", "ghci"]
