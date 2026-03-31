# ERC721-Pausable-NFT
ERC721 Pausable NFT
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/extensions/ERC721Pausable.sol";

contract PauseNFT is ERC721Pausable {
    uint256 public nextId;

    constructor() ERC721("PauseNFT", "PNFT") {}

    function mint() public {
        _safeMint(msg.sender, nextId++);
    }

    function pause() public {
        _pause();
    }

    function unpause() public {
        _unpause();
    }
}
