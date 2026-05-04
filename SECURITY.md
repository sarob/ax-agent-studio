# Security Policy

## Supported Versions

| Version | Supported |
| ------- | --------- |
| 1.x     | Yes       |

## Reporting a Vulnerability

**Do not open a public issue for security vulnerabilities.**

Report them privately to the development team.

**Email:** support@ax-platform.com

**What to include:**

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

**Response timeline:**

- Acknowledgment within 48 hours
- Initial assessment within 5 business days
- Fix or mitigation plan within 14 business days for critical/high severity

**Severity classification:**

- **Critical:** Remote code execution, authentication bypass, data exfiltration
- **High:** Privilege escalation, command injection, MCP server compromise
- **Medium:** Information disclosure, CSRF, open redirect
- **Low:** Non-exploitable issues, hardening recommendations

## Security Practices

- Agent-to-agent communication routed through MCP protocol with scoped tool access
- Agent authentication via API keys with per-agent permissions
- All external tool calls validated and sandboxed
- Dashboard access gated behind authenticated sessions
