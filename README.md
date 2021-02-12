# Pedersen commitment scheme

## Protocol

**Setup**

D = (Elliptic curve C, generator G, generator H)

This data should be generated by a trusted external party or the verifier, but NOT by
the committer. Or at least: The commiter can not know **log_G(H)**.

**Commiter**: 

Given D and a message m on C, commiter commits to m as follows:

*Commit phase*:
1. Picks a random scalar b that's smaller than the order of the group associated with C.
2. Makes public c = mG + bH

*Open phase*:
1. Makes public (m,b)

**Verifier**:

1. Given (c,m,b) checks that indeed c = mG + bH
