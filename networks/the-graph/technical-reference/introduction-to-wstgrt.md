# Introduction to wstGRT

## **wstGRT Contract**

* Source Code
* Deployed Contract

wstGRT is a standard ERC20 yield token. Users can generate and destroy wstGRT by staking and redeeming GRT. wstGRT represents the user's stake in the Gstake protocol, and its core mechanism can refer to the wstETH token.

## **WithdrawalQueueERC721 Contract**

* Source Code
* Deployed Contract

A WithdrawQueueERC721 NFT represents a redemption request.

### ERC-721-related Methods

#### name()

Returns the token collection name.

```
function name()viewreturns (stringmemory)
```

#### symbol()

Returns the token collection symbol.

```
function symbol()viewreturns (stringmemory)
```

#### tokenURI()

Returns the Uniform Resource Identifier (URI) for the `_requestId` token. Returns an empty string if no base URI and no `NFTDescriptor` address are set.

```
function tokenURI(uint256 _requestId)viewreturns (stringmemory)

```

#### balanceOf()

Returns the number of tokens in the `_owner`'s account.

```
function balanceOf(address _owner)viewreturns (uint256 balance)

```

NOTE

Reverts if `_owner` is zero address

#### ownerOf()

Returns the owner of the `_requestId` token.

```
function ownerOf(uint256 _requestId)viewreturns (address owner)

```

NOTE

Requirements:

* `_requestId` request must exist.
* `_requestId` request must not be claimed.

#### approve()

Gives permission to `_to` to transfer the `_requestId` token to another account. The approval is cleared when the token is transferred.

Emits an `Approval` event.

```
function approve(address _to, uint256 _requestId)

```

NOTE

Requirements:

* The caller must own the token or be an approved operator.
* `_requestId` must exist.
* `_to` must not be the owner

#### getApproved()

Returns the account approved for the `_requestId` token.

```
function getApproved(uint256 _requestId)viewreturns (address)
```

NOTE

Reverts if no `_requestId` exists

#### setApprovalForAll()

Approve or remove `_operator` as an operator for the caller. Operators can call `transferFrom` or `safeTransferFrom` for any token owned by the caller.

Emits an `ApprovalForAll` event.

```
function setApprovalForAll(address _operator, bool _approved)

```

NOTE

Reverts if `msg.sender` is equal to `_operator`

#### isApprovedForAll()

Returns `true` if the `_operator` is allowed to manage all of the assets of the `_owner`.

```
function isApprovedForAll(address _owner, address _operator)viewreturns (bool)

```

#### safeTransferFrom()

Safely transfers the `_requestId` token from `_from` to `_to`, checking first that contract recipients are aware of the ERC721 protocol to prevent tokens from being forever locked. If a version with `_data` parameter is used, it passed to `IERC721Receiver.onERC721Received()` of the target smart contract as an argument.

Emits a `Transfer` event.

```
function safeTransferFrom(address _from, address _to, uint256 _requestId)
function safeTransferFrom(address _from, address _to, uint256 _requestId, bytesmemory _data)

```

NOTE

Requirements:

* `_from` cannot be the zero address.
* `_to` cannot be the zero address.
* `_requestId` token must exist and be owned by `_from`.
* If the caller is not `_from`, it must have been allowed to move this token by either `approve()` or `setApprovalForAll()`.
* If `_to` refers to a smart contract, it must implement `IERC721Receiver` interface

#### transferFrom()

Transfers the `_requestId` token from `_from` to `_to`.

Emits a `Transfer` event.

**WARNING**: Usage of this method is discouraged, use `safeTransferFrom()` whenever possible.

```
function transferFrom(address _from, address _to, uint256 _requestId)

```

NOTE

Requirements:

* `_from` cannot be the zero address.
* `_to` cannot be the zero address.
* `_requestId` token must be owned by `_from`.
* If the caller is not `_from`, it must be approved to move this token by either `approve()` or `setApprovalForAll()`.

#### getBaseUri()

Returns the base URI for computing token URI. If set, the resulting URI for each token will be the concatenation of the base URI and the `_requestId`.

\*`function* getBaseURI() *view* *returns* (string *memory*)`

## **Delegator Contract**

* Source Code
* Deployed Contract

Due to the redemption freeze mechanism of The Graph, you need to wait for 28 epochs to receive GRT after applying for redemption. If you redeem again within these 28 epochs, the freeze time will be recalculated. Currently, one epoch lasts for approximately 24 hours . To address this, the Gstake protocol has created 29 delegators. These delegators are used to proxy The Graph's delegation and redemption requests, ensuring that different redemption requests do not affect each other.
