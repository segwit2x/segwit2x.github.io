
# segwit2x Release Guide

Status:  WIP

## Introduction

This is a guide with migration and deployment recommendations for the
segwit2x rollout on the Bitcoin network.

## segwit2x overview

segwit2x is a multi-step network upgrade, that enables two major new
features:  Segregated Witness ([BIP
141](https://github.com/bitcoin/bips/blob/master/bip-0141.mediawiki) aka SegWit) and a base block size increase
to 2M.

This upgrade occurs in two phases:

1. SegWit activates via a soft fork upgrade ("SW SF").

2. 12,960 blocks later (~3 months), base block size increases to 2M.

The trigger for this cascade of events is at least 80% of Bitcoin
hashpower signals, via Bit-4 of the [BIP
9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki)
method, the intent to secure both segwit2x rules, SegWit + 2M.

In Phase 1, the specific method of SegWit activation is via the [BIP
91](https://github.com/bitcoin/bips/blob/master/bip-0091.mediawiki)
method:  336 blocks (~2 days) after 80% hashpower signals on Bit-4,
SegWit Bit-1 signaling will be required of all blocks.

Bit-4 also triggers Phase 2, a 3-month grace period following SegWit
activation, after which the base block size is increased to 2M.

## Phase 1 - Segregated Witness soft fork (SW SF)

### Phase 1 chain stability

**Although there cannot be any guarantees given about a live network
upgrade of a decentralized network, the mining hashpower is currently
securing a predictable set of consensus rules, implying that Bitcoin
users should see a stable and secure chain throughout the Phase 1
upgrade.**

Everyone is working to ensure that the network upgrade occurs without a
hitch; the ideal and likely outcome is a seamless upgrade to new SegWit
rules during the month of August.

### Phase 1 & 2 timing

As of this writing, Phase 1 orphaning is predicted to start on or before
Sun Jul 23 08:00:00 UTC 2017 (Sun Jul 23 04:00:00 EDT 2017).  That
timing will vary based on block production rate.  This is height 477120.

This places SegWit feature enablement in late August, with the
2M HF around November 20 (height 494784).

### Phase 1, User migration

#### Software compatibility

SegWit is backwards compatible.  It is designed as an opt-in upgrade for
P2P nodes and wallets.  It is only a required upgrade for miners, who
collectively secure and enforce the new, post-upgrade SegWit consensus
rules.

Generally speaking, **the average user does not need to take any
action** beyond educating themselves about the new ruleset and economics
associated with SegWit.  The chain and user coins should remain stable
and secure throughout the upgrade.

#### Node migration - bitcoind

The btc1 client is based on Bitcoin Core 0.14.1, and as such, has the
same migration needs as that software.  Upgrading from BC 0.14.0, 0.14.1
or 0.14.2 is simply a drop-in replacement of bitcoind and utilities.

Upgrading from BC 0.13.x or prior is covered by the respective release
notes stored
[here](https://github.com/bitcoin/bitcoin/blob/master/doc/release-notes/release-notes-0.14.0.md).

#### Miner migration - Phase 1 (SW SF)

This is already largely complete as of this writing.  Miners should
ensure they are well-connected to other miners.

We recommend moving immediately to bit-1 (BIP141) _and_ bit-4 (segwit2x)
signaling (0x20000012) in preparation for the orphaning of blocks that
do not signal bit-1.

## Phase 2 - 2M base block size hard fork (2M HF)

(coming soon)

### Audit results

### Per-software migration

### Migration strategies

### Mitigations


