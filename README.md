# ChainID_Contracts
Ethereum ERC20 Token sale for the Veredictum anti-piracy platform on distributed technology.

www.veredictum.io

This contract is written in order to raise an inital fund of ether in exchange for ERC20 tokens which will have utility value upon the Veredictum platform.

All funds are held in the contract as escrow until the ICO is conditionally successful allowing for the funds to be removed into the fund wallet.

Contributors of a failed fund raising will be able claim a refund of the amount of ether they have contributed.

The fund raising period is from the configured start date upto 28 days. The contract may accept pre-funds from KYC'ed addresses in the period between deployment and the start date up to the limit of the maximum funding cap.

Non-KYC addresses may fund up to the juristictional regulated maximum equivilent of $10,000USD.

Bonus tokens will be generated at the following funding tranches per transaction.

Contributed	Bonus Tokens
$2,000,000	35%
$500,000	30%
$100,000	20%
$25,000	15%
$10,000	10%
$5,000	5%
The ICO fund raising has a minimum cap of $2,000,000USD and maximum of $20,000,000USD with a base conversion ratio of 3 VNT tokens per US dollar.

ETH/USD calculations are at the rate given at deployment.

The ICO will only be considered successful if the funds raised exceed the minimum cap and those funds have been swept to the FUND_WALLET.

Owners of an ICO which has raised minimum funds may call finalizeICO() before the end date is reached which sets icoSuccessful to true. No further ether deposits will be accepted by the contract.

ERC20 token transfers are prevented until the ICO is successful.

The ICO will be considered failed if the minimum cap has not been reach by the 29th day or the owner has aborted the ICO. In the event of a failed ICO, the ether contributed can be recovered unto the funders address using the refund(address) function. It may be called by anyone on the condition the fund has failed.

If a security issue arrises during the time of funding and up until funds are swept to the fund wallet, the owner can call abort(). This will force the ICO to fail and allow refunds to be enacted.
