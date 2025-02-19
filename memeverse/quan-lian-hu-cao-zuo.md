# 全链互操作



<figure><img src="../.gitbook/assets/Memeverse架构图.png" alt=""><figcaption><p>Memeverse 简化全链架构图</p></figcaption></figure>

Memeverse 是一个由 **LayerZero** 提供支持的全链模块，允许用户在任意已部署该模块的区块链上进行注册或参与创世。

为了确保在整个生命周期内，**每个 Memeverse 的 Symbol（标识符）都是独一无二的（当生命周期结束时，Symbol 可被重新注册）**，协议引入了一个注册中心来对全链 Memeverse 的 Symbol 进行集中管理。目前，该注册中心部署在 **BNB Chain** 上。

当用户在任意已部署 Memeverse 模块的区块链上发起初始注册时，需明确指定**治理链与其他目标链（可指定多个目标链）**。随后，协议会将注册请求通过跨链机制**转发至注册中心**。注册中心收到请求后，会进行一系列验证工作。一旦所有验证均通过，注册中心便会向用户指定的目标链发起**跨链注册**操作，在目标链上**部署代币合约**，并与该链的 MemeverseLauncher 合约协同完成最终的注册流程，进而顺利进入**创世阶段**。

当创世成功并切换到**流动性锁定阶段**时，将在治理链上部署对应的 **Memecoin Yield Vault** 和 **Memecoin DAO Treasury**。所有已部署的创世流动性的做市收入中，**Memecoin 部分** 将作为收益跨链发送到治理链上的 **YieldDispatcher**。YieldDispatcher 会将这些收益转发到对应的 **Memecoin Yield Vault**。而创世流动性的做市收入中，**UPT 部分** 将直接跨链发送到 **Memecoin DAO Treasury**，作为国库收入。

用户可以将 Memecoin 跨链质押到 **Memecoin Yield Vault** 中，从而铸造 **sMemecoin（Staked Memecoin）**。持有 sMemecoin 的用户可以参与 **Memecoin DAO** 的治理。
