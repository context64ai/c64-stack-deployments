# 🚀 Data Context Hub: C64 Stack Integration - Azure 


![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat&logo=helm&logoColor=white)
![NGINX](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white)
![Certbot](https://img.shields.io/badge/Certbot-3A5796?style=flat&logo=letsencrypt&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-FE4B83?style=flat&logo=argo&logoColor=white)

This folder contains detailed instructions to deploy the C64 Stack On-Prem using Helm Charts.

For more information, please refer to the project [README](https://github.com/context64ai/c64-stack-deployments/README.md).

## 📋 Requirements

**Before you start, make sure you meet the following requirements:**

- 🐧 A **Linux machine** with sudo/root access  
- 🌐 **Internet connectivity** for downloading dependencies  
- 🌍 A DNS entry is required that points to the public IP address of the cluster
- 🐙 Git installed and access to GitHub (for cloning this repository)


# ⚙️ Configuration 

To deploy a new [**DCH**](https://www.datacontexthub.com/) instance setup follow the following steps:

### 🖥️ 1. Prepare Your Kubernetes Environment 

Update and install [Kubernetes](https://kubernetes.io/) as described in [this Documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management), then follow those steps:
   ```
   sudo apt install -y kubelet kubeadm
   sudo apt-mark hold kubelet kubeadm kubectl
   sudo kubeadm init
   ```

Connect to the cluster   

   ```
   kubectl get nodes
   ```

### 📦 2. Install Helm 
Install [Helm](https://helm.sh/) according to [this Documentation](https://helm.sh/de/docs/intro/install/#von-einem-script)

### 🌐 3. Setup the Ingress Controller
   ```
   mkdir -p apps/ingress
   cd apps/ingress
   helm upgrade --install ingress-nginx ingress-nginx -f /ingress/values.yaml --repo https://kubernetes.github.io/ingress-nginx --namespace ingress-nginx --create-namespace
   ```

### 🔐 4. Install [Cert-Manager](https://cert-manager.io/)
- Add the Helm repository
- Install Cert-Manager as described in [this documentation](https://cert-manager.io/docs/installation/helm/#2-install-cert-manager)
   ```
   mkdir -p apps/certbot
- In this directory create a CusterIssuer as shown [here](https://cert-manager.io/docs/tutorials/getting-started-aks-letsencrypt/#create-a-clusterissuer-for-lets-encrypt-staging)

### 🚦 5. Install [Argo CD](https://argo-cd.readthedocs.io/en/stable/):
 Follow the next steps or refer to the [official documentation](https://github.com/argoproj/argo-helm).

   ```
   mkdir -p apps/argocd
   helm repo add argo https://argoproj.github.io/argo-helm
   helm repo update
   kubectl create ns argocd
   helm install argocd argo/argo-cd -n argocd
   ```
Replace `argocd.example.com` with your hostname in the provided `ingress.yaml`
   ```   
   kubectl -n argocd apply -f ingress.yaml
   ```
Access Argo CD:
- URL: `https://argocd.<YourDomain>/login`
- Username: `admin`
- Get initial password:   
     ```
     kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
     ```


### 🔍 6. Check ingress status, if enabled 
kubectl get ingress --namespace ingress-nginx


It's expected that all pods managed by the dch deployment are in 'Running' state

🎉 **Instance setup completed successfully.**
To proceed with configuration and deployment, please consult the [project documentation](https://docs.datacontexthub.com/deployment-and-maintenance/installation).

### 🧯 Troubleshooting

If you run into issues during setup or deployment, check the following:

- 🧱 Use `ufw allow <PORT>/tcp` and `ufw reload` to open ports on your firewall (e.g. 80 and 443)
- ✅ Use `kubectl get all -n <namespace>` to verify pod, service, and ingress status  
- 🧵 Use `kubectl logs <pod-name> -n <namespace>` to inspect application or controller logs  
- 🌐 Check DNS propagation and TLS certificate status (e.g. via [letsdebug.net](https://letsdebug.net))  
- 🔐 Make sure Role-Based Access Control (RBAC) is not restricting Helm/Kubernetes operations  
- 🧹 After a failed Helm deployment, you can run:

### ❌ Uninstall 

To uninstall your setup, execute the following:
   ```
   kubectl get namespaces
   helm uninstall --namespace <namespace>
   ```

### 🧹 Clean-up 

Note that Secrets are not removed when Helm release is deleted.
To fully remove secrets, run the following command:
   ```
  kubectl delete --namespace <namespace> secrets --all
   ```
### 🧰 Optional Tools

These tools are not required, but can improve workflow, automation, and monitoring:

- 🧪 **K9s** – Terminal-based UI for Kubernetes cluster exploration  
  👉 [https://k9scli.io/](https://k9scli.io/)
- 📊 **Lens** – Kubernetes IDE for managing multiple clusters visually  
  👉 [https://k8slens.dev](https://k8slens.dev)
- 🛠️ **Argo CLI** – To interact with ArgoCD from the terminal  
  👉 [https://argo-cd.readthedocs.io/en/stable/user-guide/commands/](https://argo-cd.readthedocs.io/en/stable/user-guide/commands/)

### 🛠️ Support


Context64 provided scripts in this GitHub project. For direct issues, please refer to the Issues tab of this GitHub project. For other questions related to this project, contact us at `github@c64.ai`


## 📄 License


This project is licensed under the GNU GENERAL PUBLIC LICENSE – see the [LICENSE](https://github.com/context64ai/c64-stack-deployments/blob/main/LICENSE) file for details.