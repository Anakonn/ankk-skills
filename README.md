# ANKK Skills

Standard Agent Skills for ANKK user workflows:

- `ankk-analyze`: stored SNS performance, comparisons, coverage and recommendations.
- `ankk-publish`: approved content preparation, publishing/scheduling and final outcomes.

These skills require compatible ANKK **v2** MCP tools or CLI commands and user OAuth. They provide procedures, not authentication, new permissions or bundled credentials. They do not install the ANKK CLI or create a connector. Check the deployment's actual capabilities; this repository does not promise that a particular environment has every feature enabled.

## Installation

The release candidate `v0.1.0-rc.1` is published. Its remote discovery and project-scoped copy installation were verified with `skills@1.7.2`. This establishes installation, not Production availability or completed business-workflow acceptance.

To discover or install the current repository:

```sh
npx skills add Anakonn/ankk-skills --list
npx skills add Anakonn/ankk-skills --skill ankk-analyze --skill ankk-publish
```

Choose the target agent and project/global scope in the installer. Local development discovery uses `npx skills add ./ --list` from this repository. See the [official skills CLI](https://github.com/vercel-labs/skills) for options.

Releases use semantic Git tags. To install the verified release candidate:

```sh
npx skills add https://github.com/Anakonn/ankk-skills/tree/v0.1.0-rc.1 --skill ankk-analyze --skill ankk-publish
```

Do not use `owner/repo@tag` as an assumed Git-ref syntax: some source forms interpret the suffix as a skill name. Tag installation must be verified against the selected released ref. Published tags are immutable; later changes require a new release.

## Compatibility and releases

ANKK CLI 0.6.0 is published. Its public package installation, upgrade, OAuth login/logout and representative reads have been verified. The next Skills release, `v0.1.0`, is being prepared for this CLI and compatible v2 MCP tools. It adds connection-prerequisite guidance to publishing and optional stored comment/DM evidence to analysis. These Skill changes are not yet included in the published `v0.1.0-rc.1` tag. Actual capabilities depend on the deployed environment and your existing permissions. Connection changes, billing, replies and moderation require their own explicit approval.

Both skills target the public v2 business contract. Use current MCP input schemas or installed CLI help for parameters. `ankk-publish` needs media preparation, content publication and operation lookup; retries additionally require `contents_retry`. `ankk-analyze` needs brand/connection reads and analytics, with posts reads for supporting detail. UI cards are optional; structured results remain usable.

Before tagging a release, validate both skills, exercise realistic approval/uncertainty and missing-data scenarios, and verify discovery and installation with the official installer in an isolated directory. Record the tested installer/CLI versions and supported capabilities. Commit/push, tag publication and external distribution require repository-owner approval. A successful installation does not establish successful OAuth or business execution.
