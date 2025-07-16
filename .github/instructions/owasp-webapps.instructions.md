---
applyTo: '**.py, **.js, **.java, **.go, **.ts, **.rb, **.php'
---
Provide project context and coding guidelines that AI should follow when generating code, answering questions, or reviewing changes.
# OWASP Web Applications Project Guidelines

## A01:2021 – Broken Access Control

### Description
Broken Access Control is a security vulnerability that allows unauthorized users to gain access to restricted resources or perform actions outside their intended permissions. This can lead to data exposure, modification, or deletion.

### Recommendations
1. Implement Role-Based Access Control (RBAC) to enforce user permissions.
2. Validate user input to prevent unauthorized access attempts.
3. Regularly review and update access control policies.
4. Use secure coding practices to prevent common vulnerabilities.

### Resources
- [OWASP Access Control Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Access_Control_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
Access control is only effective in trusted server-side code or server-less API, where the attacker cannot modify the access control check or metadata.

- Except for public resources, deny by default.

- Implement access control mechanisms once and re-use them throughout the application, including minimizing Cross-Origin Resource Sharing (CORS) usage.

- Model access controls should enforce record ownership rather than accepting that the user can create, read, update, or delete any record.

- Unique application business limit requirements should be enforced by domain models.

- Disable web server directory listing and ensure file metadata (e.g., .git) and backup files are not present within web roots.

- Log access control failures, alert admins when appropriate (e.g., repeated failures).

- Rate limit API and controller access to minimize the harm from automated attack tooling.

- Stateful session identifiers should be invalidated on the server after logout. Stateless JWT tokens should rather be short-lived so that the window of opportunity for an attacker is minimized. For longer lived JWTs it's highly recommended to follow the OAuth standards to revoke access.

## A02:2021 – Cryptographic Failures

### Description
Cryptographic Failures occur when sensitive data is not properly protected using encryption or other cryptographic techniques. This can lead to unauthorized access, data breaches, and other security incidents.

### Recommendations
1. Use strong encryption algorithms and key management practices.
2. Protect sensitive data in transit and at rest.
3. Regularly review and update cryptographic protocols and libraries.
4. Implement proper authentication and authorization mechanisms.

### Resources
- [OWASP Cryptographic Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
- Always use strong, industry-standard encryption algorithms (e.g., AES-256) for sensitive data.
- Implement proper key management practices, including key rotation and access controls.
- Use secure protocols (e.g., HTTPS, TLS) to protect data in transit.
- Regularly audit and test cryptographic implementations for vulnerabilities.

## A03:2021 – Injection
### Description
Injection vulnerabilities occur when untrusted data is sent to an interpreter as part of a command or query. This can allow attackers to execute arbitrary commands, access sensitive data, or compromise the application.      

### Recommendations
1. Use parameterized queries or prepared statements to prevent SQL injection.
2. Validate and sanitize user input to prevent command injection.
3. Use ORM (Object-Relational Mapping) frameworks to abstract database interactions.
4. Regularly review and update code to identify and fix injection vulnerabilities.                  

### Resources
- [OWASP SQL Injection Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Cheat_Sheet.html)
- [OWASP Command Injection Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Command_Injection_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
- Always use parameterized queries or prepared statements for database interactions.
- Validate and sanitize all user inputs to prevent injection attacks.
- Use ORM frameworks to abstract database interactions and reduce the risk of injection vulnerabilities.
- Regularly review and update code to identify and fix injection vulnerabilities.               
- Implement input validation and output encoding to prevent cross-site scripting (XSS) attacks.

## A04:2021 – Insecure Design
### Description
Insecure Design refers to the lack of security controls and considerations in the design phase of software development. This can lead to vulnerabilities that are difficult to fix later in the development lifecycle.  

### Recommendations
1. Incorporate security requirements into the design phase of software development.
2. Use threat modeling to identify potential security risks and design mitigations.
3. Regularly review and update design documents to reflect security considerations.
4. Implement secure coding practices throughout the development lifecycle.      

### Resources
- [OWASP Secure Design Principles](https://owasp.org/www-project-secure-design-pr
inciples/)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)       

### How to Prevent
- Incorporate security requirements into the design phase of software development.
- Use threat modeling to identify potential security risks and design mitigations.
- Regularly review and update design documents to reflect security considerations.
- Implement secure coding practices throughout the development lifecycle.       

## A05:2021 – Security Misconfiguration
### Description
Security Misconfiguration occurs when security settings are not properly configured, leaving the application vulnerable to attacks.
This can include default settings, unnecessary features, or insecure configurations.    

### Recommendations
1. Regularly review and update security configurations.
2. Disable unnecessary features and services.
3. Implement secure defaults and harden configurations.     
4. Use automated tools to identify and fix security misconfigurations.  

### Resources
- [OWASP Security Misconfiguration Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Security_Misconfiguration_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)       

### How to Prevent
- Regularly review and update security configurations to ensure they are secure and up-to-date.
- Disable unnecessary features and services to reduce the attack surface.
- Implement secure defaults and harden configurations to prevent security misconfigurations.
- Use automated tools to identify and fix security misconfigurations.

## A06:2021 – Vulnerable and Outdated Components
### Description
Vulnerable and Outdated Components refer to the use of libraries, frameworks, and other software components that have known vulnerabilities or are no longer maintained. This can lead to security risks and compatibility issues.  

### Recommendations
1. Regularly update and patch software components to address known vulnerabilities.
2. Use automated tools to identify and manage software dependencies.
3. Implement a process for evaluating and approving third-party components.     
4. Monitor for security advisories and updates for software components.

### Resources
- [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
- Regularly update and patch software components to address known vulnerabilities.
- Use automated tools to identify and manage software dependencies.
- Implement a process for evaluating and approving third-party components.
- Monitor for security advisories and updates for software components.  

## A07:2021 – Identification and Authentication Failures
### Description
Identification and Authentication Failures occur when an application does not properly verify the identity of users or does not implement strong authentication mechanisms. This can lead to unauthorized access and data breaches. 

### Recommendations
1. Implement strong password policies and multi-factor authentication.
2. Use secure session management practices to protect user sessions.        
3. Regularly review and update authentication mechanisms.
4. Implement proper error handling to prevent information leakage.

### Resources
- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
- Implement strong password policies, including minimum length, complexity, and expiration.
- Use multi-factor authentication to enhance security.
- Use secure session management practices, such as regenerating session IDs after login and logout.
- Regularly review and update authentication mechanisms to address vulnerabilities.
- Implement proper error handling to prevent information leakage and provide generic error messages to users.       

## A08:2021 – Software and Data Integrity Failures
### Description
Software and Data Integrity Failures occur when an application does not properly validate the integrity of software components or data. This can lead to unauthorized modifications, data corruption, and security vulnerabilities. 

### Recommendations
1. Implement code signing and integrity checks for software components.
2. Use secure data storage and transmission practices to protect data integrity.
3. Regularly review and update data integrity mechanisms.
4. Implement proper error handling to prevent information leakage.

### Resources
- [OWASP Software Integrity Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Software_Integrity_Cheat_Sheet.html)
- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)

### How to Prevent
- Implement code signing and integrity checks for software components to ensure they have not been tampered with.
- Use secure data storage and transmission practices, such as encryption and checksums, to protect data integrity.
- Regularly review and update data integrity mechanisms to address vulnerabilities.
- Implement proper error handling to prevent information leakage and provide generic error messages to users.       

## A09:2021 – Security Logging and Monitoring Failures