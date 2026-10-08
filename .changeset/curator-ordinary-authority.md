---
'@mastra/core': patch
'@mastra/memory': patch
---

Subconscious curate now writes with the session's ordinary Knowledge authority. Every curator write tool goes through the Knowledge facade, which checks the resource and thread rungs' current grants and access epoch, so a curator can no longer place nodes in read-only structural scopes, keep writing after a grant is revoked, or bind mentions to nodes in the unvouched organization scope. `Knowledge` gains authorized `createNodeWithRecord()` and `replaceNodeRecords()` methods for these atomic writes. The curator can still write to the organization rung when the org grants the session `append` access; without such a grant, org writes are refused.
