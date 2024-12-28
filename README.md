# Prequisites
Testing on a kind cluster. Setup as follows

```
#!/bin/bash

sudo dnf install helm
sudo dnf install golang-bin
go install sigs.k8s.io/kind@v0.26.0
sudo dnf install kubernetes1.32-client
kind create cluster --config=kind-config.yaml
```

# Startup configuration
Most config values are given sensible defaults in values.yml. Username and password are still required. 
Install as follows

```
helm -n ib-gateway install  -f values.yaml  ib-gateway . --set TWS_USERID='<username>' --set TWS_PASSWORD='<password>'
```