# Infisical

## Source development guide

### Product and architecture

Secrets management with project environments, identity controls, integrations and audit capabilities.

Fastify/TypeScript backend, PostgreSQL/Knex persistence and BullMQ workers; React/Vite frontend; a partial Go backend rewrite in `backend-go/`. Docker Compose coordinates development services. Enterprise modules retain separate licensing.

### Requirements and local development

Docker Compose for the supported local stack; host Node/npm versions must match each component manifest.

Run these commands from the repository root unless a `cd` is shown:

```sh
make up-dev
```

These are source-defined entry points. Full dependency installation and service startup were not run during the portfolio maintenance audit; successful application deployment is not claimed.

### Environment configuration

Inspect `docker-compose.dev.yml` and the component-specific environment templates before startup. Supply local database, service URLs and integration credentials through untracked environment files or a secret manager. Do not copy production credentials into tracked files.

### Testing

```sh
make test-api-unit
```

The full application suite requires the dependencies and services described above. Shell changes in this maintenance pass were checked separately with syntax and mocked command tests; that does not replace integration testing.

### Deployment and integrations

Start with `docker-compose.prod.yml` and review image versions, persistent data paths, authentication, exposed ports and backups before production use. Integration implementations and configuration are in the source directories described above; generated API clients must stay in sync with server contracts.

### Source provenance and license

Imported from [Infisical/infisical](https://github.com/Infisical/infisical); upstream functionality and copyright belong to the original contributors. Local Git history begins with a 2026 source snapshot import, not historical authorship. The exact imported upstream revision is unknown. The upstream GitHub repository was created on 2022-08-05; the local year directory is organizational metadata.

Read [LICENSE](LICENSE) and nested license/notice files before redistribution; enterprise and bundled third-party components may use different terms. Restored root license text was retrieved verbatim from the official upstream repository during this maintenance pass.

## Distribution status

Further publication of this complete imported snapshot is on hold: `backend/src/ee/LICENSE.md` restricts redistribution of enterprise code. The existing remote import was not deleted or rewritten. Resolve permission or obtain a correctly scoped community source tree before publishing additional history. Root community licensing does not override enterprise terms.
