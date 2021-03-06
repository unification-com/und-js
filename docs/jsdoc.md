## Modules

<dl>
<dt><a href="#module_client">client</a></dt>
<dd></dd>
<dt><a href="#module_crypto">crypto</a></dt>
<dd></dd>
<dt><a href="#amino.module_encode">encode</a></dt>
<dd></dd>
<dt><a href="#module_utils">utils</a></dt>
<dd></dd>
</dl>

## Constants

<dl>
<dt><a href="#checkNumber">checkNumber</a></dt>
<dd><p>validate the input number.</p>
</dd>
<dt><a href="#checkCoins">checkCoins</a></dt>
<dd><p>basic validation of coins</p>
</dd>
</dl>

<a name="module_client"></a>

## client

* [client](#module_client)
    * [.UndClient](#module_client.UndClient)
        * [new exports.UndClient(server, broadcastMode)](#new_module_client.UndClient_new)
        * [.initChain()](#module_client.UndClient+initChain) ⇒ <code>Promise</code>
        * [.setPrivateKey(privateKey, localOnly)](#module_client.UndClient+setPrivateKey) ⇒ <code>Promise</code>
        * [.setBroadcastMode(broadcastMode)](#module_client.UndClient+setBroadcastMode)
        * [.setAccountNumber(accountNumber)](#module_client.UndClient+setAccountNumber)
        * [.setClientNameHeader(clientNameHeader)](#module_client.UndClient+setClientNameHeader) ⇒ <code>UndClient</code>
        * [.setSigningDelegate(delegate, ledgerMode)](#module_client.UndClient+setSigningDelegate) ⇒ <code>UndClient</code>
        * [.setBroadcastDelegate(delegate)](#module_client.UndClient+setBroadcastDelegate) ⇒ <code>UndClient</code>
        * [.useDefaultSigningDelegate()](#module_client.UndClient+useDefaultSigningDelegate) ⇒ <code>UndClient</code>
        * [.useLedgerSigningDelegate(acc, ts, localOnly)](#module_client.UndClient+useLedgerSigningDelegate) ⇒ <code>UndClient</code>
        * [.confirmLedgerAddress()](#module_client.UndClient+confirmLedgerAddress) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.useDefaultBroadcastDelegate()](#module_client.UndClient+useDefaultBroadcastDelegate) ⇒ <code>UndClient</code>
        * [.transferUnd(toAddress, amount, fee, denom, fromAddress, memo, sequence)](#module_client.UndClient+transferUnd) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.raiseEnterprisePO(amount, fee, denom, fromAddress, memo, sequence)](#module_client.UndClient+raiseEnterprisePO) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.registerBeacon(moniker, name, fromAddress, gas, memo, sequence)](#module_client.UndClient+registerBeacon) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.recordBeaconTimestamp(beacon_id, hash, submit_time, fromAddress, gas, memo, sequence)](#module_client.UndClient+recordBeaconTimestamp) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.registerWRKChain(moniker, base_type, name, genesis, fromAddress, gas, memo, sequence)](#module_client.UndClient+registerWRKChain) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.recordWRKChainBlock(wrkchain_id, height, blockhash, parenthash, hash1, hash2, hash3, fromAddress, gas, memo, sequence)](#module_client.UndClient+recordWRKChainBlock) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.delegate(validator, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+delegate) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.undelegate(validator, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+undelegate) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.redelegate(validatorFrom, validatorTo, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+redelegate) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.modifyWithdrawAddress(withdrawAddress, fee, delegator, memo, sequence)](#module_client.UndClient+modifyWithdrawAddress) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.withdrawDelegationReward(validator, fee, delegator, memo, sequence)](#module_client.UndClient+withdrawDelegationReward) ⇒ <code>Promise.&lt;\*&gt;</code>
        * [.sendTransaction(signedTx)](#module_client.UndClient+sendTransaction) ⇒ <code>Promise</code>
        * [.sendRawTransaction(signedBz)](#module_client.UndClient+sendRawTransaction) ⇒ <code>Promise</code>
        * [.getBeaconParams()](#module_client.UndClient+getBeaconParams) ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
        * [.getWRKChainParams()](#module_client.UndClient+getWRKChainParams) ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
        * [.getAccount(address)](#module_client.UndClient+getAccount) ⇒ <code>Promise</code>
        * [.getBalance(address)](#module_client.UndClient+getBalance) ⇒ <code>Promise</code>
        * [.getEnterpriseLocked(address)](#module_client.UndClient+getEnterpriseLocked) ⇒ <code>Promise</code>
        * [.getTransactions(address, page, limit)](#module_client.UndClient+getTransactions) ⇒ <code>Promise</code>
        * [.getTransactionsReceived(address, page, limit)](#module_client.UndClient+getTransactionsReceived) ⇒ <code>Promise</code>
        * [.getFilteredTransactions(filters, page, limit)](#module_client.UndClient+getFilteredTransactions) ⇒ <code>Promise</code>
        * [.getTx(hash)](#module_client.UndClient+getTx) ⇒ <code>Promise</code>
        * [.getEnteprisePos(address, page, limit)](#module_client.UndClient+getEnteprisePos) ⇒ <code>Promise</code>
        * [.getDelegations(address, valAddress)](#module_client.UndClient+getDelegations) ⇒ <code>Promise</code>
        * [.getUnbondingDelegations(address, valAddress)](#module_client.UndClient+getUnbondingDelegations) ⇒ <code>Promise</code>
        * [.getBondedValidators(address, valAddress)](#module_client.UndClient+getBondedValidators) ⇒ <code>Promise</code>
        * [.getDelegatorRewards(address, valAddress)](#module_client.UndClient+getDelegatorRewards) ⇒ <code>Promise</code>
        * [.getDelegatorWithdrawAddress(address)](#module_client.UndClient+getDelegatorWithdrawAddress) ⇒ <code>Promise</code>
        * [.getValidators(status, page, limit, valAddress)](#module_client.UndClient+getValidators) ⇒ <code>Promise</code>
        * [.getValidatorDelegations(valAddress)](#module_client.UndClient+getValidatorDelegations) ⇒ <code>Promise</code>
        * [.getValidatorUnbondingDelegations(valAddress)](#module_client.UndClient+getValidatorUnbondingDelegations) ⇒ <code>Promise</code>
        * [.getRedelegations(delAddress, valSrcAddress, valDestAddress)](#module_client.UndClient+getRedelegations) ⇒ <code>Promise</code>
        * [.getValidatorDistributionInfo(valAddress)](#module_client.UndClient+getValidatorDistributionInfo) ⇒ <code>Promise</code>
        * [.getValidatorDistributionOutstandingRewards(valAddress)](#module_client.UndClient+getValidatorDistributionOutstandingRewards) ⇒ <code>Promise</code>
        * [.getValidatorDistributionRewards(valAddress)](#module_client.UndClient+getValidatorDistributionRewards) ⇒ <code>Promise</code>
        * [.getTotalSupply()](#module_client.UndClient+getTotalSupply) ⇒ <code>Promise</code>
        * [.getIsAddressEntWhitelisted(address)](#module_client.UndClient+getIsAddressEntWhitelisted) ⇒ <code>Promise</code>
        * [.createAccount()](#module_client.UndClient+createAccount) ⇒ <code>object</code>
        * [.createAccountWithKeystore(password)](#module_client.UndClient+createAccountWithKeystore)
        * [.createAccountWithMneomnic()](#module_client.UndClient+createAccountWithMneomnic) ⇒ <code>object</code>
        * [.recoverAccountFromKeystore(keystore, password)](#module_client.UndClient+recoverAccountFromKeystore)
        * [.recoverAccountFromMnemonic(mneomnic)](#module_client.UndClient+recoverAccountFromMnemonic)
        * [.recoverAccountFromPrivateKey(privateKey)](#module_client.UndClient+recoverAccountFromPrivateKey)
        * [.checkAddress(address, prefix)](#module_client.UndClient+checkAddress) ⇒ <code>Boolean</code>
        * [.getClientKeyAddress()](#module_client.UndClient+getClientKeyAddress) ⇒ <code>String</code>
    * [.DefaultSigningDelegate](#module_client.DefaultSigningDelegate) ⇒ <code>Transaction</code>
    * [.LedgerSigningDelegate](#module_client.LedgerSigningDelegate) ⇒ <code>Transaction</code>
    * [.DefaultBroadcastDelegate](#module_client.DefaultBroadcastDelegate)

<a name="module_client.UndClient"></a>

### client.UndClient
The und Mainchain client.

**Kind**: static class of [<code>client</code>](#module_client)  

* [.UndClient](#module_client.UndClient)
    * [new exports.UndClient(server, broadcastMode)](#new_module_client.UndClient_new)
    * [.initChain()](#module_client.UndClient+initChain) ⇒ <code>Promise</code>
    * [.setPrivateKey(privateKey, localOnly)](#module_client.UndClient+setPrivateKey) ⇒ <code>Promise</code>
    * [.setBroadcastMode(broadcastMode)](#module_client.UndClient+setBroadcastMode)
    * [.setAccountNumber(accountNumber)](#module_client.UndClient+setAccountNumber)
    * [.setClientNameHeader(clientNameHeader)](#module_client.UndClient+setClientNameHeader) ⇒ <code>UndClient</code>
    * [.setSigningDelegate(delegate, ledgerMode)](#module_client.UndClient+setSigningDelegate) ⇒ <code>UndClient</code>
    * [.setBroadcastDelegate(delegate)](#module_client.UndClient+setBroadcastDelegate) ⇒ <code>UndClient</code>
    * [.useDefaultSigningDelegate()](#module_client.UndClient+useDefaultSigningDelegate) ⇒ <code>UndClient</code>
    * [.useLedgerSigningDelegate(acc, ts, localOnly)](#module_client.UndClient+useLedgerSigningDelegate) ⇒ <code>UndClient</code>
    * [.confirmLedgerAddress()](#module_client.UndClient+confirmLedgerAddress) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.useDefaultBroadcastDelegate()](#module_client.UndClient+useDefaultBroadcastDelegate) ⇒ <code>UndClient</code>
    * [.transferUnd(toAddress, amount, fee, denom, fromAddress, memo, sequence)](#module_client.UndClient+transferUnd) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.raiseEnterprisePO(amount, fee, denom, fromAddress, memo, sequence)](#module_client.UndClient+raiseEnterprisePO) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.registerBeacon(moniker, name, fromAddress, gas, memo, sequence)](#module_client.UndClient+registerBeacon) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.recordBeaconTimestamp(beacon_id, hash, submit_time, fromAddress, gas, memo, sequence)](#module_client.UndClient+recordBeaconTimestamp) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.registerWRKChain(moniker, base_type, name, genesis, fromAddress, gas, memo, sequence)](#module_client.UndClient+registerWRKChain) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.recordWRKChainBlock(wrkchain_id, height, blockhash, parenthash, hash1, hash2, hash3, fromAddress, gas, memo, sequence)](#module_client.UndClient+recordWRKChainBlock) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.delegate(validator, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+delegate) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.undelegate(validator, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+undelegate) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.redelegate(validatorFrom, validatorTo, amount, fee, denom, delegator, memo, sequence)](#module_client.UndClient+redelegate) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.modifyWithdrawAddress(withdrawAddress, fee, delegator, memo, sequence)](#module_client.UndClient+modifyWithdrawAddress) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.withdrawDelegationReward(validator, fee, delegator, memo, sequence)](#module_client.UndClient+withdrawDelegationReward) ⇒ <code>Promise.&lt;\*&gt;</code>
    * [.sendTransaction(signedTx)](#module_client.UndClient+sendTransaction) ⇒ <code>Promise</code>
    * [.sendRawTransaction(signedBz)](#module_client.UndClient+sendRawTransaction) ⇒ <code>Promise</code>
    * [.getBeaconParams()](#module_client.UndClient+getBeaconParams) ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
    * [.getWRKChainParams()](#module_client.UndClient+getWRKChainParams) ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
    * [.getAccount(address)](#module_client.UndClient+getAccount) ⇒ <code>Promise</code>
    * [.getBalance(address)](#module_client.UndClient+getBalance) ⇒ <code>Promise</code>
    * [.getEnterpriseLocked(address)](#module_client.UndClient+getEnterpriseLocked) ⇒ <code>Promise</code>
    * [.getTransactions(address, page, limit)](#module_client.UndClient+getTransactions) ⇒ <code>Promise</code>
    * [.getTransactionsReceived(address, page, limit)](#module_client.UndClient+getTransactionsReceived) ⇒ <code>Promise</code>
    * [.getFilteredTransactions(filters, page, limit)](#module_client.UndClient+getFilteredTransactions) ⇒ <code>Promise</code>
    * [.getTx(hash)](#module_client.UndClient+getTx) ⇒ <code>Promise</code>
    * [.getEnteprisePos(address, page, limit)](#module_client.UndClient+getEnteprisePos) ⇒ <code>Promise</code>
    * [.getDelegations(address, valAddress)](#module_client.UndClient+getDelegations) ⇒ <code>Promise</code>
    * [.getUnbondingDelegations(address, valAddress)](#module_client.UndClient+getUnbondingDelegations) ⇒ <code>Promise</code>
    * [.getBondedValidators(address, valAddress)](#module_client.UndClient+getBondedValidators) ⇒ <code>Promise</code>
    * [.getDelegatorRewards(address, valAddress)](#module_client.UndClient+getDelegatorRewards) ⇒ <code>Promise</code>
    * [.getDelegatorWithdrawAddress(address)](#module_client.UndClient+getDelegatorWithdrawAddress) ⇒ <code>Promise</code>
    * [.getValidators(status, page, limit, valAddress)](#module_client.UndClient+getValidators) ⇒ <code>Promise</code>
    * [.getValidatorDelegations(valAddress)](#module_client.UndClient+getValidatorDelegations) ⇒ <code>Promise</code>
    * [.getValidatorUnbondingDelegations(valAddress)](#module_client.UndClient+getValidatorUnbondingDelegations) ⇒ <code>Promise</code>
    * [.getRedelegations(delAddress, valSrcAddress, valDestAddress)](#module_client.UndClient+getRedelegations) ⇒ <code>Promise</code>
    * [.getValidatorDistributionInfo(valAddress)](#module_client.UndClient+getValidatorDistributionInfo) ⇒ <code>Promise</code>
    * [.getValidatorDistributionOutstandingRewards(valAddress)](#module_client.UndClient+getValidatorDistributionOutstandingRewards) ⇒ <code>Promise</code>
    * [.getValidatorDistributionRewards(valAddress)](#module_client.UndClient+getValidatorDistributionRewards) ⇒ <code>Promise</code>
    * [.getTotalSupply()](#module_client.UndClient+getTotalSupply) ⇒ <code>Promise</code>
    * [.getIsAddressEntWhitelisted(address)](#module_client.UndClient+getIsAddressEntWhitelisted) ⇒ <code>Promise</code>
    * [.createAccount()](#module_client.UndClient+createAccount) ⇒ <code>object</code>
    * [.createAccountWithKeystore(password)](#module_client.UndClient+createAccountWithKeystore)
    * [.createAccountWithMneomnic()](#module_client.UndClient+createAccountWithMneomnic) ⇒ <code>object</code>
    * [.recoverAccountFromKeystore(keystore, password)](#module_client.UndClient+recoverAccountFromKeystore)
    * [.recoverAccountFromMnemonic(mneomnic)](#module_client.UndClient+recoverAccountFromMnemonic)
    * [.recoverAccountFromPrivateKey(privateKey)](#module_client.UndClient+recoverAccountFromPrivateKey)
    * [.checkAddress(address, prefix)](#module_client.UndClient+checkAddress) ⇒ <code>Boolean</code>
    * [.getClientKeyAddress()](#module_client.UndClient+getClientKeyAddress) ⇒ <code>String</code>

<a name="new_module_client.UndClient_new"></a>

#### new exports.UndClient(server, broadcastMode)

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| server | <code>String</code> |  | und Mainchain public url |
| broadcastMode | <code>String</code> | <code>sync</code> | sync = wait for checkTx, async = send and forget (faster but less guarantees), block = wait for block to process (default sync) |

<a name="module_client.UndClient+initChain"></a>

#### undClient.initChain() ⇒ <code>Promise</code>
Initialize the client with the chain's ID. Asynchronous.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
<a name="module_client.UndClient+setPrivateKey"></a>

#### undClient.setPrivateKey(privateKey, localOnly) ⇒ <code>Promise</code>
Sets the client's private key for calls made by this client. Asynchronous.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| privateKey | <code>string</code> |  | the private key hexstring |
| localOnly | <code>boolean</code> | <code>false</code> | set this to true if you will supply an account_number yourself via `setAccountNumber`. Warning: You must do that if you set this to true! |

<a name="module_client.UndClient+setBroadcastMode"></a>

#### undClient.setBroadcastMode(broadcastMode)
Set the mode for broadcasting a Tx

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Description |
| --- | --- | --- |
| broadcastMode | <code>String</code> | sync = wait for checkTx, async = send and forget (faster but less guarantees), block = wait for block to process (default sync) |

<a name="module_client.UndClient+setAccountNumber"></a>

#### undClient.setAccountNumber(accountNumber)
Sets the client's account number.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type |
| --- | --- |
| accountNumber | <code>boolean</code> | 

<a name="module_client.UndClient+setClientNameHeader"></a>

#### undClient.setClientNameHeader(clientNameHeader) ⇒ <code>UndClient</code>
Sets an optional clientName for HTTP headers

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  

| Param | Type |
| --- | --- |
| clientNameHeader | <code>String</code> | 

<a name="module_client.UndClient+setSigningDelegate"></a>

#### undClient.setSigningDelegate(delegate, ledgerMode) ⇒ <code>UndClient</code>
Sets the signing delegate (for wallet integrations).

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  

| Param | Type | Default |
| --- | --- | --- |
| delegate | <code>function</code> |  | 
| ledgerMode | <code>boolean</code> | <code>false</code> | 

<a name="module_client.UndClient+setBroadcastDelegate"></a>

#### undClient.setBroadcastDelegate(delegate) ⇒ <code>UndClient</code>
Sets the broadcast delegate (for wallet integrations).

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  

| Param | Type |
| --- | --- |
| delegate | <code>function</code> | 

<a name="module_client.UndClient+useDefaultSigningDelegate"></a>

#### undClient.useDefaultSigningDelegate() ⇒ <code>UndClient</code>
Applies the default signing delegate.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  
<a name="module_client.UndClient+useLedgerSigningDelegate"></a>

#### undClient.useLedgerSigningDelegate(acc, ts, localOnly) ⇒ <code>UndClient</code>
Applies the Ledger device signing delegate. Internally assigns the wallet
address used by the SDK to the respective HD wallet path's address.
For unit testing, the Node-HID transport can be passed instead of a string

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  

| Param | Type | Default |
| --- | --- | --- |
| acc | <code>Number</code> | <code>0</code> | 
| ts | <code>String</code> \| <code>Transport</code> | <code>WebUSB</code> | 
| localOnly | <code>boolean</code> | <code>false</code> | 

<a name="module_client.UndClient+confirmLedgerAddress"></a>

#### undClient.confirmLedgerAddress() ⇒ <code>Promise.&lt;\*&gt;</code>
Asks the user to view and confirm the wallet address on the Ledger device
that is currently being used by the SDK

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise.&lt;\*&gt;</code> - String containing bech32 address for external comparison  
<a name="module_client.UndClient+useDefaultBroadcastDelegate"></a>

#### undClient.useDefaultBroadcastDelegate() ⇒ <code>UndClient</code>
Applies the default broadcast delegate.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>UndClient</code> - this instance (for chaining)  
<a name="module_client.UndClient+transferUnd"></a>

#### undClient.transferUnd(toAddress, amount, fee, denom, fromAddress, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Transfer FUND to an address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| toAddress | <code>String</code> |  |  |
| amount | <code>Number</code> |  |  |
| fee | <code>Object</code> |  |  |
| denom | <code>String</code> | <code>nund</code> | optional denom |
| fromAddress | <code>String</code> |  | optional fromAddress |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+raiseEnterprisePO"></a>

#### undClient.raiseEnterprisePO(amount, fee, denom, fromAddress, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Raise an Enterprise FUND Purchase Order

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| amount | <code>Number</code> |  |  |
| fee | <code>Object</code> |  |  |
| denom | <code>String</code> | <code>nund</code> | optional denom |
| fromAddress | <code>String</code> |  | optional fromAddress |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+registerBeacon"></a>

#### undClient.registerBeacon(moniker, name, fromAddress, gas, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Register a BEACON

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| moniker | <code>String</code> |  | moniker |
| name | <code>String</code> |  | name optional name |
| fromAddress | <code>String</code> |  | fromAddress |
| gas | <code>Number</code> | <code>100000</code> | gas optional gas |
| memo | <code>String</code> |  | memo optional memo |
| sequence | <code>Number</code> | <code></code> | sequence optional sequence |

<a name="module_client.UndClient+recordBeaconTimestamp"></a>

#### undClient.recordBeaconTimestamp(beacon_id, hash, submit_time, fromAddress, gas, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Submit a BEACON timestamp

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| beacon_id | <code>Number</code> |  | beacon_id |
| hash | <code>String</code> |  | hash |
| submit_time | <code>Number</code> |  | submit_time |
| fromAddress | <code>String</code> |  | fromAddress |
| gas | <code>Number</code> | <code>100000</code> | gas optional gas |
| memo | <code>String</code> |  | memo optional memo |
| sequence | <code>Number</code> | <code></code> | sequence optional sequence |

<a name="module_client.UndClient+registerWRKChain"></a>

#### undClient.registerWRKChain(moniker, base_type, name, genesis, fromAddress, gas, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Register a WRKChain

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| moniker | <code>String</code> |  | moniker |
| base_type | <code>String</code> |  | base_type optional base_type |
| name | <code>String</code> |  | name optional name |
| genesis | <code>String</code> |  | genesis optional genesis |
| fromAddress | <code>String</code> |  | fromAddress |
| gas | <code>Number</code> | <code>100000</code> | gas optional gas |
| memo | <code>String</code> |  | memo optional memo |
| sequence | <code>Number</code> | <code></code> | sequence optional sequence |

<a name="module_client.UndClient+recordWRKChainBlock"></a>

#### undClient.recordWRKChainBlock(wrkchain_id, height, blockhash, parenthash, hash1, hash2, hash3, fromAddress, gas, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Submit WRKChain block header hashes

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| wrkchain_id | <code>Number</code> |  | wrkchain_id |
| height | <code>String</code> |  | height |
| blockhash | <code>String</code> |  | blockhash |
| parenthash | <code>String</code> |  | parenthash optional parenthash |
| hash1 | <code>String</code> |  | hash1 optional hash1 |
| hash2 | <code>String</code> |  | hash2 optional hash2 |
| hash3 | <code>String</code> |  | hash3 optional hash3 |
| fromAddress | <code>String</code> |  | fromAddress |
| gas | <code>Number</code> | <code>120000</code> | gas optional gas |
| memo | <code>String</code> |  | memo optional memo |
| sequence | <code>Number</code> | <code></code> | sequence optional sequence |

<a name="module_client.UndClient+delegate"></a>

#### undClient.delegate(validator, amount, fee, denom, delegator, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Delegate FUND to a validator

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| validator | <code>String</code> |  |  |
| amount | <code>Number</code> |  |  |
| fee | <code>Object</code> |  |  |
| denom | <code>String</code> | <code>nund</code> | optional denom |
| delegator | <code>String</code> |  | optional delegator |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+undelegate"></a>

#### undClient.undelegate(validator, amount, fee, denom, delegator, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Undelegate FUND from a validator

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| validator | <code>String</code> |  |  |
| amount | <code>Number</code> |  |  |
| fee | <code>Object</code> |  |  |
| denom | <code>String</code> | <code>nund</code> | optional denom |
| delegator | <code>String</code> |  | optional delegator |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+redelegate"></a>

#### undClient.redelegate(validatorFrom, validatorTo, amount, fee, denom, delegator, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Redelegate FUND from one validator to another

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| validatorFrom | <code>String</code> |  |  |
| validatorTo | <code>String</code> |  |  |
| amount | <code>Number</code> |  |  |
| fee | <code>Object</code> |  |  |
| denom | <code>String</code> | <code>nund</code> | optional denom |
| delegator | <code>String</code> |  | optional delegator |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+modifyWithdrawAddress"></a>

#### undClient.modifyWithdrawAddress(withdrawAddress, fee, delegator, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| withdrawAddress | <code>String</code> |  |  |
| fee | <code>Object</code> |  |  |
| delegator | <code>String</code> |  | optional delegator |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+withdrawDelegationReward"></a>

#### undClient.withdrawDelegationReward(validator, fee, delegator, memo, sequence) ⇒ <code>Promise.&lt;\*&gt;</code>
Withdraw Delegator rewards

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| validator | <code>String</code> |  |  |
| fee | <code>Object</code> |  |  |
| delegator | <code>String</code> |  | optional delegator |
| memo | <code>String</code> |  | optional memo |
| sequence | <code>Number</code> | <code></code> | optional sequence |

<a name="module_client.UndClient+sendTransaction"></a>

#### undClient.sendTransaction(signedTx) ⇒ <code>Promise</code>
Broadcast a transaction to the blockchain.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with response (success or fail)  

| Param | Type | Description |
| --- | --- | --- |
| signedTx | <code>String</code> | signed Transaction object |

<a name="module_client.UndClient+sendRawTransaction"></a>

#### undClient.sendRawTransaction(signedBz) ⇒ <code>Promise</code>
Broadcast a raw transaction to the blockchain.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with response (success or fail)  

| Param | Type | Description |
| --- | --- | --- |
| signedBz | <code>String</code> | signed and serialized raw transaction |

<a name="module_client.UndClient+getBeaconParams"></a>

#### undClient.getBeaconParams() ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
get BEACON params

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
<a name="module_client.UndClient+getWRKChainParams"></a>

#### undClient.getWRKChainParams() ⇒ <code>Promise.&lt;({result: {error: \*}, status: number}\|{result: \*, status: \*}\|void)&gt;</code>
get WRKChain params

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
<a name="module_client.UndClient+getAccount"></a>

#### undClient.getAccount(address) ⇒ <code>Promise</code>
get account

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type |
| --- | --- |
| address | <code>String</code> | 

<a name="module_client.UndClient+getBalance"></a>

#### undClient.getBalance(address) ⇒ <code>Promise</code>
get balances

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |

<a name="module_client.UndClient+getEnterpriseLocked"></a>

#### undClient.getEnterpriseLocked(address) ⇒ <code>Promise</code>
get enteprise locked FUND

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |

<a name="module_client.UndClient+getTransactions"></a>

#### undClient.getTransactions(address, page, limit) ⇒ <code>Promise</code>
get transactions for an account

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| address | <code>String</code> |  | optional address |
| page | <code>Number</code> | <code>1</code> | page number, default 1 |
| limit | <code>Number</code> | <code>100</code> | number of results per page, default 100, max 100 |

<a name="module_client.UndClient+getTransactionsReceived"></a>

#### undClient.getTransactionsReceived(address, page, limit) ⇒ <code>Promise</code>
Get transactions received by an account - specifically, FUND transfers sent to the address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| address | <code>String</code> |  | optional address |
| page | <code>Number</code> | <code>1</code> | page number, default 1 |
| limit | <code>Number</code> | <code>100</code> | number of results per page, default 100, max 100 |

<a name="module_client.UndClient+getFilteredTransactions"></a>

#### undClient.getFilteredTransactions(filters, page, limit) ⇒ <code>Promise</code>
Get Transactions based on arbitrary filters. Filters must be passed as an array of objects. Each
object must be in the format { 'key': 'the_key', 'val': 'the_val' }
for example:

[
  {
    'key': 'message.sender',
    'val': 'und1x8pl6wzqf9atkm77ymc5vn5dnpl5xytmn200xy'
  },
  {
   'key': 'message.action',
   'val': 'register_wrkchain'
  },
]

will generate the query string:

massage.sender=und1x8pl6wzqf9atkm77ymc5vn5dnpl5xytmn200xy&message.action=register_wrkchain

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| filters | <code>Array</code> |  | an array of filter objects |
| page | <code>Number</code> | <code>1</code> | page number, default 1 |
| limit | <code>Number</code> | <code>100</code> | number of results per page, default 100, max 100 |

<a name="module_client.UndClient+getTx"></a>

#### undClient.getTx(hash) ⇒ <code>Promise</code>
get transaction

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| hash | <code>String</code> | the transaction hash |

<a name="module_client.UndClient+getEnteprisePos"></a>

#### undClient.getEnteprisePos(address, page, limit) ⇒ <code>Promise</code>
get enterprise purchase orders for account

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| address | <code>String</code> |  | optional address |
| page | <code>Number</code> | <code>1</code> | optional page |
| limit | <code>Number</code> | <code>100</code> | optional limit |

<a name="module_client.UndClient+getDelegations"></a>

#### undClient.getDelegations(address, valAddress) ⇒ <code>Promise</code>
get delegations for address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |
| valAddress | <code>String</code> | optional Bech32 operator address |

<a name="module_client.UndClient+getUnbondingDelegations"></a>

#### undClient.getUnbondingDelegations(address, valAddress) ⇒ <code>Promise</code>
get unbonding delegations for address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional Bech32 address |
| valAddress | <code>String</code> | optional Bech32 operator address |

<a name="module_client.UndClient+getBondedValidators"></a>

#### undClient.getBondedValidators(address, valAddress) ⇒ <code>Promise</code>
get bonded validators for delegator address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |
| valAddress | <code>String</code> | optional Bech32 operator address |

<a name="module_client.UndClient+getDelegatorRewards"></a>

#### undClient.getDelegatorRewards(address, valAddress) ⇒ <code>Promise</code>
get delegator address's rewards

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |
| valAddress | <code>String</code> | optional Bech32 operator address |

<a name="module_client.UndClient+getDelegatorWithdrawAddress"></a>

#### undClient.getDelegatorWithdrawAddress(address) ⇒ <code>Promise</code>
get delegator's current withdraw address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>String</code> | optional address |

<a name="module_client.UndClient+getValidators"></a>

#### undClient.getValidators(status, page, limit, valAddress) ⇒ <code>Promise</code>
get a list of current validators based on filters

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| status | <code>String</code> | <code>bonded</code> | optional status. one of bonded, unbonded, unbonding. Default bonded |
| page | <code>Number</code> | <code>1</code> | optional page |
| limit | <code>Number</code> | <code>100</code> | optional limit |
| valAddress | <code>String</code> |  | optional Bech32 operator address |

<a name="module_client.UndClient+getValidatorDelegations"></a>

#### undClient.getValidatorDelegations(valAddress) ⇒ <code>Promise</code>
get a validator's bonded delegations

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type |
| --- | --- |
| valAddress | <code>String</code> | 

<a name="module_client.UndClient+getValidatorUnbondingDelegations"></a>

#### undClient.getValidatorUnbondingDelegations(valAddress) ⇒ <code>Promise</code>
get a validator's unbonding delegations

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| valAddress | <code>String</code> | bech32 operator address |

<a name="module_client.UndClient+getRedelegations"></a>

#### undClient.getRedelegations(delAddress, valSrcAddress, valDestAddress) ⇒ <code>Promise</code>
get redelegations, with optional filters

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| delAddress | <code>String</code> | optional delAddress Bech32 address |
| valSrcAddress | <code>String</code> | optional valSrcAddress Bech32 operator address |
| valDestAddress | <code>String</code> | optional valDestAddress Bech32 operator address |

<a name="module_client.UndClient+getValidatorDistributionInfo"></a>

#### undClient.getValidatorDistributionInfo(valAddress) ⇒ <code>Promise</code>
get distribution information for a given validator's operator address

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| valAddress | <code>String</code> | bech32 operator address |

<a name="module_client.UndClient+getValidatorDistributionOutstandingRewards"></a>

#### undClient.getValidatorDistributionOutstandingRewards(valAddress) ⇒ <code>Promise</code>
get Fee distribution outstanding rewards of a single validator

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| valAddress | <code>String</code> | bech32 operator address |

<a name="module_client.UndClient+getValidatorDistributionRewards"></a>

#### undClient.getValidatorDistributionRewards(valAddress) ⇒ <code>Promise</code>
get Commission and self-delegation rewards of a single validator

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type | Description |
| --- | --- | --- |
| valAddress | <code>String</code> | bech32 operator address |

<a name="module_client.UndClient+getTotalSupply"></a>

#### undClient.getTotalSupply() ⇒ <code>Promise</code>
get total supply of FUND

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  
<a name="module_client.UndClient+getIsAddressEntWhitelisted"></a>

#### undClient.getIsAddressEntWhitelisted(address) ⇒ <code>Promise</code>
check is given address is able to raise Enterprise purchase orders

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>Promise</code> - resolves with http response  

| Param | Type |
| --- | --- |
| address | <code>String</code> | 

<a name="module_client.UndClient+createAccount"></a>

#### undClient.createAccount() ⇒ <code>object</code>
Creates a private key and returns it and its address.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>object</code> - the private key and address in an object.
{
 address,
 privateKey
}  
<a name="module_client.UndClient+createAccountWithKeystore"></a>

#### undClient.createAccountWithKeystore(password)
Creates an account keystore object, and returns the private key and address.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Description |
| --- | --- | --- |
| password | <code>String</code> | {  privateKey,  address,  keystore } |

<a name="module_client.UndClient+createAccountWithMneomnic"></a>

#### undClient.createAccountWithMneomnic() ⇒ <code>object</code>
Creates an account from mnemonic seed phrase.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
**Returns**: <code>object</code> - {
 privateKey,
 address,
 mnemonic
}  
<a name="module_client.UndClient+recoverAccountFromKeystore"></a>

#### undClient.recoverAccountFromKeystore(keystore, password)
Recovers an account from a keystore object.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Description |
| --- | --- | --- |
| keystore | <code>object</code> | object. |
| password | <code>string</code> | password. { privateKey, address } |

<a name="module_client.UndClient+recoverAccountFromMnemonic"></a>

#### undClient.recoverAccountFromMnemonic(mneomnic)
Recovers an account from a mnemonic seed phrase.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Description |
| --- | --- | --- |
| mneomnic | <code>String</code> | { privateKey, address } |

<a name="module_client.UndClient+recoverAccountFromPrivateKey"></a>

#### undClient.recoverAccountFromPrivateKey(privateKey)
Recovers an account using private key.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type | Description |
| --- | --- | --- |
| privateKey | <code>String</code> | { privateKey, address } |

<a name="module_client.UndClient+checkAddress"></a>

#### undClient.checkAddress(address, prefix) ⇒ <code>Boolean</code>
Validates an address.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  

| Param | Type |
| --- | --- |
| address | <code>String</code> | 
| prefix | <code>String</code> | 

<a name="module_client.UndClient+getClientKeyAddress"></a>

#### undClient.getClientKeyAddress() ⇒ <code>String</code>
Returns the address for the current account if setPrivateKey has been called on this client.

**Kind**: instance method of [<code>UndClient</code>](#module_client.UndClient)  
<a name="module_client.DefaultSigningDelegate"></a>

### client.DefaultSigningDelegate ⇒ <code>Transaction</code>
The default signing delegate which uses the local private key.

**Kind**: static constant of [<code>client</code>](#module_client)  

| Param | Type | Description |
| --- | --- | --- |
| tx | <code>Transaction</code> | the transaction |
| signMsg | <code>Object</code> | the canonical sign bytes for the msg |

<a name="module_client.LedgerSigningDelegate"></a>

### client.LedgerSigningDelegate ⇒ <code>Transaction</code>
The Ledger signing delegate which uses the Ledger app over USB.

**Kind**: static constant of [<code>client</code>](#module_client)  

| Param | Type | Description |
| --- | --- | --- |
| tx | <code>Transaction</code> | the transaction |

<a name="module_client.DefaultBroadcastDelegate"></a>

### client.DefaultBroadcastDelegate
The default broadcast delegate which immediately broadcasts a transaction.

**Kind**: static constant of [<code>client</code>](#module_client)  

| Param | Type | Description |
| --- | --- | --- |
| signedTx | <code>Transaction</code> | the signed transaction |

<a name="module_crypto"></a>

## crypto

* [crypto](#module_crypto)
    * [.decodeAddress](#module_crypto.decodeAddress)
    * [.checkAddress](#module_crypto.checkAddress) ⇒ <code>boolean</code>
    * [.encodeAddress](#module_crypto.encodeAddress)
    * [.generatePrivateKey](#module_crypto.generatePrivateKey) ⇒ <code>string</code>
    * [.generateRandomArray](#module_crypto.generateRandomArray) ⇒ <code>ArrayBuffer</code>
    * [.getPublicKey](#module_crypto.getPublicKey) ⇒ <code>Elliptic.PublicKey</code>
    * [.getPublicKeyFromPrivateKey](#module_crypto.getPublicKeyFromPrivateKey) ⇒ <code>string</code>
    * [.generatePubKey](#module_crypto.generatePubKey) ⇒ <code>Elliptic.PublicKey</code>
    * [.generatePubKeyCompressed](#module_crypto.generatePubKeyCompressed) ⇒ <code>\*</code>
    * [.getAddressFromPublicKey](#module_crypto.getAddressFromPublicKey)
    * [.getAddressFromPrivateKey](#module_crypto.getAddressFromPrivateKey)
    * [.generateSignature](#module_crypto.generateSignature) ⇒ <code>Buffer</code>
    * [.verifySignature](#module_crypto.verifySignature) ⇒ <code>Buffer</code>
    * [.generateKeyStore](#module_crypto.generateKeyStore) ⇒ <code>object</code>
    * [.getPrivateKeyFromKeyStore](#module_crypto.getPrivateKeyFromKeyStore)
    * [.generateMnemonic](#module_crypto.generateMnemonic)
    * [.validateMnemonic](#module_crypto.validateMnemonic) ⇒ <code>bool</code>
    * [.getPrivateKeyFromMnemonic](#module_crypto.getPrivateKeyFromMnemonic) ⇒ <code>string</code>

<a name="module_crypto.decodeAddress"></a>

### crypto.decodeAddress
Decodes an address in bech32 format.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>string</code> | the bech32 address to decode |

<a name="module_crypto.checkAddress"></a>

### crypto.checkAddress ⇒ <code>boolean</code>
Checks whether an address is valid.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| address | <code>string</code> | the bech32 address to decode |
| hrp | <code>string</code> | the prefix to check for the bech32 address |

<a name="module_crypto.encodeAddress"></a>

### crypto.encodeAddress
Encodes an address from input data bytes.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>string</code> | the public key to encode |
| prefix | <code>\*</code> | the address prefix |
| type | <code>\*</code> | the output type (default: hex) |

<a name="module_crypto.generatePrivateKey"></a>

### crypto.generatePrivateKey ⇒ <code>string</code>
Generates 32 bytes of random entropy

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>string</code> - entropy bytes hexstring  

| Param | Type | Description |
| --- | --- | --- |
| len | <code>number</code> | output length (default: 32 bytes) |

<a name="module_crypto.generateRandomArray"></a>

### crypto.generateRandomArray ⇒ <code>ArrayBuffer</code>
Generates an arrayBuffer filled with random bits.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| length | <code>number</code> | Length of buffer. |

<a name="module_crypto.getPublicKey"></a>

### crypto.getPublicKey ⇒ <code>Elliptic.PublicKey</code>
**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>Elliptic.PublicKey</code> - public key hexstring  

| Param | Type | Description |
| --- | --- | --- |
| publicKey | <code>string</code> | Encoded public key |

<a name="module_crypto.getPublicKeyFromPrivateKey"></a>

### crypto.getPublicKeyFromPrivateKey ⇒ <code>string</code>
Calculates the public key from a given private key.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>string</code> - public key hexstring  

| Param | Type | Description |
| --- | --- | --- |
| privateKeyHex | <code>string</code> | the private key hexstring |

<a name="module_crypto.generatePubKey"></a>

### crypto.generatePubKey ⇒ <code>Elliptic.PublicKey</code>
PubKey performs the point-scalar multiplication from the privKey on the
generator point to get the pubkey.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>Elliptic.PublicKey</code> - PubKey  

| Param | Type |
| --- | --- |
| privateKey | <code>Buffer</code> | 

<a name="module_crypto.generatePubKeyCompressed"></a>

### crypto.generatePubKeyCompressed ⇒ <code>\*</code>
generatePubKeyCompressed performs the point-scalar multiplication from the
privKey on the generator point to get the pubkey.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param |
| --- |
| privateKey | 

<a name="module_crypto.getAddressFromPublicKey"></a>

### crypto.getAddressFromPublicKey
Gets an address from a public key hex.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| publicKeyHex | <code>string</code> | the public key hexstring |
| prefix | <code>string</code> | the address prefix |

<a name="module_crypto.getAddressFromPrivateKey"></a>

### crypto.getAddressFromPrivateKey
Gets an address from a private key.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| privateKeyHex | <code>string</code> | the private key hexstring |

<a name="module_crypto.generateSignature"></a>

### crypto.generateSignature ⇒ <code>Buffer</code>
Generates a signature (64 byte <r,s>) for a transaction based on given private key.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>Buffer</code> - Signature. Does not include tx.  

| Param | Type | Description |
| --- | --- | --- |
| signBytesHex | <code>string</code> | Unsigned transaction sign bytes hexstring. |
| privateKey | <code>string</code> \| <code>Buffer</code> | The private key. |

<a name="module_crypto.verifySignature"></a>

### crypto.verifySignature ⇒ <code>Buffer</code>
Verifies a signature (64 byte <r,s>) given the sign bytes and public key.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>Buffer</code> - Signature. Does not include tx.  

| Param | Type | Description |
| --- | --- | --- |
| sigHex | <code>string</code> | The signature hexstring. |
| signBytesHex | <code>string</code> | Unsigned transaction sign bytes hexstring. |
| publicKeyHex | <code>string</code> | The public key. |

<a name="module_crypto.generateKeyStore"></a>

### crypto.generateKeyStore ⇒ <code>object</code>
Generates a keystore object (web3 secret storage format) given a private key to store and a password.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>object</code> - the keystore object.  

| Param | Type | Description |
| --- | --- | --- |
| privateKeyHex | <code>string</code> | the private key hexstring. |
| password | <code>string</code> | the password. |

<a name="module_crypto.getPrivateKeyFromKeyStore"></a>

### crypto.getPrivateKeyFromKeyStore
Gets a private key from a keystore given its password.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  

| Param | Type | Description |
| --- | --- | --- |
| keystore | <code>string</code> | the keystore in json format |
| password | <code>string</code> | the password. |

<a name="module_crypto.generateMnemonic"></a>

### crypto.generateMnemonic
Generates mnemonic phrase words using random entropy.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
<a name="module_crypto.validateMnemonic"></a>

### crypto.validateMnemonic ⇒ <code>bool</code>
Validates mnemonic phrase words.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>bool</code> - validation result  

| Param | Type | Description |
| --- | --- | --- |
| mnemonic | <code>string</code> | the mnemonic phrase words |

<a name="module_crypto.getPrivateKeyFromMnemonic"></a>

### crypto.getPrivateKeyFromMnemonic ⇒ <code>string</code>
Get a private key from mnemonic words.

**Kind**: static constant of [<code>crypto</code>](#module_crypto)  
**Returns**: <code>string</code> - hexstring  

| Param | Type | Description |
| --- | --- | --- |
| mnemonic | <code>string</code> | the mnemonic phrase words |
| derive | <code>Boolean</code> | derive a private key using the default HD path (default: true) |
| index | <code>number</code> | the bip44 address index (default: 0) |
| password | <code>string</code> | according to bip39 |

<a name="amino.module_encode"></a>

## encode

* [encode](#amino.module_encode)
    * [.encodeNumber](#amino.module_encode.encodeNumber)
    * [.encodeBool](#amino.module_encode.encodeBool)
    * [.encodeString](#amino.module_encode.encodeString)
    * [.encodeTime](#amino.module_encode.encodeTime)
    * [.convertObjectToSignBytes](#amino.module_encode.convertObjectToSignBytes) ⇒ <code>Buffer</code>
    * [.marshalBinary](#amino.module_encode.marshalBinary)
    * [.marshalBinaryBare](#amino.module_encode.marshalBinaryBare)
    * [.encodeBinary](#amino.module_encode.encodeBinary) ⇒ <code>Buffer</code>
    * [.encodeBinaryByteArray](#amino.module_encode.encodeBinaryByteArray) ⇒ <code>Buffer</code>
    * [.encodeObjectBinary](#amino.module_encode.encodeObjectBinary) ⇒ <code>Buffer</code>
    * [.encodeArrayBinary](#amino.module_encode.encodeArrayBinary) ⇒ <code>Buffer</code>

<a name="amino.module_encode.encodeNumber"></a>

### encode.encodeNumber
encode number

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param |
| --- |
| num | 

<a name="amino.module_encode.encodeBool"></a>

### encode.encodeBool
encode bool

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param |
| --- |
| b | 

<a name="amino.module_encode.encodeString"></a>

### encode.encodeString
encode string

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param |
| --- |
| str | 

<a name="amino.module_encode.encodeTime"></a>

### encode.encodeTime
encode time

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param |
| --- |
| value | 

<a name="amino.module_encode.convertObjectToSignBytes"></a>

### encode.convertObjectToSignBytes ⇒ <code>Buffer</code>
**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  
**Returns**: <code>Buffer</code> - bytes  

| Param | Type | Description |
| --- | --- | --- |
| obj | <code>object</code> | - |

<a name="amino.module_encode.marshalBinary"></a>

### encode.marshalBinary
js amino MarshalBinary

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param | Type |
| --- | --- |
| obj | <code>Object</code> | 

<a name="amino.module_encode.marshalBinaryBare"></a>

### encode.marshalBinaryBare
js amino MarshalBinaryBare

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  

| Param | Type |
| --- | --- |
| obj | <code>Object</code> | 

<a name="amino.module_encode.encodeBinary"></a>

### encode.encodeBinary ⇒ <code>Buffer</code>
This is the main entrypoint for encoding all types in binary form.

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  
**Returns**: <code>Buffer</code> - binary of object.  

| Param | Type | Description |
| --- | --- | --- |
| js | <code>\*</code> | data type (not null, not undefined) |
| field | <code>Number</code> | index of object |
| isByteLenPrefix | <code>Boolean</code> |  |

<a name="amino.module_encode.encodeBinaryByteArray"></a>

### encode.encodeBinaryByteArray ⇒ <code>Buffer</code>
prefixed with bytes length

**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  
**Returns**: <code>Buffer</code> - with bytes length prefixed  

| Param | Type |
| --- | --- |
| bytes | <code>Buffer</code> | 

<a name="amino.module_encode.encodeObjectBinary"></a>

### encode.encodeObjectBinary ⇒ <code>Buffer</code>
**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  
**Returns**: <code>Buffer</code> - with bytes length prefixed  

| Param | Type |
| --- | --- |
| obj | <code>Object</code> | 

<a name="amino.module_encode.encodeArrayBinary"></a>

### encode.encodeArrayBinary ⇒ <code>Buffer</code>
**Kind**: static constant of [<code>encode</code>](#amino.module_encode)  
**Returns**: <code>Buffer</code> - bytes of array  

| Param | Type | Description |
| --- | --- | --- |
| fieldNum | <code>Number</code> | object field index |
| arr | <code>Array</code> |  |
| isByteLenPrefix | <code>Boolean</code> |  |

<a name="module_utils"></a>

## utils

* [utils](#module_utils)
    * [.ab2str](#module_utils.ab2str) ⇒ <code>string</code>
    * [.str2ab](#module_utils.str2ab) ⇒ <code>arrayBuffer</code>
    * [.hexstring2ab](#module_utils.hexstring2ab) ⇒ <code>Array.&lt;number&gt;</code>
    * [.ab2hexstring](#module_utils.ab2hexstring) ⇒ <code>string</code>
    * [.str2hexstring](#module_utils.str2hexstring) ⇒ <code>string</code>
    * [.hexstring2str](#module_utils.hexstring2str) ⇒ <code>string</code>
    * [.int2hex](#module_utils.int2hex) ⇒ <code>string</code>
    * [.num2hexstring](#module_utils.num2hexstring) ⇒ <code>string</code>
    * [.num2VarInt](#module_utils.num2VarInt) ⇒ <code>string</code>
    * [.hexXor](#module_utils.hexXor) ⇒ <code>string</code>
    * [.reverseArray](#module_utils.reverseArray) ⇒ <code>Uint8Array</code>
    * [.reverseHex](#module_utils.reverseHex) ⇒ <code>string</code>
    * [.isHex](#module_utils.isHex) ⇒ <code>boolean</code>
    * [.ensureHex](#module_utils.ensureHex)
    * [.sha256ripemd160](#module_utils.sha256ripemd160) ⇒ <code>string</code>
    * [.sha256](#module_utils.sha256) ⇒ <code>string</code>
    * [.sha3](#module_utils.sha3) ⇒ <code>string</code>
    * [.calculateRandomNumberHash](#module_utils.calculateRandomNumberHash) ⇒ <code>string</code>
    * [.checkBroadcastMode](#module_utils.checkBroadcastMode) ⇒ <code>string</code>

<a name="module_utils.ab2str"></a>

### utils.ab2str ⇒ <code>string</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - ASCII string  

| Param | Type |
| --- | --- |
| buf | <code>arrayBuffer</code> | 

<a name="module_utils.str2ab"></a>

### utils.str2ab ⇒ <code>arrayBuffer</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | ASCII string |

<a name="module_utils.hexstring2ab"></a>

### utils.hexstring2ab ⇒ <code>Array.&lt;number&gt;</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | HEX string |

<a name="module_utils.ab2hexstring"></a>

### utils.ab2hexstring ⇒ <code>string</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - HEX string  

| Param | Type |
| --- | --- |
| arr | <code>arrayBuffer</code> | 

<a name="module_utils.str2hexstring"></a>

### utils.str2hexstring ⇒ <code>string</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - HEX string  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | ASCII string |

<a name="module_utils.hexstring2str"></a>

### utils.hexstring2str ⇒ <code>string</code>
**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - ASCII string  

| Param | Type | Description |
| --- | --- | --- |
| hexstring | <code>string</code> | HEX string |

<a name="module_utils.int2hex"></a>

### utils.int2hex ⇒ <code>string</code>
convert an integer to big endian hex and add leading zeros

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type |
| --- | --- |
| num | <code>Number</code> | 

<a name="module_utils.num2hexstring"></a>

### utils.num2hexstring ⇒ <code>string</code>
Converts a number to a big endian hexstring of a suitable size, optionally little endian

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type | Description |
| --- | --- | --- |
| num | <code>Number</code> |  |
| size | <code>Number</code> | The required size in bytes, eg 1 for Uint8, 2 for Uint16. Defaults to 1. |
| littleEndian | <code>Boolean</code> | Encode the hex in little endian form |

<a name="module_utils.num2VarInt"></a>

### utils.num2VarInt ⇒ <code>string</code>
Converts a number to a variable length Int. Used for array length header

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - hexstring of the variable Int.  

| Param | Type | Description |
| --- | --- | --- |
| num | <code>Number</code> | The number |

<a name="module_utils.hexXor"></a>

### utils.hexXor ⇒ <code>string</code>
XORs two hexstrings

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - XOR output as a HEX string  

| Param | Type | Description |
| --- | --- | --- |
| str1 | <code>string</code> | HEX string |
| str2 | <code>string</code> | HEX string |

<a name="module_utils.reverseArray"></a>

### utils.reverseArray ⇒ <code>Uint8Array</code>
Reverses an array. Accepts arrayBuffer.

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type |
| --- | --- |
| arr | <code>Array</code> | 

<a name="module_utils.reverseHex"></a>

### utils.reverseHex ⇒ <code>string</code>
Reverses a HEX string, treating 2 chars as a byte.

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - HEX string reversed in 2s.  

| Param | Type | Description |
| --- | --- | --- |
| hex | <code>string</code> | HEX string |

**Example**  
```js
reverseHex('abcdef') = 'efcdab'
```
<a name="module_utils.isHex"></a>

### utils.isHex ⇒ <code>boolean</code>
Checks if input is a hexstring. Empty string is considered a hexstring.

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type |
| --- | --- |
| str | <code>string</code> | 

**Example**  
```js
isHex('0101') = true
isHex('') = true
isHex('0x01') = false
```
<a name="module_utils.ensureHex"></a>

### utils.ensureHex
Throws an error if input is not hexstring.

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type |
| --- | --- |
| str | <code>string</code> | 

<a name="module_utils.sha256ripemd160"></a>

### utils.sha256ripemd160 ⇒ <code>string</code>
Computes a SHA256 followed by a RIPEMD160.

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - hash output  

| Param | Type | Description |
| --- | --- | --- |
| hex | <code>string</code> | message to hash |

<a name="module_utils.sha256"></a>

### utils.sha256 ⇒ <code>string</code>
Computes a single SHA256 digest.

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - hash output  

| Param | Type | Description |
| --- | --- | --- |
| hex | <code>string</code> | message to hash |

<a name="module_utils.sha3"></a>

### utils.sha3 ⇒ <code>string</code>
Computes a single SHA3 (Keccak) digest.

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - hash output  

| Param | Type | Description |
| --- | --- | --- |
| hex | <code>string</code> | message to hash |

<a name="module_utils.calculateRandomNumberHash"></a>

### utils.calculateRandomNumberHash ⇒ <code>string</code>
Computes sha256 of random number and timestamp

**Kind**: static constant of [<code>utils</code>](#module_utils)  
**Returns**: <code>string</code> - sha256 result  

| Param | Type |
| --- | --- |
| randomNumber | <code>String</code> | 
| timestamp | <code>Number</code> | 

<a name="module_utils.checkBroadcastMode"></a>

### utils.checkBroadcastMode ⇒ <code>string</code>
Ensure Broadcast Mode is only one of sync, async or block

**Kind**: static constant of [<code>utils</code>](#module_utils)  

| Param | Type |
| --- | --- |
| broadcastMode | <code>string</code> | 

<a name="checkNumber"></a>

## checkNumber
validate the input number.

**Kind**: global constant  

| Param | Type |
| --- | --- |
| value | <code>Number</code> | 

<a name="checkCoins"></a>

## checkCoins
basic validation of coins

**Kind**: global constant  

| Param | Type |
| --- | --- |
| coins | <code>Array</code> | 

