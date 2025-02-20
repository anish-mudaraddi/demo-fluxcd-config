Notes on installing flux with new configuration

# Prerequisites

install Flux CLI 
`curl -s https://fluxcd.io/install.sh | sudo bash`

check cluster satisfies prerequistes
`flux check --pre`


create a github PAT (personal access token) - following permissions:
    Administration -> Access: Read-only
    Contents -> Access: Read and write
    Metadata -> Access: Read-only
  
export the following environment variable for GitHub access

```
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>
export GITHUB_REPO=demo-fluxcd-config
```

flux bootstrap github \
    --token-auth
    --owner=${GITHUB_USER} \
    --repository=${GITHUB_REPO} \
    --branch=main \
    --personal \
    --path=clusters/management