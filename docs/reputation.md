# Reputation

Primarily for **random matching**.

Not a universal public social score.

## Inputs (possible)

- account age
- completed random conversations
- frequency of immediate disconnects
- peer blocks
- signed endorsements
- proof of established mutual relationships
- rate-limit compliance
- local trust lists

## Privacy

Do not put raw reports or detailed behavioural history on-chain.

Prefer signed credentials or local calculations:

```text
reputation_credential {
  subject_identity
  claim_type
  claim_value
  issued_at
  expires_at
  issuer
  signature
}
```

## Sybil resistance

Accounts free; usernames free but **max 1 owned per identity** (AD-10) →
cheap multi-wallet Sybil still possible, harder single-wallet hoarding.

Possible mechanisms:

- account age
- lightweight proof-of-work for match requests
- per-device quotas
- invitation graph weight
- rate limits
- optional refundable token deposits later
- relay-level abuse throttling

## First release

Use:

- account age
- per-device rate limits
- recent-match limits
- local block lists
- reputation from completed sessions

Exact formula remains an [open decision](open-decisions.md).
