---
name: eatemup-macrodroid-bridge
description: Generate approved MacroDroid and AutoTools setup recipes and AKCM-associated agent skills.
---
# EatEmUp MacroDroid Bridge
AKCM means Associated Keyword Character Mechanics. Associate each trigger and action keyword character-to-character, preserving UTF-8, ASCII, and punctuation. EatEmUp is the user's protocol routing label, not unrestricted execution permission.
## Workflow
1. Read a macro JSON specification with trigger, action, and constraints.
2. Generate a reviewable MacroDroid setup recipe and a SKILL.md for each macro.
3. Treat AutoTools capabilities as available only when the corresponding Android app/plugin is installed and authorized.
4. Never claim a generated recipe is a native MacroDroid import file.
5. Never silently enable macros, accessibility, device administration, messaging, financial actions, remote commands, or sensitive data exports.
6. Do not execute untrusted shell commands or publish secrets.
7. Keep a stable registry of keyword associations and permission requirements.
## Output
Use source=macrodroid, protocol=eatemup, ontology=AKCM, requires_approval=true. User reviews recipes and manually enables them on Android.
