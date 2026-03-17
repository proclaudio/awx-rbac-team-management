# RBAC Access Control Matrix

## Organizations

| Organization | Purpose |
|-------------|---------|
| Default | Built-in AWX organization |
| Development | Development team — deploy application code only |
| Operations | Full control over infrastructure and automation workflows |
| Security | Read-only visibility for audit and compliance enforcement |

## Teams and Users

| Team | Organization | User | AWX User Type |
|------|-------------|------|---------------|
| Dev Team | Development | dev-user | Normal User |
| Ops Team | Operations | ops-user | Normal User |
| Security Team | Security | sec-user | Normal User |

## Job Template Access

| Resource | Dev Team | Ops Team | Security Team |
|----------|----------|----------|---------------|
| Deploy Web App | ✅ Execute | ✅ Execute | ❌ No access |
| Deploy node_exporter | ❌ No access | ✅ Execute | ❌ No access |
| Deploy Promtail | ❌ No access | ✅ Execute | ❌ No access |
| Harden Linux Servers | ❌ No access | ✅ Execute | ✅ Execute |
| Drift Detection | ❌ No access | ✅ Execute | ✅ Execute |
| Patch Servers | ❌ No access | ✅ Execute | ❌ No access |

## Inventory Access

| Inventory | Dev Team | Ops Team | Security Team |
|-----------|----------|----------|---------------|
| Monitored Servers | ✅ Use | ✅ Use | ❌ No access |
| Hardened Servers | ❌ No access | ✅ Use | ✅ Use |
| Patch Inventory | ❌ No access | ✅ Use | ✅ Use |

## Credentials Access

| Credential | Dev Team | Ops Team | Security Team |
|-----------|----------|----------|---------------|
| Dev SSH Key | ❌ No access | ✅ Use | ❌ No access |
| GitLab Lab Credential | ❌ No access | ✅ Use | ❌ No access |

## AWX Role Definitions

| Role | Capabilities |
|------|-------------|
| Admin | Full access including create, modify, delete |
| Execute | Can launch job templates, cannot modify |
| Use | Can use resource in jobs, cannot modify |
| Read | View only, cannot launch or modify |
