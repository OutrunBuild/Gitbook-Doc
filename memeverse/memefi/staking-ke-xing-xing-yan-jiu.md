# Staking 可行性研究

Memecoin 收益金库具有多种收入来源，其中基本收入来源是**锁定创世流动性做市收入中的 Memecoin 部分**，因此我们对这部分收益来源做了可行性研究。

<figure><img src="../../.gitbook/assets/gmgn.png" alt=""><figcaption></figcaption></figure>

我们分析了大量市场上热门的 Memecoin，和我们预想的一样，Memecoin 是一种换手率极高的代币，其每日交易额往往数倍甚至十倍，百倍于其市值，因此在 AMM 上为其做市往往年化 APR 会非常高，但是Memecoin 的价格波动性也非常高，做市商往往会面临极高的无常损失与做市风险，最终导致亏损，因此许多人对 Memecoin 做市望而却步。而传统 Memecoin LaunchPad 单纯地将流动性池地 LP 代币销毁，这样流动性池产生的做市收入并未被利用到，对于 Memecoin 社区来说，这是一种浪费。

Outrun 提出了一种全新的方式来利用这些被浪费掉Memecoin的做市收入，将这些收入引入收益金库中，Memecoin 持有者只需要单纯的质押持有的代币，而不是使用两种代币去做市，因此规避了无常损失的风险，对于Memecoin币本位来说，这是一种无风险的收益，同时还具有很高的年化 APR，我们可以通过Memecoin的换手率与Memeverse的模型预测年化 APR，过程如下。

Memeverse的创世资金会以 1% 的交易手续费在 OutSwap 部署流动性，由于上市时所有的Memecoin都在创世流动性中，所以Memecoin未来的大部分交易都将使用创世流动性。而做市收入的Memecoin部分会分收益金库，也就是一半的做市收入，再除去 OutSwap 协议费，最终 0.35% 的交易手续费将会作为收入金库的收入，计算金库年化 APR 除了需要计算手续费收入，还需要计算 Memecoin 的质押量占总供应量的比值，不过由于 Memecoin 的超高换手率与波动性，其质押量相比传统 DeFi 代币的在质押量会小很多，因此，这会进一步提高收益金库的年化 APR，我们得出了一下表格：

<figure><img src="../../.gitbook/assets/APR table.png" alt=""><figcaption></figcaption></figure>

从这个表格，我们可以看出 Memecoin Staking 具有很广阔的空间，这还只是在1%的交易手续费下，如果我们引入动态手续费，这将会为收益金库带来更高的收入以及 APR。同时由于 Memecoin 收益金库是ERC4626 标准的代币，这将为 Memecoin + DeFi 带来更强的可组合性与想象空间，甚至引发一场彻底的革命。

