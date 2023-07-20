# Trusted-Service-Interaction-Techniques-for-Cloud-Native-Architecture
Trusted Service Interaction Techniques for Cloud Native Architecture
pragma solidity ^0.8.0;

contract ReputationContract {
    struct User {
        uint reputationScore;
        uint totalTransactions;
    }

    mapping(address =&gt; User) public users;

    function updateReputation(address userAddress, uint reputationDelta) external {
        User storage user = users[userAddress];
        user.reputationScore += reputationDelta;
        user.totalTransactions += 1;
    }

    function getReputation(address userAddress) external view returns (uint) {
        return users[userAddress].reputationScore;
    }

    function getTotalTransactions(address userAddress) external view returns (uint) {
        return users[userAddress].totalTransactions;
    }
}
