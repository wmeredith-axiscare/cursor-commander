## Security Checklist

### Input Validation
- All user inputs validated and sanitized
- Schema validation where appropriate (Zod, JSON Schema, Pydantic, etc.)
- File uploads validated (type, size, content)

### Injection Prevention
- **SQLi**: No raw SQL with user input; use parameterized queries or ORM
- **XSS**: Avoid raw HTML injection; sanitize if unavoidable
- **Command injection**: No user input in shell commands
- **Path traversal**: Validate file paths, no `../` exploitation

### Authorization
- AuthZ checks on every request/action touching protected data
- Principle of least privilege enforced
- Admin routes/actions properly protected
- Don't rely on client-side checks for access control

### Sensitive Data
- No secrets/PII in logs, responses, or client state
- Environment variables used correctly (public vs private)
- Tokens/keys not exposed in URLs or error messages
- Secrets not committed to version control

### Attack Vectors
- Rate limiting on auth and sensitive endpoints
- CSRF protection where needed
- Proper CORS configuration
- Session management secure (httpOnly, secure flags)
