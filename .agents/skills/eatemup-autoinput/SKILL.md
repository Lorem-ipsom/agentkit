---
name: eatemup-autoinput
description: Convert reviewed Android AutoInput UI interaction workflows into AKCM/EatEmUp skill recipes for MacroDroid.
---
# EatEmUp AutoInput Skill
Use AutoInput as an Android accessibility/UI interaction adapter. It requires the AutoInput application, Android Accessibility authorization, and user review. Never claim this skill itself installs or operates AutoInput remotely.

## Workflow
1. Receive a task with app package, expected screen, selector type, selector value, and desired action.
2. Associate task keywords with AKCM UTF-8/ASCII character mapping and route under EatEmUp.
3. Generate an AutoInput recipe for MacroDroid: trigger, constraints, UI Query, click/text/swipe action, timeout, and failure recovery.
4. Prefer resource ID and verified text selectors; avoid hardcoded screen coordinates.
5. Require confirmation before any macro is enabled on the device.

## Safety
Do not automate consent dialogs, security prompts, financial transactions, account recovery, permission grants, or credential entry. Never bypass lock screens or accessibility restrictions. Keep passwords, tokens, and private keys out of logs and generated files. Default to preview-only mode.

## Output
Provide JSON recipes and SKILL.md definitions. These are not native MacroDroid imports. Real execution requires installed and authorized Android components.
