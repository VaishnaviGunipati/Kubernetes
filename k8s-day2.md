## Kubernetes

### Services
<img width="3483" height="1144" alt="image" src="https://github.com/user-attachments/assets/3ba67792-49a3-4797-b093-def022ca8a8a" />


#### Types of service's
<img width="2206" height="831" alt="image" src="https://github.com/user-attachments/assets/057baaa7-b8ff-4b69-b556-dc2376da7ad8" />


#### Expose Application to outside cluster
1. NodePort -- Range(30000-32767)
- Expose Paticular Port on all nodes
- Expose randon port if we not specify -- nodePort: 30007

<img width="2064" height="724" alt="image" src="https://github.com/user-attachments/assets/367a3e87-3a35-4b10-aa81-07799a934246" />

#### NodePort with 3 Nodes
<img width="2681" height="2230" alt="image" src="https://github.com/user-attachments/assets/de108cb4-f865-4ea7-9243-35ae944e2437" />



```
kubectl apply -f deploy.yaml

kubectl apply -f np.yaml
```
#### Access Application
```
public-ip-any-node:NP
xx.xx.xx.xx:30007
```
2. ClusterIP
- Internal communcation with name of service
- default type of service is ClusterIP
<img width="2350" height="3006" alt="image" src="https://github.com/user-attachments/assets/fb71c934-9439-46f0-9aaf-deab4d914d06" />

```
kubectl apply -f c-ip.yaml 
```
```
kubectl describe svc nginx-svc-cip
```
```
kubectl get ep
```
3. LoadBalancer
- it will create external loadbalancer in cloud.
  <img width="2350" height="3711" alt="image" src="https://github.com/user-attachments/assets/b578c144-e74e-4b47-a937-4e86f1b82b1b" />

```
kubectl apply -f lb.yaml 
```
4. ExternalName
- it uses cname
- connect to our external DB (inside cloud)
  <img width="2547" height="1028" alt="image" src="https://github.com/user-attachments/assets/6604bc70-5b96-4f30-9fff-0e4d94f57214" />

```
kubectl apply -f ext.yaml 
```
