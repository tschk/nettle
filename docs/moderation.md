# Moderation and abuse boundaries

Private chats and private groups have no central content moderation.

Public chatrooms have no protocol-level moderators.

Random matching uses reputation and abuse controls.

## User controls

Every client must support:

- block user
- reject request
- disconnect random match
- hide room event
- local keyword filters
- local media filters
- clear conversation locally

## Random matching controls

- reputation thresholds
- account age thresholds
- rate limits
- per-device quotas
- recent match suppression
- instant rematch prevention after abuse
- local and relay-level exclusion lists

## Reporting

A report system may be added for random matching.

Because content is end-to-end encrypted, reports must be user-initiated and
explicitly attach selected evidence.

Reports must not silently upload conversations.

## Public rooms

Relays may refuse to carry illegal or abusive content without changing room
identity. Clients choose relays and local filters.
