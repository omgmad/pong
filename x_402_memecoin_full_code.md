// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Pong is ERC20, Ownable {
    constructor() ERC20("Pong", "PONG") Ownable(msg.sender) {
        _mint(msg.sender, 100_000_000 * 10 ** decimals()); // Premint 100 million tokens
    }

    // Optional mint function for owner (can be removed for fixed supply)
    function mint(address to, uint256 amount) external onlyOwner {
        _mint(to, amount);
    }
}

