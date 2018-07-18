# Neural_ERC20TokenBase

Base project structure to create ERC20 compatible Tokens with a total supply of 100.000.000 of Neural Tokens (NTKs).

This Token can be easily populated compiling the contract, copying the bytecode and using MEW (MyEtherWallet) or any other platform to deploy the Token contract. 

In order to deploy the contract, take into account the compiler version (the last one tested was 0.4.24+commit.e67f0147) and the optimisation flag (using Remix it can be found in Settings => General Settings => Enable optimisation. After the Contract bytecode has been deployed, in order to verify the code of the contract the original Contract that code and compiler settings will be need provided.

After the Tokens have been successfully created they can be used and sent using any ERC20 compatible wallet, such as MEW.

# ERC20 Specs

The ERC20 standard is used to generate the Tokens in a standard way.

The main interface populates:

* totalSupply(): returns the total supply of tokens, in this case 100.000.000 of NTK (used the total amount with the number of decimals to split the token, in this case 100.000.000 x 10^18 to have a big granularity of tokens.

* balanceOf(address tokenOwner): get the balance of that specific account

* transfer(address to, uint tokens): send the amount of tokens from the sender message to the addres "to"

* approve(address spender, uint tokens): allows the specified address to send tokens in the behalf of the current account message. Every time a transfer is performed from the "spender" they are reduced until be 0. When 0, no more tokens will be allowed to be send but this method can be called multiple times to allow more tokens to be sent. 

* transferFrom(address from, address to, uint tokens): sends tokens from account "from" to account "to" if they have been previously allowed by the approve() method and the maximum allowance of tokens has not yet been reached.

* allowance(address tokenOwner, address spender) : returns the amount of tokens that the spender account can send in the behalf of tokenOwner.

Events:

For future projects, we will listen for the events using JSON-RPC as we are interested in real-time events (coming soon!)

* Transfer(address indexed from, address indexed to, uint tokens): Triggered everytime tokens are transfered from account "fromt" to account "to".

* Approval(address indexed tokenOwner, address indexed spender, uint tokens): Triggeded when an approval of tokens is allowed from "tokenOwner" to "spender"
