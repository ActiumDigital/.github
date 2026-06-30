# Security & Data Protection

## Credentials Management

### ❌ NEVER commit:
- Database passwords
- API keys
- Connection strings with credentials
- Azure AD secrets
- Personal access tokens

### ✅ DO use:
- `.env.example` as template (with placeholder values)
- `.env` locally (add to `.gitignore`)
- Azure Key Vault or similar for production
- GitHub Secrets for CI/CD pipelines

## Data Classification
All data is classified as **[INTERNAL/CONFIDENTIAL/RESTRICTED]**.

## Row-Level Security (RLS)
RLS policies restrict data visibility by role/region. Document all RLS rules in `docs/rls-rules.md`.

## Access Control
- **Development**: Team members with limited access
- **Staging**: Approvers and leads
- **Production**: Authorized users via Azure AD

## Incident Response
If you suspect a security breach:
1. Stop work immediately
2. Contact [Security Team/Data Owner]
3. Do not modify or delete files
4. Document the incident

## Compliance
This project complies with GDPR/CCPA/SOX and company data retention policies.
