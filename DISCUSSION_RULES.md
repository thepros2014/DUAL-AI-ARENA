# DUAL-AI-ARENA Discussion Rules

These rules apply to every public Discussion, comment, attachment, issue, and link. Participation is a privilege, and moderators may remove content or restrict accounts that violate them.

## Never post

1. **Secrets or credentials.** Never post API keys, access tokens, passwords, cookies, JWTs, private keys, certificates, signing material, connection strings, `.env` files, authorization headers, or screenshots containing them. Rotate a secret immediately if it was exposed anywhere.
2. **Private or sensitive data.** Do not post customer data, personal information, proprietary source, internal logs, production URLs or IP addresses, regulated data, incident details, or confidential business information.
3. **Unfixed vulnerabilities.** Do not publish exploit code, weaponized prompts, exact reproduction details, or a vulnerability that has not been privately reported and coordinated. Send security reports to [thepros2014@gmail.com](mailto:thepros2014@gmail.com?subject=DUAL-AI-ARENA%20security%20report).
4. **Unauthorized material.** Share only software, data, screenshots, and test cases that you own or are authorized to disclose.
5. **Harmful activity.** No malware, ransomware, credential theft, phishing, evasion, destructive payloads, unauthorized access, surveillance, or instructions intended to facilitate abuse.
6. **Impersonation or fraud.** Do not impersonate a maintainer, customer, provider, security researcher, or another participant. Do not request credentials or payment details.
7. **Harassment or doxxing.** No threats, hate, discrimination, sexual harassment, personal attacks, stalking, or publication of someone else's identifying information.
8. **Spam and solicitation.** No bulk promotion, referral links, unrelated advertising, crypto schemes, or repeated off-topic posts.
9. **Illegal or infringing content.** Do not use Discussions to distribute pirated material, stolen data, or content that violates applicable law or another party's rights.
10. **Unverified claims.** Model output is not proof. Label AI-generated results, distinguish observations from confirmed findings, and do not present an unreviewed result as a security guarantee.

## Required for technical reports

Post a minimal, sanitized report containing the product version or commit, Windows version, provider type, steps to reproduce, expected result, actual result, and relevant redacted logs. Remove secrets and proprietary code before posting. Do not attach an entire customer project or production dump.

Use one topic per thread, search for an existing thread before opening a duplicate, and keep replies focused on the product or report being discussed.

## Safe AI and provider use

Assume that cloud providers may process submitted content under their applicable terms and retention settings. Use an approved endpoint or local Ollama for sensitive work, and follow your organization's data-classification and access policies. Review every generated suggestion before applying it; never allow an unreviewed model response to make an irreversible production change.

## Moderation and reporting

Moderators may edit for redaction, remove, lock, or archive content; limit participation; or report serious violations to GitHub or the appropriate authority. Security reports are handled privately and should not be opened as public Discussions.

If you accidentally expose a secret, revoke or rotate it first, then notify the affected provider or administrator. Do not repost the value while asking for help.
