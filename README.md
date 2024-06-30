This Solidity smart contract defines a basic ERC-20 token named `myToken`. Here's a brief explanation of its key components:

1. **Contract Initialization (`constructor`)**:
   - `owner`: This variable is initialized with the address that deploys the contract (`msg.sender`), effectively making them the owner.

2. **Public Variables**:
   - `name`: The name of the token ("Metacrafters").
   - `symbol`: The symbol of the token ("MTAC").
   - `totalSupply`: Tracks the total supply of tokens in circulation. Initialized to 0.

3. **Events**:
   - `Mint`: Triggered when new tokens are minted and assigned to an address.
   - `Burn`: Triggered when tokens are burned (removed from circulation).
   - `Transfer`: Triggered when tokens are transferred from one address to another.

4. **Error Handling**:
   - `InsufficientBalance`: Custom error that can be reverted to indicate insufficient balance during a burn operation.

5. **Mapping**:
   - `balances`: Maps addresses to their token balances.

6. **Modifiers**:
   - `onlyOwner`: A modifier that restricts access to functions to only the owner of the contract (`msg.sender == owner`).

7. **Functions**:
   - `mint`: Allows the owner to mint new tokens and assign them to a specified address.
   - `burn`: Allows the owner to burn (destroy) tokens from a specified address, with error handling for insufficient balances.
   - `transfer`: Allows any token holder to transfer tokens to another address, ensuring the sender has sufficient balance.

### Key Considerations:
- **Security**: The `onlyOwner` modifier restricts critical functions (`mint` and `burn`) to ensure they can only be executed by the contract owner.
- **Functionality**: The contract supports basic token operations (`transfer`, `mint`, `burn`) required for an ERC-20 token.
- **Events**: Events (`Mint`, `Burn`, `Transfer`) provide transparency for token minting, burning, and transfers.
- **Error Handling**: Includes a custom error (`InsufficientBalance`) for clear and explicit error messages during token burning.

This contract forms a foundational implementation of an ERC-20 token with basic functionalities and security measures to control token minting and burning operations.
