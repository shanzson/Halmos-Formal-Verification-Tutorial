## Workshop Notes

## Getting started with Halmos
- [Halmos github](https://github.com/a16z/halmos/tree/main)
- [Halmos Examples](https://github.com/a16z/halmos/blob/main/examples/README.md)

## Installation
A) Mac
1. Run the following command:
```
pip3 install halmos
```
2. Add exectable to PATH
3. Run the command `nano ~/.zshrc`
4. Add the following line at the end of the file.
`export PATH="$PATH:/Users/username/Library/Python/3.9/bin"`
Note: Replace the username with the appropriate username on your PC.
5. Save changes and then run `source ~/.zshrc`


## Running Halmos on [Simple examples](https://github.com/a16z/halmos/tree/main/examples/simple)
1) File: Example.t.sol 
- Run: `forge test --match-path test/Example.t.sol`
- Using Halmos: `halmos --function testTotalPriceBuggy`
2) DEI stablecoin backdoor
- https://twitter.com/adamb83024264/status/1654558408803250176
- [Etherscan Code](https://etherscan.deth.net/address/0x63c28e2ff796e1480eb9ac8c3c55dcb9ae7b3df6#code)
- Run: `halmos --function check_NoBackdoor`
- Function signature hash of burnFrom(address,uint256)


## Running on [Halmos Sandbox](https://github.com/karmacoma-eth/halmos-sandbox)
1) File: 2_powerOfTwo.t.sol (Underflow bug)
- `halmos --function test_isPowerOfTwo_fast_buggy --loop 256`
- `halmos --function test_isPowerOfTwo_fast_ok`
- `halmos --function test_isPowerOfTwo_fast_ok --loop 256`
- NOTE:  NOTE: `--loop 256` option needed for complete verification. Default loop is 2.
2) File: 4_average.t.sol (Overflow bug)
- `halmos --function test_averageIgnoreReverts`
- `halmos --function test_averageWithReverts`
3) File: 5_anycallLowLevel.t.sol (_transfer access control)
- `halmos --function test_anycallLowLevel`
- `halmos --function test_anycallLowLevelExplicit`
4) File: 13_callToSymbolicAddress.t.sol (sending ether)
- `halmos --function test_callToSymbolicAddress`
- `halmos 00function test_prankCallToSymbolicAddress`
5) File: 18_emptyCounterExample.t.sol (assert false)
- `halmos --function test_emptyCounterExample`
6) File: 29_twoStepOwnershipTransfer.t.sol (function selector)
- `forge test --match-path test/29_twoStepOwnershipTransfer.t.sol`
- `halmos --function check_stateful_invariant`

## Useful Commands
- `halmos --function`
- `halmos --solver-timeout-assertion 0`

## Important points
- Like fuzz tests, any input combinations that don't satisfy the assume() conditions are disregarded. 
- Won't work with compiler versions less than 0.8.0. A custom assertion is needed in case you want it to work.



