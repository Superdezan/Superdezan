### Hi there 👋

<!--
**Superdezan/Superdezan** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on swisstronik
- 🌱 I’m currently learning coding
- 👯 I’m looking to collaborate on swisstronik
- 🤔 I’m looking for help with as
- 💬 Ask me about anything 
- 📫 How to reach me: hm
- 😄 Pronouns: superdezan
- ⚡ Fun fact: I really like worked as a dev
-->
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Register {
    string public github;
    address public owner;
    
    struct Referral {
        address referralAddress;
        string referralString;
    }
    
    Referral[] public referrals;
    
    constructor() {
        github = "superdezan";
        owner = 0xD9Ba01Fd9b3c9523094FfC476eF59181587ca267;
    }
    
    function addReferral(address _referralAddress, string memory _referralString) external {
        require(msg.sender == owner, "Only the owner can add referrals.");
        referrals.push(Referral(_referralAddress, _referralString));
    }
    
    function totalReferrals() public view returns (uint256) {
        return referrals.length;
    }
}
