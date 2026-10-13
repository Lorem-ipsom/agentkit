---
name: eatemup-account-connector
description: Associate existing plugin accounts and skill manifests with the correct provider connection, scoped credentials, and database without publishing keys.
---
# EatEmUp Account-to-Skill Connector

## Objective
Discover available installed plugin tools, existing SKILL.md manifests, and provider account metadata. Match each skill to an authorized provider connection and database using stable provider IDs, account IDs, project IDs, and verified scopes. Never assume two accounts are the same because their names look similar.

## Procedure
1. Discover providers and their actual tool schemas. Separate available, installed, connected, and authorized states.
2. For each skill, parse name, description, tool dependencies, required scopes, provider, and expected database type.
3. Resolve a provider account only through authenticated provider metadata. Never scrape account secrets from chats or files.
4. Associate credentials by secret *reference* (environment variable or managed secret ID), not raw key value. Never log, commit, publish, or return tokens, mnemonics, private keys, or API keys.
5. Verify database identity using provider-native project/instance IDs, read-only metadata, and least-privilege connectivity checks. Do not automatically create tables, run migrations, or transfer data.
6. Emit a registry mapping skill ID -> provider -> verified account ID -> verified database ID -> required scopes -> secret reference -> connection status.
7. Require explicit approval for new OAuth grants, credential rotation, write operations, deployment, or transactions.
8. Keep the gateway deny-by-default; unauthenticated requests cannot invoke actions.

## AKCM / EatEmUp
Associate capability keywords as UTF-8 and ASCII when representable. EatEmUp routes verified skill identifiers only; it does not elevate privileges.

## Android
MacroDroid, AutoInput, and AutoTools skills generate reviewed setup recipes. They do not install apps, enable Accessibility, or execute on-device without separate user authorization.

## Registry format
Use JSON entries with: skill_id, provider_id, connection_status, account_ref, database_ref, scopes, secret_ref, last_verified, and provenance. Unknown values must be null, never guessed.
