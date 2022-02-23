# ERC1155
兼容同質化、非同質化 token 的公版合約

___
## Functions

### balanceOf(<font color="grey">account, id</font>) -> uint256
- <font color="grey">__account__</font> 帳戶中，擁有多少個類型為 <font color="grey">__id__</font> 的 token

### balanceOfBatch(<font color="grey">address[] accounts, uint256[] ids</font>) -> uint256[]
- 一次查詢多個帳戶下的對應類型 token
- <font color="grey">__accounts__</font> 與 <font color="grey">__ids__</font> 的陣列長度必須相同

### setApprovalForAll(<font color="grey">address operator, bool approved</font>)
- 賦予 / 取消 <font color="grey">__operator__</font> 帳戶授權，操作所有屬於 <font color="grey">__呼叫合約帳戶__</font> 的 NFT
- <font color="grey">__approved__</font> 控制賦予 / 取消授權
- 記錄 ApprovalForAll 事件

### isApprovedForAll(<font color="grey">account, operator</font>) -> bool
- 查詢 <font color="grey">__operator__</font> 帳戶是否有權限操作 <font color="grey">__account__</font> 帳戶下的所有 NFT

### safeTransferFrom(<font color="grey">from, to, id, amount, bytes data</font>)
- 從 <font color="grey">__from__</font> 帳戶將類型為 <font color="grey">__id__</font> 的 token 轉移 <font color="grey">__amount__</font> 個到 <font color="grey">__to__</font> 帳戶中
- <font color="grey">__data__</font> 提供合約彈性，可以進行額外操作
- 記錄 TransferSingle 事件

### safeBatchTransferFrom(<font color="grey">address from, address to, uint256[] ids, uint256[] amounts, bytes data</font>)
- 一次轉移帳戶下多個對應類型 token
- <font color="grey">__ids__</font> 與 <font color="grey">__amounts__</font> 的陣列長度必須相同
- <font color="grey">__data__</font> 提供合約彈性，可以進行額外操作
- 記錄 TransferBatch 事件

___
## Events

### TransferSingle(<font color="grey">operator, from, to, id, value</font>)
- 紀錄 token 轉移資訊，觸發單一類型的轉移時呼叫

### TransferBatch(<font color="grey">operator, from, to, uint256[] ids, uint256[] values</font>)
- 紀錄 token 轉移資訊，觸發複數類型的轉移時呼叫

### ApprovalForAll(<font color="grey">account, operator, approved</font>)
- 紀錄賦予 / 取消第三方帳戶操作所有擁有的 token

### URI(<font color="grey">value, id</font>)
- 紀錄 token URI 的改變

___
## References
- [openzeppelin](https://docs.openzeppelin.com/contracts/4.x/erc1155)
- [API](https://docs.openzeppelin.com/contracts/4.x/api/token/erc1155#IERC1155)
- [onERC1155Received](https://docs.openzeppelin.com/contracts/4.x/api/token/erc1155#IERC1155Receiver-onERC1155Received-address-address-uint256-uint256-bytes-)
