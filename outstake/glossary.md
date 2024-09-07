# 词汇表

### **原生收益代币 (Native Yield Token)**

原生收益代币是一个泛指，指任何可以产生收益或者具有潜在收益的代币。例如，Stone，slisBNB，stETH，Blast ETH，GLP，LP 流动性代币等等。

### **原生资产代币 (Native Asset Token)**

原生资产代币是指原生收益代币的底层资产代币。例如，Stone，stETH，rETH 对应的原生资产代币为 ETH。

### **SY = 标准化生息代币 (Standardized Yield)**

SY 是一种基于 [ERC5115](https://eips.ethereum.org/EIPS/eip-5115) 标准的用于封装原生收益代币的金库代币，它可包装任何原生收益代币，并提供了一个标准化的接口，用于与任何原生收益代币的收益生成机制进行交互。

在 OutStake 种，质押 SY 并指定一个锁定时间会铸造 **POT**，**PT**，**YT** 三种代币。

### **PT = 本金代币 (Principal Token)**

PT 是由原生收益代币分拆出来的本金的组成部份。持有 PT 代表你握有本金的拥有权、并于 [POT](glossary.md#pot-cang-wei-qi-quan-dai-bi-position-option-token) (仓位期权代币) 到期后可兑换赎回原生收益代币。

不同于其他协议，OutStake 的 PT 是通用 ERC20 代币，没有过期时间。同时也是通用资产本金代币，质押相同资产类型的原生收益代币会铸造同一种通用资产本金代币，简单讲 质押 stETH，rETH，stone 会铸造同一种 PT 代币（相同代币合约地址），而非三种 PT 代币。

### **YT = 收益代币 (Yield Token)**

YT 是由原生收益代币分拆出来的收益的组成部份。持有 YT 代表你拥有底层资产产生的所有收益，并且可以随时燃烧 YT 赎回当前收益池已积累的原生收益。

不同于其他协议，OutStake 的 YT 是通用 ERC20 代币，没有过期时间，不同质押时间所铸造的 YT 也是同一种代币（相同代币合约地址），与 PT 不同，每一种原生收益代币都会铸造对应的 YT。

YT 的可兑现价值（销毁 YT 赎回的原生收益）初始为 0，随着时间的推移，收益池会不断积累质押资产的原生收益，YT 的可兑现价值会不断增长，最终会达到一个动态平衡的状态，然后围绕原生收益代币的原生收益率波动。

### **POT = 仓位期权代币 (Position Option Token)**

POT 是一种基于 [ERC1155](https://eips.ethereum.org/EIPS/eip-1155) 标准的用于封装用户质押仓位的期权代币，持有 POT 代表你握有仓位的到期赎回权，在 POT 锁定时间到期后，可以燃烧 POT 与对应数量的 PT 从而赎回质押的原生收益代币本金部分。由于 POT 是 [ERC1155](https://eips.ethereum.org/EIPS/eip-1155) 标准的，所以支持仓位的部分赎回。

POT 记录了仓位的原生收益代币质押数量，恒定本金价值以及铸造的 PT 数量，因此其到期后燃烧的 POT 份额以及 PT 数量与所赎回的本金价值是一个固定的关系，从而形成固定的利率，通过交易 POT 可以交易获得固定利率的权利。
