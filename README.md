# P.CL Kubernetes Sample Applications
## Echo App
```
# Download Samples
git clone https://github.com/powerds/pcl-sample-apps.git
cd pcl-sample-apps

# Deploy echo app
kubectl apply -f echo.yaml

# Check your pod is ready
kubectl get pod

# Get Your Cluster ip
export YOUR_EXTERNAL_IP=$(kubectl get nodes -o wide | grep control-plane | awk {'print $7'})

# Add domain name to your local hosts file for access your echo app
echo "$YOUR_EXTERNAL_IP echo.pcl.com" | sudo tee -a /etc/hosts

# Access your echo app
curl http://echo.pcl.com
```
## Nginx with PVC
```
# Download Samples
git clone https://github.com/powerds/pcl-sample-apps.git
cd pcl-sample-apps

# Deploy nginx app with persistent volume
kubectl apply -f nginx-with-pvc.yaml

# Check your persistent volume is ready
kubectl get pvc

# Check your pod is ready
kubectl get pod

# Get Your Cluster ip
export YOUR_EXTERNAL_IP=$(kubectl get nodes -o wide | grep control-plane | awk {'print $7'})

# Add domain name to your local hosts file for access your nginx app
echo "$YOUR_EXTERNAL_IP nginx.pcl.com" | sudo tee -a /etc/hosts

# Access your echo app
curl http://nginx.pcl.com
```
