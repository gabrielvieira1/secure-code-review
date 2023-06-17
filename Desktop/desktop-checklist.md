# secure-code-review

A starter secure code review checklist

## Table of Contents

- [Autenticação e Autorização](#Authentication)
- [Data Validation](#Validation)
- [Memory and Resource Management](#Memory)
- [File handling](#File)
- [Secure communication](#Communication)
- [Cryptography](#Cryptography)
- [Updates and Fixes](#UpdatesFixes)
- [Error handling and Log Management](#LogError)
- [Configuration](#Configuration)

### <a name="Authentication">Authentication and Authorization</a>

- [ ] Ensure that all critical application functions are protected by authentication.
- [ ] Make sure there is adequate access control for different user privilege levels.
- [ ] Make sure passwords and credentials are stored securely and are not transmitted in plain text.
- [ ] Sensitive transactions require re authentication
- [ ] Authentication and Authorization checks are done on each private request
- [ ] Authorization checks are granular, per page / directory / action
- [ ] Authorization checks are appropriate for each HTTP Verb the application supports

### <a name="Validation">Data Validation</a>

- [ ] All user input is validated for proper type, length, format and range
- [ ] Validation on user input is done server side
- [ ] Uploaded files are validated for content type, size, file type and filename
- [ ] Special characters are sanitized before being used in external systems, like databases
- [ ] Does invalid input trigger handled exceptions

### <a name="Memory">Memory and Resource Management</a>

- [ ] Prevent memory leaks by correctly releasing allocated resources when they are no longer needed.
- [ ] Make sure there are no invalid references or loose pointers that could be exploited.

### <a name="File">File handling</a>

- [ ] Validate file names and paths to prevent arbitrary file inclusion (path traversal) attacks.
- [ ] Restrict file and folder access permissions to ensure only necessary operations are allowed.

### <a name="Communication">Secure communication</a>

- [ ] Use proper encryption to secure communication between the app and external services.
- [ ] Make sure that all network connections, such as HTTP requests, are made over secure channels (HTTPS).
- [ ] Sensitive data is only transmitted over an SSL connection
- [ ] Site is partitioned into private and public URLs
- [ ] Sensitive data has been secured in memory, storage and transit
- [ ] Sensitive data doesn’t leak to non private channels

### <a name="Cryptography">Cryptography</a>

- [ ] User passwords are encrypted using a stretching algorithm and uniquely salted
- [ ] Block ciphers operate in CBC and IV values are not reused
- [ ] Salts are unique per user, have over 64 bits of secure random data
- [ ] Check for known bad ciphers (RC4), cryptographic hash functions (MD5) and insecure random number generation

### <a name="UpdatesFixes">Updates and Fixes</a>

- [ ] Keep the app up to date with the latest fixes and security patches.
- [ ] Implement a secure update mechanism to ensure users are using patched versions of the software.

### <a name="LogError">Error handling and Log Management</a>

- [ ] Do not reveal sensitive information in error messages.
- [ ] Error messages don’t reveal sensitive information
- [ ] Error messages aren't user controllable
- [ ] Properly log and monitor errors to detect potential vulnerabilities or exploits.
- [ ] All sensitive user actions are logged with the following: Where, What, When, Who, How answered
- [ ] All sensitive system actions are logged with the following: Where, What, When, Who, How answered
- [ ] Sensitive info is not logged
- [ ] User input is sanitized and validated before being placed in application logs

### <a name="Configuration">Configuration</a>

- [ ] Sensitive data is not hard-coded in configuration files
- [ ] Develop and test code are properly segregated from production
- [ ] Dependencies are up to date

#### Sources and References

- [OWASP Code Review Guide](https://owasp.org/www-project-code-review-guide/)
