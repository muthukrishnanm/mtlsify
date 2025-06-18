📝 License: Apache License 2.0
This project is licensed under the terms of the Apache License, Version 2.0.
See the LICENSE file for full details.

# 🔐 mtlsify

> Automate mutual TLS (mTLS) configuration and certificate bundling — the secure way.

**mtlsify** is a lightweight, extensible JavaScript tool that generates ready-to-use mTLS configurations, keystores, and trust bundles for platforms like **NGINX**, **Envoy**, **Spring Boot**, and more. Designed for DevSecOps, platform engineers, and security-focused teams, it simplifies PKI workflows and accelerates secure service deployments.

---

## ✨ Features

- 🔐 Generate platform-specific mTLS config files from cert/key inputs
- 📦 Bundle certificates into PEM, PKCS#12 (.p12), or JKS formats
- ⚙️ Config templates for NGINX, Spring Boot, and others
- 🧰 API and CLI support
- 🔄 Extensible and easy to integrate with CI/CD workflows

---

## 🚀 Getting Started

### 📦 Install via npm (coming soon)

```bash
npm install -g mtlsify

```
### 🔧 Use CLI

```bash
mtlsify generate --platform nginx \
  --cert ./certs/client.crt \
  --key ./certs/client.key \
  --ca ./certs/ca.crt \
  --out ./output/
```

### 🧑‍💻 Use as a Library
```JavaScript
import { generateConfig } from 'mtlsify';

const config = await generateConfig({
  platform: 'nginx',
  cert: fs.readFileSync('client.crt'),
  key: fs.readFileSync('client.key'),
  ca: fs.readFileSync('ca.crt')
});

fs.writeFileSync('nginx.conf', config.configText);
```

🧪 Examples

See examples/ for sample inputs and outputs.

📜 License

Licensed under the Apache 2.0 License — free for commercial and open-source use.

🤝 Contributing

Contributions are welcome! Open issues, submit pull requests, or suggest new features. See CONTRIBUTING.md for details.

🗺️ Roadmap
	•	Support for Envoy, HAProxy, Istio
	•	Add PKCS#12 to JKS conversion
	•	Web-based UI frontend
	•	GitHub Action & Docker image

📫 Contact

Created and maintained by Muthukrishnan Manoharan
