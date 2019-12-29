# K8S

## Config 구성
- 

## Cluster 추가



''''yaml
> kubectl config view
apiVersion: v1
clusters:
- cluster:
    certificate-authority: /nonexistent/.kube/certs/ca.crt
    server: https://localhost/k8s/clusters/c-r8nn4
  name: Default
contexts:
- context:
    cluster: Default
    user: Default
  name: Default
current-context: Default
kind: Config
preferences: {}
users:
- name: Default
  user:
    token: kubectl-shell-user-4g6r7:b9g94wbw9lszqwm9pwpkknvv6nplwd2h5hvjwv4r8jznrmlqtpqtjw
''''