# Smart Contract version flipstarter

Initial motivation: [solve the limit of ~650 pledges](https://bitcoincashresearch.org/t/p2sh-assurance-contract/720)
Additionally the smart contract version allows for automatic refunds at expiry and for stretch goals.

## V1

Solves the limit on the number of contributors to a campaign but does not allow for cancel-at-any-time.
When the campaign expires and everybody has to be refunded this can be automated and does not require intervention from the user.
Repo contains a version with and without stretch goals.

## V2

Uses the features of the Cashtoken upgrade which will activate May 2023 but are already usable on chipnet.
Solves the limit on the number of contributors to a campaign and also allows for cancel-at-any-time.
When the campaign expires and everybody has to be refunded this can be automated and does not require intervention from the user.
Canceling the pledghe before this time does require action on the part of the user.
Repo contains a version with and without stretch goals.

In some circumstances it might be preferable for pledges to be non-revokable until campaign expiry

## Alternative designs

Instead an interactive contract where all pledges are added to one cmpaign UTXO [there is an alternative design](https://read.cash/@emergent_reasons/flipstarter-research-a-simple-smart-contract-for-assurance-payments-884697fc) where each pledge is a separate P2SH UTX0, currently this design still faces a limit on the number of pledges (with native introspection this limit is probably close to the original limit of ~650 pledges) so it does not solve the limit on the number of participants but it allows for any wallet to make contributions to a campaign. [There a number of tradeoffs](https://bitcoincashresearch.org/t/p2sh-assurance-contract/720/19?u=mathieug) such as that it is hard to verify the total amount contributed, and related to this campaigns might have overfunding or forget about certain pledges. Additionally a campaign database crash might lead to the loss of funds if the pledges are not linked somehow.

With cashtokens the non-interactive design can also have an unlimited amount of contributors. It can not have the option to revoke the pledge at any time.  