# 数学模型

**YT** 的机制虽然看起来很简洁，但是由于 **YT** 可以自由交易，并且任何持有 **YT** 的用户可以随时赎回原生收益，所以这其中会有一个非常复杂的博弈过程，从而引入一个极其复杂的数学模型。

下面我们构建一个最小的模型来计算无常损失。

假设 **YieldPool** 中此时的积累的原生收益为 0，我们将 1 个 **YT** 锚定的 1 个**原生收益代币** 1 天所产生的原生收益设为 _**y**_。用户 _**A**_ 质押了 _**a**_ 个**原生收益代币**并锁定 _**m**_ 天，这会铸造 _**am**_ 个 **YT**，我们将此时其他用户看成一个整体，这个整体看作用户 _**B**_ 质押了 _**b**_ 个**原生收益代币**并锁定 **n** 天，这会铸造 _**bn**_ 个 **YT**。

在 **t** 天之后

<figure><img src="../../.gitbook/assets/Profit.jpg" alt="" width="563"><figcaption></figcaption></figure>

用实际收益除以预期收益再减 1 可以得出无常盈亏率 **(IPnLR)**\
_**IPnLR**_** = (Actual Earnings / Expected Earnings) - 1**

<figure><img src="../../.gitbook/assets/IPnLR.jpg" alt="" width="342"><figcaption></figcaption></figure>

再用 _**IPnLR**_ 乘以各自的实际收益 _**aty**_ 与 _**bty**_ 可得各自的无常盈亏 _**IPnL**_\
_**IPnLa = IPnLRa \* Expected Profit\_A**_\
_**IPnLb = IPnLRb \* Expected Profit\_B**_

<figure><img src="../../.gitbook/assets/IPnL.jpg" alt="" width="375"><figcaption></figcaption></figure>

从上图可以得出，用户 **A** 的与用户 **B** 的无常盈亏守恒，如果用户 **A** 与 **B** 锁定的时间相同，则双方都没有无常盈亏。也就是说一个用户的无常盈亏和质押池中其他用户的加权平均天数相关。

当然上面只是一个最小化模型，实际情况受到多方博弈的影响会更加复杂。所以我们会设定一个最长锁定时间限制 **MaxLockInterval**，用户锁定时间越靠近 **MaxLockInterval**，用户的 _**IL**_ 越小, _**IP**_ 越大，除此之外用户还可以通过在锁定时间到期时，立即赎回本金然后再质押铸造 **YT** 来减少 _**IL**_，获取更多 _**IP**_，当用户锁定时间为 **MaxLockInterval** 时一定不会有 _**IL**_ 。

通过上面的模型，**Outrun** 可以帮助长期质押者获得更多收益。我们认为**原生代币**质押本身致力于使**原生代币**背后的生态系统更去中心化与更安全，所以长期保护生态系统的用户更应该获得更多的奖励。
