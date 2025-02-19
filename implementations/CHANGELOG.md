# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

### [3.1.1](https://github.com/ERC725Alliance/ERC725/compare/v3.1.0...v3.1.1) (2022-06-07)

This minor release include the following two changes:

- `constants.sol` now include the `bytes4` selectors of the overloaded functions `setData(bytes32,bytes)` and `setData(bytes32[],bytes[])` from ERC725Y ([#126](https://github.com/ERC725Alliance/ERC725/issues/126)) ([a4e6b52](https://github.com/ERC725Alliance/ERC725/commit/a4e6b52f58a9abc781841017b963f31e99624e83))
- remove `Context` contract from `OwnableUnset` ( [#129](https://github.com/ERC725Alliance/ERC725/pull/129) )

## [3.1.0](https://github.com/ERC725Alliance/ERC725/compare/v3.0.3...v3.1.0) (2022-06-07)

### ⚠ BREAKING CHANGES

- remove `value` param in `DataChanged` event (#123)

### Features

- remove `value` param in `DataChanged` event ([#123](https://github.com/ERC725Alliance/ERC725/issues/123)) ([8794d16](https://github.com/ERC725Alliance/ERC725/commit/8794d16033fbfc97d3d26808fdcc6602abd4a6da))

## [3.0.3](https://www.npmjs.com/package/@erc725/smart-contracts/v/3.0.3) (2022-05-25)

- `ERC725X`: removed `owner()` check for operation delegatecall ([#119](https://github.com/ERC725Alliance/ERC725/pull/119))
- added custom `Initializable` contract for `ERC725XInitAbstract` and `ERC725YInitAbstract` ([#114](https://github.com/ERC725Alliance/ERC725/pull/114))

### Bug Fixes

- check that `_to == address(0)` (**zero-address**) in `ERC725X` when operation is CREATE or CREATE2 ([#112](https://github.com/ERC725Alliance/ERC725/pull/112))

---

## [3.0.2](https://www.npmjs.com/package/@erc725/smart-contracts/v/3.0.2) (2022-05-09)

### BREAKING CHANGE

- the `Executed` event in `ERC725X` use only the `bytes4` selector, instead of the full `bytes _data` ([#104](https://github.com/ERC725Alliance/ERC725/pull/104))

### Bug Fixes

- check that `_value == 0` in `ERC725X` when operation is STATICCALL or DELEGATECALL, as value cannot be transferred with these operation types ([#108](https://github.com/ERC725Alliance/ERC725/pull/108)) ([9fb6b1d](https://github.com/ERC725Alliance/ERC725/commit/9fb6b1d3b06fdefa5f4eafaf66e7b91e4ca14af9))
- change inheritance order from most base to most derived ([#107](https://github.com/ERC725Alliance/ERC725/pull/107)) ([70d3b67](https://github.com/ERC725Alliance/ERC725/commit/70d3b67af494e7a5f74ae033a7436f9766a1cb98))

---

## [3.0.1](https://www.npmjs.com/package/@erc725/smart-contracts/v/3.0.1) (2022-04-28)

- the `_setOwner(address)` function in `OwnableUnset` was changed from `private` to `internal` ([#103](https://github.com/ERC725Alliance/ERC725/pull/103))
- the contracts now implement the `supportsInterface(bytes4)` function via `ERC165` (previously `ERC165Storage`). This reduce gas deployment cost + save gas when calling `supportsInterface(bytes4)` function, as the interface IDs are nto read from the contract storage anymore but rather hardcoded inside the implementation function ([#96](https://github.com/ERC725Alliance/ERC725/pull/96))

### Bug Fixes

- in `ERC725X`, check the contract balance against the provided `_value` parameter, to ensure the contract has enough to transfer (this made the call revert silently before). ([PR #102](https://github.com/ERC725Alliance/ERC725/pull/102)) ([8a96bcc](https://github.com/ERC725Alliance/ERC725/commit/8a96bcc56e447ba8064630a59a04f33c9ec0c0dc))

---

## [3.0.0](https://www.npmjs.com/package/@erc725/smart-contracts/v/3.0.0) (2022-03-29)

- add [`constants.js`](https://github.com/ERC725Alliance/ERC725/blob/main/implementations/constants.**js**) file in the npm package. This file includes the `INTERFACE_ID` of ERC725X and ERC725Y + the different operation types used by ERC725X.

### BREAKING CHANGES

- getData and setData overloading ([#93](https://github.com/ERC725Alliance/ERC725/issues/93)) ([014c41e](https://github.com/ERC725Alliance/ERC725/commit/014c41e342db5b1e1c5880d5fd81a66841617529))

### Features

- `ERC725X` now handle custom revert error introduced in [solc 0.8.4](https://github.com/ethereum/solidity/releases/tag/v0.8.4) ([#86](https://github.com/ERC725Alliance/ERC725/pull/86))

### Bug Fixes

- mark initialize(...) as internal for onlyInitializing ([#88](https://github.com/ERC725Alliance/ERC725/issues/88)) ([2fd43ef](https://github.com/ERC725Alliance/ERC725/commit/2fd43ef09547202590f79c524470a174ca7bd60e))
- fix initializer re-entrancy issue from OZ ([#81](https://github.com/ERC725Alliance/ERC725/pull/81)), closes [#78](https://github.com/ERC725Alliance/ERC725/issues/78)

---

## [2.1.7](https://www.npmjs.com/package/@erc725/smart-contracts/v/2.1.7) (2021-12-20)

## [2.1.6](https://www.npmjs.com/package/@erc725/smart-contracts/v/2.1.6) (2021-12-13)

## [2.1.5](https://www.npmjs.com/package/@erc725/smart-contracts/v/2.1.5) (2021-12-06)

## [2.1.4](https://www.npmjs.com/package/@erc725/smart-contracts/v/2.1.4) (2021-11-17)

## [2.1.3](https://www.npmjs.com/package/@erc725/smart-contracts/v/2.1.3) (2021-11-12)
