## Workshop Notes

## Getting started with Halmos
- [Halmos github](https://github.com/a16z/halmos/tree/main)
- [Halmos Examples](https://github.com/a16z/halmos/blob/main/examples/README.md)

## Installation
A) Mac
1. 
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

## Running on [Halmos Sandbox](https://github.com/karmacoma-eth/halmos-sandbox
1) File: 2_powerOfTwo.t.sol (Underflow bug)
- `halmos --function test_isPowerOfTwo_fast_buggy --loop 256`
- `halmos --function test_isPowerOfTwo_fast_ok`
- `halmos --function test_isPowerOfTwo_fast_ok --loop 256`
- NOTE:  NOTE: `--loop 256` option needed for complete verification. Default loop is 2.
2) File: 4_average.t.sol (Overflow bug)
- `halmos --function test_averageIgnoreReverts`
- `halmos --function test_averageWithReverts`
3) File: 5_anycallLowLevel.t.sol (_transfer access control)
- 
```
halmos --function test_anycallLowLevelExplicit
```

## Useful Commands
- `halmos --function`
- `halmos --solver-timeout-assertion 0`

## Debugging common errors
- 


