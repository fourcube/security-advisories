# Advisory

**Software**: ToolJet\
**Vendor**: ToolJet Solutions Inc.\
**Affected Versions**: < 1.11.0\
**CVE**: CVE-2022-27979\
**CWE IDs**: [79](https://cwe.mitre.org/data/definitions/79.html)\
**Reporter**: [Chris Grieger](https://github.com/fourcube)

## Description

https://github.com/ToolJet/ToolJet

```
ToolJet is an open-source low-code framework to build and deploy internal tools quickly without much effort from the engineering teams. You can connect to your data sources, such as databases (like PostgreSQL, MongoDB, Elasticsearch, etc), API endpoints (ToolJet supports importing OpenAPI spec & OAuth2 authorization), and external services (like Stripe, Slack, Google Sheets, Airtable) and use our pre-built UI widgets to build internal tools.
```

Through improper sanitization of user input the the application an authenticated attacker to perform a stored Cross-site Scripting (XSS) attack on other users through the Comment component of the ToolJet Job Editor.

## POC

Authenticated users can add a comment to a ToolJet app. When a users activates the comments 'submenu' the malicous javascript payload will be executed.

Following is an example that demonstrates the vulnerability.

```html
<img style="visibility:hidden" onerror="console.log`xss`" src="__">
  ```

## Mitigation

Update ToolJet to a version >= 1.11.0.

## Timeline

|Date|Action|
|----|------|
|2022/03/21|Contacted developers with security finding, POC and mitigation note.
|2022/04/22|Fix version released.
