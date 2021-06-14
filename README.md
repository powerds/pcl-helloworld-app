# P.CL Kubernetes Sample Applications
## Echo App
```
git clone https://github.com/powerds/pcl-sample-apps.git
cd pcl-sample-apps
kubectl apply -f echo.yaml
export YOUR_EXTERNAL_IP=$(kubectl get nodes -o wide | grep control-plane | awk {'print $7'})
echo "$YOUR_EXTERNAL_IP echo.pcl.com" | sudo tee -a /etc/hosts
kubectl get pod
curl http://echo.pcl.com
```
## Nginx with PVC
```
git clone https://github.com/powerds/pcl-sample-apps.git
cd pcl-sample-apps
kubectl apply -f nginx-with-pvc.yaml
export YOUR_EXTERNAL_IP=$(kubectl get nodes -o wide | grep control-plane | awk {'print $7'})
echo "$YOUR_EXTERNAL_IP nginx.pcl.com" | sudo tee -a /etc/hosts
kubectl get pvc
kubectl get pod
curl http://nginx.pcl.com
```
