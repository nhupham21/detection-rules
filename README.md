# detection-rules

Sigma detection rules written alongside the vulnerability and incident analyses on [netsec101.com](https://netsec101.com).

Every rule is:

- grouped by **domain** (Windows, Linux, macOS, Network, Web/App, Cloud, Identity, Kubernetes, Email, Cross-Platform),
- mapped to **MITRE ATT&CK** tactics and techniques in its `tags`,
- linked back to the netsec101 write-up that explains the case, the condition and how to tune it.

Browse the full list in [Detection Rules](Detection%20Rules/README.md).

## Using the rules

Convert them to your SIEM query language with [sigma-cli](https://github.com/SigmaHQ/sigma-cli), for example:

```
sigma convert -t splunk -p splunk_windows "Detection Rules/Windows/<rule>.yml"
sigma convert -t lucene -p ecs_windows "Detection Rules/Windows/<rule>.yml"
sigma convert -t kusto -p microsoft_xdr "Detection Rules/Windows/<rule>.yml"
```

Rules are starting points. Most are `experimental`: test them against your own logs and tune exclusions before you alert on them.
