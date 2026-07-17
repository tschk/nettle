# Private group chats

Creator-controlled private groups.

## Authority

Creator can:

- add / remove members
- rename group / change metadata
- close the group
- optionally transfer ownership later (not required in MVP)

### On-chain record (AD-23)

Group identity may be recorded on-chain as `group_id -> creator` (optional
metadata). Membership and messages stay off-chain. Chain record supports
discovery and ownership claims; encryption/membership still MLS off-chain.

## Membership events

Signed group events:

```text
group_created
group_member_added
group_member_removed
group_metadata_changed
group_closed
```

```mermaid
stateDiagram-v2
  [*] --> Open: group_created
  Open --> Open: member_added / removed / metadata
  Open --> Closed: group_closed
  Closed --> [*]
```

## Encryption

MLS or another reviewed group protocol.

A removed member must not decrypt future messages after membership epoch
change.

## History

Group history remains on member devices.

New members receive earlier history **only** if an existing member explicitly
transfers it.

Default: **no automatic pre-membership history**.
