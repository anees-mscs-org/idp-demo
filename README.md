**Prequisites**:
https://github.com/charmbracelet/gum#installation

**Steps**:

1. Fork this repository under your GitHub organization with repository name as `idp-demo`.  You need to be organization admin of an org to run this demo.

2. Create org admin token (ORG_ADMIN_TOKEN). Under Personal access token settings of the org, enroll access via Personal Access Token(s).  `Personal access token (classic)` was used in this demo.
The actual token needs to be created under user profile Developer settings with below scopes:
   - Read/Write access to repositories (repo)
   - Delete repositories (delete_repo)
   - Codespace secrets (codespace)
   - Read/Write access to repository hooks (admin:repo_hook)
   - Workflows access (workflow)
   - Admin access (admin:org, admin:org_hook)

3. Clone the forked repo on your local
4. Authenticate Github CLI, run 'gh auth login' and follow the instructions.
5. run ./setup.sh


**Deployed tools**
1. Port UI - portal for application developers to use pre-configured infrastructure resources by the platfrom team.
2. ArgoCD - portal for platform team to view deployed apps and infra resources. ArgoCD available on `gitops.${INGRESS_HOST}.nip.io`, where INGRESS_HOST IP can be found in the `.env` file on local once setup is completed.
3. Interacting with k8s cluster - In the forked idp-demo folder, platform team can use `kubectl` to access k8s resources.
```
export AWS_ACCESS_KEY_ID=***
export AWS_SECRET_ACCESS_KEY=***
kubectl get namespaces
```

