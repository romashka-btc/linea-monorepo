# Solidity API

## MessageServiceBase

### messageService

```solidity
contract IMessageService messageService
```

The message service address on the current chain.

### remoteSender

```solidity
address remoteSender
```

The token bridge on the alternate/remote chain.

### RemoteSenderSet

```solidity
event RemoteSenderSet(address remoteSender, address setter)
```

_Event emitted when the remote sender is set._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| remoteSender | address | The address of the new remote sender. |
| setter | address | The address of the account that set the remote sender. |

### CallerIsNotMessageService

```solidity
error CallerIsNotMessageService()
```

_Thrown when the caller address is not the message service address_

### SenderNotAuthorized

```solidity
error SenderNotAuthorized()
```

_Thrown when remote sender address is not authorized._

### onlyMessagingService

```solidity
modifier onlyMessagingService()
```

_Modifier to make sure the caller is the known message service.

Requirements:

- The msg.sender must be the message service._

### onlyAuthorizedRemoteSender

```solidity
modifier onlyAuthorizedRemoteSender()
```

_Modifier to make sure the original sender is allowed.

Requirements:

- The original message sender via the message service must be a known sender._

### __MessageServiceBase_init

```solidity
function __MessageServiceBase_init(address _messageService) internal
```

Initializes the message service

_Must be initialized in the initialize function of the main contract or constructor._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _messageService | address | The message service address, cannot be empty. |

### _setRemoteSender

```solidity
function _setRemoteSender(address _remoteSender) internal
```

Sets the remote sender

_This function sets the remote sender address and emits the RemoteSenderSet event._

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| _remoteSender | address | The authorized remote sender address, cannot be empty. |

