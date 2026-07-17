# Coding agent instructions

1. Treat product docs as direction, not permission to invent cryptography.
2. Use reviewed cryptographic libraries only.
3. Keep blockchain code separate from messaging code.
4. Make all schemas versioned.
5. Write protocol test vectors before network integration.
6. Avoid permanent private message storage on relays.
7. Implement sender-side durable queues.
8. Make every network operation idempotent where possible.
9. Use structured tracing without logging plaintext or secret keys.
10. Add fuzzing for parsers and event verification.
11. Add integration tests with multiple clients and relays.
12. Keep transports pluggable.
13. Document every metadata leak.
14. Default to safe size and rate limits.
15. Prefer a CLI reference implementation before UI work.

## Parallelism

Docs and independent crate design can proceed in parallel.

Implementation still respects dependency edges:

```text
types / protocol / crypto
        ↓
identity / storage
        ↓
messaging / transport
        ↓
presence / relay
        ↓
rooms / groups / discovery / attachments / routing
```

Chain-runtime may develop in parallel behind `chain-client`.

## License

ISC. Do not add restrictive dependency licenses or telemetry without explicit
approval.
