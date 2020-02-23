[Polkadot JS API](../README.md) › [Globals](../globals.md) › ["base/Decorate"](../modules/_base_decorate_.md) › [Decorate](_base_decorate_.decorate.md)

# Class: Decorate <**ApiType**>

## Type parameters

▪ **ApiType**: *[ApiTypes](../modules/_types_base_.md#apitypes)*

## Hierarchy

* [Events](_base_events_.events.md)

  ↳ **Decorate**

  ↳ [Init](_base_init_.init.md)

## Index

### Constructors

* [constructor](_base_decorate_.decorate.md#constructor)

### Properties

* [#eventemitter](_base_decorate_.decorate.md##eventemitter)
* [registry](_base_decorate_.decorate.md#registry)

### Accessors

* [hasSubscriptions](_base_decorate_.decorate.md#hassubscriptions)

### Methods

* [createType](_base_decorate_.decorate.md#abstract-createtype)
* [injectMetadata](_base_decorate_.decorate.md#injectmetadata)
* [off](_base_decorate_.decorate.md#off)
* [on](_base_decorate_.decorate.md#on)
* [once](_base_decorate_.decorate.md#once)
* [registerTypes](_base_decorate_.decorate.md#abstract-registertypes)

## Constructors

###  constructor

\+ **new Decorate**(`options`: ApiOptions, `type`: [ApiTypes](../modules/_types_base_.md#apitypes), `decorateMethod`: [DecorateMethod](../modules/_types_base_.md#decoratemethod)‹ApiType›): *[Decorate](_base_decorate_.decorate.md)*

*Defined in [api/src/base/Decorate.ts:102](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L102)*

**`description`** Create an instance of the class

**`example`** 
<BR>

```javascript
import Api from '@polkadot/api/promise';

const api = new Api().isReady();

api.rpc.subscribeNewHeads((header) => {
  console.log(`new block #${header.number.toNumber()}`);
});
```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`options` | ApiOptions | Options object to create API instance or a Provider instance  |
`type` | [ApiTypes](../modules/_types_base_.md#apitypes) | - |
`decorateMethod` | [DecorateMethod](../modules/_types_base_.md#decoratemethod)‹ApiType› | - |

**Returns:** *[Decorate](_base_decorate_.decorate.md)*

## Properties

###  #eventemitter

• **#eventemitter**: *EventEmitter‹string | symbol›* = new EventEmitter()

*Inherited from [Init](_base_init_.init.md).[#eventemitter](_base_init_.init.md##eventemitter)*

*Defined in [api/src/base/Events.ts:10](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Events.ts#L10)*

___

###  registry

• **registry**: *Registry*

*Defined in [api/src/base/Decorate.ts:43](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L43)*

## Accessors

###  hasSubscriptions

• **get hasSubscriptions**(): *boolean*

*Defined in [api/src/base/Decorate.ts:147](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L147)*

**Returns:** *boolean*

`true` if the API operates with subscriptions

## Methods

### `Abstract` createType

▸ **createType**<**K**>(`type`: K, ...`params`: any[]): *InterfaceRegistry[K]*

*Defined in [api/src/base/Decorate.ts:140](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L140)*

**Type parameters:**

▪ **K**: *InterfaceTypes*

**Parameters:**

Name | Type |
------ | ------ |
`type` | K |
`...params` | any[] |

**Returns:** *InterfaceRegistry[K]*

___

###  injectMetadata

▸ **injectMetadata**(`metadata`: Metadata, `fromEmpty?`: undefined | false | true): *void*

*Defined in [api/src/base/Decorate.ts:151](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L151)*

**Parameters:**

Name | Type |
------ | ------ |
`metadata` | Metadata |
`fromEmpty?` | undefined &#124; false &#124; true |

**Returns:** *void*

___

###  off

▸ **off**(`type`: ApiInterfaceEvents, `handler`: function): *this*

*Inherited from [Init](_base_init_.init.md).[off](_base_init_.init.md#off)*

*Defined in [api/src/base/Events.ts:62](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Events.ts#L62)*

**`description`** Remove the given eventemitter handler

**`example`** 
<BR>

```javascript
const handler = (): void => {
 console.log('Connected !);
};

// Start listening
api.on('connected', handler);

// Stop listening
api.off('connected', handler);
```

**Parameters:**

▪ **type**: *ApiInterfaceEvents*

The type of event the callback was attached to. Available events are `connected`, `disconnected`, `ready` and `error`

▪ **handler**: *function*

The callback to unregister.

▸ (...`args`: any[]): *any*

**Parameters:**

Name | Type |
------ | ------ |
`...args` | any[] |

**Returns:** *this*

___

###  on

▸ **on**(`type`: ApiInterfaceEvents, `handler`: function): *this*

*Inherited from [Init](_base_init_.init.md).[on](_base_init_.init.md#on)*

*Defined in [api/src/base/Events.ts:35](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Events.ts#L35)*

**`description`** Attach an eventemitter handler to listen to a specific event

**`example`** 
<BR>

```javascript
api.on('connected', (): void => {
  console.log('API has been connected to the endpoint');
});

api.on('disconnected', (): void => {
  console.log('API has been disconnected from the endpoint');
});
```

**Parameters:**

▪ **type**: *ApiInterfaceEvents*

The type of event to listen to. Available events are `connected`, `disconnected`, `ready` and `error`

▪ **handler**: *function*

The callback to be called when the event fires. Depending on the event type, it could fire with additional arguments.

▸ (...`args`: any[]): *any*

**Parameters:**

Name | Type |
------ | ------ |
`...args` | any[] |

**Returns:** *this*

___

###  once

▸ **once**(`type`: ApiInterfaceEvents, `handler`: function): *this*

*Inherited from [Init](_base_init_.init.md).[once](_base_init_.init.md#once)*

*Defined in [api/src/base/Events.ts:87](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Events.ts#L87)*

**`description`** Attach an one-time eventemitter handler to listen to a specific event

**`example`** 
<BR>

```javascript
api.once('connected', (): void => {
  console.log('API has been connected to the endpoint');
});

api.once('disconnected', (): void => {
  console.log('API has been disconnected from the endpoint');
});
```

**Parameters:**

▪ **type**: *ApiInterfaceEvents*

The type of event to listen to. Available events are `connected`, `disconnected`, `ready` and `error`

▪ **handler**: *function*

The callback to be called when the event fires. Depending on the event type, it could fire with additional arguments.

▸ (...`args`: any[]): *any*

**Parameters:**

Name | Type |
------ | ------ |
`...args` | any[] |

**Returns:** *this*

___

### `Abstract` registerTypes

▸ **registerTypes**(`types?`: RegistryTypes): *void*

*Defined in [api/src/base/Decorate.ts:142](https://github.com/polkadot-js/api/blob/a35da085d/packages/api/src/base/Decorate.ts#L142)*

**Parameters:**

Name | Type |
------ | ------ |
`types?` | RegistryTypes |

**Returns:** *void*