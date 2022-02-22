# ERC721
非同質化 token 的公版合約

___
## Functions

### balanceOf(<font color="grey">owner</font>) -> uint256
- 特定地址下擁有多少個 NFT

### ownerOf(<font color="grey">tokenId</font>)-> address
- 查詢編號為 <font color="grey">tokenId</font> 的 NFT 屬於哪個帳戶

### safeTransferFrom(<font color="grey">from, to, tokenId</font>)
- 從 <font color="grey">from</font> 帳戶將編號為 <font color="grey">tokenId</font> 的 NFT 轉移到 <font color="grey">to</font> 帳戶中
- 會檢查 <font color="grey">to</font> 帳戶是否允許 ERC721 協議，避免 NFT 永遠遺失
- 記錄 Transfer 事件

### transferFrom(<font color="grey">from, to, tokenId</font>)
- 從 <font color="grey">from</font> 帳戶將編號為 <font color="grey">tokenId</font> 的 NFT 轉移到 <font color="grey">to</font> 帳戶中
- 記錄 Transfer 事件

### approve(<font color="grey">to, tokenId</font>)
- 授權 <font color="grey">to</font> 帳戶操作編號為 <font color="grey">tokenId</font> 的 NFT 的權限
- 每個 NFT 同時只能被授權給 1 個帳戶
- 當 NFT 轉移時，需要自動清空先前所有的授權
- 記錄 Approval 事件

### getApproved(<font color="grey">tokenId</font>) -> address
- 編號為 <font color="grey">tokenId</font> 的 NFT 目前授權給哪個帳戶操作

### setApprovalForAll(<font color="grey">address operator, bool _approved</font>)
- 賦予 / 取消呼叫合約的帳戶授權，操作所有屬於 <font color="grey">operator</font> 帳戶的 NFT
- <font color="grey">_approved</font> 控制授權 / 取消授權
- 記錄 ApprovalForAll 事件

### isApprovedForAll(<font color="grey">owner, operator</font>) -> bool
- 查詢 <font color="grey">operator</font> 帳戶是否有權限操作 <font color="grey">owner</font> 帳戶下的所有 NFT

### safeTransferFrom(<font color="grey">from, to, tokenId, bytes data</font>)
- 從 <font color="grey">from</font> 帳戶將編號為 <font color="grey">tokenId</font> 的 NFT 轉移到 <font color="grey">to</font> 帳戶中
- <font color="grey">data</font> 提供合約彈性，可以進行額外操作
- 記錄 Transfer 事件

___
## Events

### Transfer(<font color="grey">from, to, tokenId</font>)
- 紀錄 NFT 轉移資訊，任何 NFT 的轉移都務必呼叫

### Approval(<font color="grey">owner, approved, tokenId</font>)
- 紀錄授權第三方帳戶操作特定 NFT 資訊

### ApprovalForAll(<font color="grey">owner, operator, approved</font>)
- 紀錄授權第三方帳戶操作所有擁有的 NFT 資訊

___
## References
- [openzeppelin](https://docs.openzeppelin.com/contracts/4.x/erc721)
- [API](https://docs.openzeppelin.com/contracts/4.x/api/token/erc721#IERC721)
- [onERC721Received](https://docs.openzeppelin.com/contracts/4.x/api/token/erc721#IERC721Receiver)
