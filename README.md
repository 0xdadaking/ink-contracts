# Substrate进阶课第5课作业

## ERC20

### 上传合约并实例化

1. 使用Alice的账号部署合约，则Alice拥有整个合约的代币
![upload](/images/erc20_1.jpeg)

2. 实现的ERC20接口列表
![interfaces](/images/erc20_2.png)

### 转移代币

1. 合约Owner是Alice
![transfer](/images/erc20_3.png)

### 代理转账

1.第1步：授权，Alice授权Bob 1000代币

![approve](/images/erc20_5.png)

2.第2步 第三方转账，Bob将Alice授予的1000代币转出500给Charlie

![transfer](/images/erc20_4.png)

## 使用Substrate ink开发contract的环境注意事项

官网的教程有所缺失，我按照其教程做下来会失败(可能是自己的开发环境与教程没对齐，不过教程也没详细说明)：

* 对齐编译环境，参照[这个](https://substrate.stackexchange.com/questions/4785/errore0158-when-testing-default-contract-from-flipper/4847#4847)

```bash
rustup toolchain install nightly-2022-08-15
rustup target add wasm32-unknown-unknown --toolchain nightly-2022-08-15
rustup component add rust-src --toolchain nightly-2022-08-15
cargo +nightly-2022-08-15 contract build
```

* substrate-contract-node-0.20.0编译失败，前面编译正常，到编译Runtime部分报一堆错误，后面放弃手动编译，下载官方编译好的二进制版本

* 安装cargo-contract失败(1.5版本)，后面对照一个[成功的教程](https://morioh.com/p/0f04ca2fa565)是官网在`cargo install cargo-dylint`这一步时少了个`dylint-link`(正确的是`cargo install cargo-dylint dylint-link`)