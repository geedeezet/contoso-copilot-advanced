# Control map — GitHub Copilot in our organisation

Status: ✅ enforced or configured as noted · ⚠️ available but not set · ❓ unknown · 🔒 can't see (admin only)

Snapshot: VS Code Policy Diagnostics, 2026-11-18 09:48 UTC, on this device. The diagnostics do not establish enterprise-wide policy or cover remote agent hosts. Owners below are indicative and need confirmation.

| Layer | Control | Owner | Status |
|---|---|---|---|
| ① GitHub AI controls | Copilot features (chat, agents, cloud agent, code review) | GitHub admin (to confirm) | ❓ Not established by these diagnostics |
| ① GitHub AI controls | Model availability + "Default availability" for new models | GitHub admin (to confirm) | ❓ Not established by these diagnostics |
| ① GitHub AI controls | MCP servers in Copilot policy | GitHub admin (to confirm) | ❓ Not established by these diagnostics |
| ① GitHub AI controls | Content exclusion | GitHub admin (to confirm) | ❓ Not established by these diagnostics |
| ① GitHub AI controls | Audit log (agent actions) | GitHub admin (to confirm) | ❓ Audit configuration and coverage not established |
| ② Enterprise-managed settings | `permissions` / `sandbox` | Enterprise admin (to confirm) | ❓ Runtime settings not shown; no enterprise-required Agent Host sandbox active on this device |
| ② Enterprise-managed settings | Default `model` / `fusionTier` | Enterprise admin (to confirm) | ❓ Runtime settings not shown |
| ② Enterprise-managed settings | MCP allow / deny lists | Enterprise admin (to confirm) | ❓ Runtime settings not shown |
| ③ VS Code device policies | ChatAgentMode · ChatToolsAutoApprove · ChatMCP | Device / enterprise admin (to confirm) | ❓ Not listed among applied policies; effective values and other enforcement paths not shown |
| Repository | preToolUse guardrail hook (`.github/hooks/`) — Step 4 | me (this lab) | ⚠️ No repository-level `.github/hooks/` found in this workspace |
| Repository | Branch ruleset on `main` — Step 5 | me (this lab) | ❓ Cannot establish from local files |
| Repository | CI check `Test` (`.github/workflows/ci.yml`) | Repository maintainers (to confirm) | ✅ Job defined in the workflow; execution and required-check enforcement not verified |

## Diagnostic context

- Managed settings were received from the GitHub Server API; the account policy gate was inactive.
- Chat harness enforcement was **not enforced**. This does not establish whether other controls apply.
- The Agent Runtime snapshot was not included in the supplied diagnostics. VS Code policy values alone do not prove which runtime-owned settings are effective.
- The diagnostics report four Agent Host readiness items requiring verification: extra marketplaces, telemetry identity capture, telemetry headers, and telemetry protocol. These are not in themselves findings of failed enforcement.
- Verify GitHub controls and the `main` ruleset with the relevant administrators. Verify runtime-owned settings from the Agent Runtime snapshot and test relevant enforcement paths.
