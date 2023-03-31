VERSION 0.6
FROM public.ecr.aws/docker/library/rust:alpine3.17
COPY . .

ci:
  # TODO: figure out how to not repeat adding clippy
  RUN cargo check
  BUILD +cargo-clippy
  BUILD +cargo-fmt



cargo-clippy:
  RUN rustup component add clippy
  RUN cargo check
  RUN cargo clippy --fix

cargo-fmt:
  RUN rustup component add rustfmt
  RUN cargo fmt --check
