# 🔒 Secure Package Distribution — CVE-Free by Design

Welcome to the **GreenOSS PSL organization** for our private package ecosystem.

This organization is dedicated to **securely building, auditing, and publishing software packages** that are **verified free from known vulnerabilities (CVEs)**.

---

## 🎯 Mission

Our mission is to **maintain and distribute safe, dependency-audited packages** across our internal and client ecosystems.  
Every package published through this organization undergoes **manual CVE review, patching, and verification** to ensure reliability and security.

We exist to **prevent vulnerable packages from entering production pipelines** — protecting developers, users, and organizations from supply-chain risks.

---

## 🧩 What We Do

### 1. **Private & Controlled Package Publication**
- All packages are published to **private repositories** or **restricted registries**.  
- Access is **limited to authorized collaborators** via scoped tokens.  
- **Read, write, and publish permissions** are strictly role-based.

### 2. **CVE-Based Package Curation**
- We **identify widely-used community packages** based on popularity and adoption.  
- Each package is **reviewed for known CVEs** using public vulnerability databases such as **NVD**, GitHub Security Advisories, and OSV.  
- CVEs are **manually patched or backported**, ensuring that the published version is free from reported vulnerabilities.  
- Security advisories and the applied mitigations are **documented per version** for traceability.

### 3. **Manual Patch & Release Process**
- Packages are forked from upstream and **patched manually** to fix CVEs.  
- Each release is **tested locally** and verified before publishing.  
- Every patched version is **digitally tagged and versioned** in the repository.  
- Builds are reproducible, and all changes are **auditable**, ensuring that consumers get **verified, CVE-free packages**.  

### 4. **Forked & Patched Package Maintenance**
- We maintain **forked versions of popular open-source packages** that include:
  - Backported security patches.
  - Hardened input validation.
  - Removal of unsafe or deprecated APIs.
- Example: Patched versions of libraries like `express-hbs`, `jsonpath-plus`, `cross-spawn`, and others.

---

## 🔍 Security Principles

- **Least Privilege Access:** Only designated maintainers can publish.
- **Auditability:** Every package commit and release is logged with metadata.
- **Transparency:** Security advisories and fix notes are published internally and optionally upstream.
- **Integrity Enforcement:** Only verified, signed artifacts are accepted by consumers.

---

## 🧱 Typical Use Case

This organization supports internal engineering teams and select partners who:
- Need **guaranteed secure dependencies** for production systems.
- Want to **mirror or consume packages privately** without exposure to public registry threats.
- Require **CVE-free forks** of critical dependencies for long-term supported environments.

---

## 🧰 Example Projects

| Package | Description | Status |
|----------|--------------|--------|
| `express-hbs` | Secure fork of `express-hbs` with restricted layout path resolution | ✅ CVE-Free |
| `jsonpath-plus` | Hardened fork of `jsonpath-plus` (CVE-2024-21534 fix) | ✅ CVE-Free |
| `braces` | Sanitized fork with environment safety patches | ✅ CVE-Free |

---

## ⚙️ Publication Model

- **Registry:** GitHub Packages (Private Scope)  
- **Access Control:**  
  - Only authenticated users with scoped PATs can install.
  - Publication rights are restricted to CI tokens and maintainers.

```bash
# Example: Installing a verified private package ( need to have a PAT and user account added to readonly contributors )
npm install @greenosspsl/jsonpath-plus@9.0.0-patched --registry=https://npm.pkg.github.com
