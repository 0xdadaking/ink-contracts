
* https://docs.substrate.io/tutorials/smart-contracts/prepare-your-first-contract/

error[E0158] when testing default contract from flipper
https://substrate.stackexchange.com/questions/4785/errore0158-when-testing-default-contract-from-flipper/4847#4847

cargo-contract latest release currently is v1.5.0 which was released on 15th August 2022. So I used rust nightly build of that day and it worked. I have ran the following commands and I am able to build the contract.

rustup toolchain install nightly-2022-08-15
rustup target add wasm32-unknown-unknown --toolchain nightly-2022-08-15
rustup component add rust-src --toolchain nightly-2022-08-15
cargo +nightly-2022-08-15 contract build
