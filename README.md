# Blockchain Core Library

## Project Overview

This is a lightweight, pure Python implementation of core blockchain data structures and transaction processing mechanisms. The library provides essential components for blockchain simulation, educational purposes, and experimental blockchain development.

### Key Features
- Robust Block and Transaction Classes
- RLP (Recursive Length Prefix) Encoding Support
- Transaction Signing and Verification
- State Management with Merkle Trie
- Cryptographic Primitives Integration

## Installation

### Prerequisites
- Python 3.7+
- `pybitcointools` library
- `rlp` library

### Installation Methods
```bash
# Using pip (recommended)
pip install blockchain-core-library

# Alternatively, clone the repository
git clone https://github.com/yourusername/blockchain-core-library.git
cd blockchain-core-library
pip install -r requirements.txt
```

## API Reference

### Block Class (`blocks.py`)

#### Constructor
```python
Block(data=None)
```
- `data`: Optional hex-encoded or RLP-encoded block data
- Creates a block with transactions, state, and metadata

#### Methods
- `pay_fee(address, fee, tominer=True)`: Process transaction fees
- `get_nonce(address)`: Retrieve account nonce
- `get_balance(address)`: Get account balance
- `set_balance(address, balance)`: Set account balance
- `get_contract(address)`: Retrieve contract state
- `update_contract(address, contract)`: Update contract state
- `serialize()`: Convert block to RLP-encoded format
- `hash()`: Compute block hash

### Transaction Class (`transactions.py`)

#### Constructors
```python
Transaction(nonce, to, value, fee, data)
Transaction(serialized_data)
```
- Supports creating transactions from individual parameters or decoding existing transactions

#### Methods
- `parse(data)`: Decode transaction from RLP or hex data
- `sign(key)`: Sign transaction with private key
- `serialize()`: Convert transaction to RLP-encoded format
- `hex_serialize()`: Serialize transaction to hex
- `hash()`: Compute transaction hash

## Repository Structure
- `blocks.py`: Block processing and state management
- `transactions.py`: Transaction creation and signing
- `trie.py`: Merkle Trie implementation
- `rlp.py`: RLP encoding/decoding utilities
- `parser.py`: Additional parsing utilities
- `processblock.py`: Block processing logic

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

### Running Tests
```bash
python -m unittest discover tests/
```

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Disclaimer
This library is for educational and experimental purposes. Not recommended for production blockchain systems without extensive security audits.