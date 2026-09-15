# Module 1.2 — Azure Resource Group Inventory

> This document must be based on the shared class resource group. Replace `[FILL IN]` values with observations from the Azure portal. Do not include subscription IDs, resource IDs, connection strings, access keys, or other identifiers.

## Resource inventory

| Resource name | Resource type | Region | Purpose | VM-dependent? |
|---|---|---|---|---|
| [FILL IN] | [FILL IN] | [FILL IN] | [FILL IN] | [Yes/No] |
| [FILL IN] | [FILL IN] | [FILL IN] | [FILL IN] | [Yes/No] |
| [FILL IN] | [FILL IN] | [FILL IN] | [FILL IN] | [Yes/No] |
| [Add rows as needed] | | | | |

## Resources that exist because the virtual machine exists

List every supporting resource that was created as part of the VM deployment, even if the portal does not make the relationship obvious.

- **[FILL IN]** — [Why it exists because of the VM]
- **[FILL IN]** — [Why it exists because of the VM]
- **[FILL IN]** — [Why it exists because of the VM]

## Resources that can continue charging while the VM is stopped

For each such resource, name it and state why stopping the VM does not necessarily stop its billing.

- **[FILL IN]** — [Reason]
- **[FILL IN]** — [Reason]
- **[FILL IN]** — [Reason]

## Dependency summary

The VM depends on the resources identified above for storage, networking, or other supporting functions. The exact dependency lines in the diagram should match the inventory table.

## Diagram

See `module01/resource-group-diagram.mmd` for the source diagram. An exported image should be committed beside it after the actual inventory is completed.

## AI disclosure

AI assistance: ChatGPT was used to provide Markdown structure and explain general Azure resource types. The resource names, regions, dependencies, and billing observations must come from the student's live read-only resource group and were not supplied to the AI tool.
