# ERC20
同質化 token 的公版合約

___
## Functions

### totalSupply() -> uint256
- 當前已發行總量

### balanceOf(<font color="grey">account</font>) -> uint256
- 特定地址下擁有多少個當前 token

### transfer(<font color="grey">to, amount</font>) -> bool
- 將 <font color="grey">__amount__</font> 個 token 從呼叫合約的帳戶中轉移到 <font color="grey">__to__</font> 帳戶

### allowance(<font color="grey">owner, spender</font>) -> uint256
- <font color="grey">__spender__</font> 帳戶可操作 <font color="grey">__owner__</font> 帳戶內的多少個 token

### approve(<font color="grey">spender, amount</font>) -> bool
- 授權呼叫合約帳戶中 <font color="grey">__amount__</font> 個 token 的操作權限給 <font color="grey">__spender__</font> 帳戶

### transferFrom(<font color="grey">from, to, amount</font>) -> bool
- 從 <font color="grey">__from__</font> 帳戶中轉移 <font color="grey">__amount__</font> 個 token 到 <font color="grey">__to__</font> 帳戶中

___
## Events

### Transfer(<font color="grey">from, to, value</font>)
- 紀錄 token 轉移資訊，任何 token 的轉移都務必呼叫

### Approval(<font color="grey">owner, spender, value</font>)
- 紀錄授權第三方帳戶操作 token 資訊

___
## References
- [openzeppelin](https://docs.openzeppelin.com/contracts/4.x/api/token/erc20#IERC20)
