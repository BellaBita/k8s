# K8S

## Config 구성
- cluster : 
  - name으로 식별되는 Cluster설정  
  - server : (API서버 주소) 
  - certificate-authority (or certificate-authority-data) : TLS 통신을 위한 Public Key 파일위치 or Data
- user : 
  - name으로 식별
  - token : token 방식 인증의 경우 사용하는 token 값 
  - client-certificate-data : 
  - client-key-data : 
- context : cluster-user를 묶어서 어느 Cluster에 어느 User로 접속할 지를 설정
  - name으로 식별
  - cluser : Cluser의 Name
  - user : User의 Name
- current-context :  현재의 Default Context 설정값


## Kube Config Sample (~/.kube/config)

> kubectl config view

- Token Sample
```yaml
apiVersion: v1
clusters:
- cluster:
    certificate-authority: c:\temp\kube\certs\ca-rancher.crt
    server: https://kubernetes.docker.internal/k8s/clusters/c-r8nn4
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
    token: token-x6x8v:sjdf7wxlbnzvsnbk9zxvdqlb7jntpn5r2xf4xfvh58lszw8kfzl668
```

- CA Data Sample
```yaml
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUN5RENDQWJDZ0F3SUJBZ0lCQURBTkJna3Foa2lHOXcwQkFRc0ZBREFWTVJNd0VRWURWUVFERXdwcmRXSmwKY201bGRHVnpNQjRYRFRFNU1USXlPVEExTVRVek9Gb1hEVEk1TVRJeU5qQTFNVFV6T0Zvd0ZURVRNQkVHQTFVRQpBeE1LYTNWaVpYSnVaWFJsY3pDQ0FTSXdEUVlKS29aSWh2Y05BUUVCQlFBRGdnRVBBRENDQVFvQ2dnRUJBTWVICkZMa21CdHZNVlFXR2dOWHlKNzZVcDY3dUlVK2xxSk9TQmVPQVNVa25DY3RQVm1RbmtPTnZrRUh2RmRsWGFZMUMKU0x4T29OM29vczRVNFM5amxudFllYjVsaDR2dGF0NGZPUkRHenZrZjAwRzNIQjVTR3dTUVA0UE9pSUlYcDA3TworSlU0ZDZ4Sy93dUd4RnQ3MmFPM0NCUTRCTkcyTkI3dzhKMjRodmZXeldNekEzZWFaOHQ0cm0reXFFcVpESWpoCmE3b3puWFZyNi9KUmtJb1dZbUphcDEyYXRNRTEwaUFINTh1L1NRbmJIS2pHMEJSNnd0aHk5cThkQUVxZGx5TUgKTTBoZ0VYWDFwSE8yUC9lRi9UYi92OUlMWmcvWGVZTnZQZ21PNU1pZDRieXJuT2Z3aDUraEZ2ZG1tUy92bUdYbQpUMVFZa0ZIS1JtSXduYVAyd0UwQ0F3RUFBYU1qTUNFd0RnWURWUjBQQVFIL0JBUURBZ0trTUE4R0ExVWRFd0VCCi93UUZNQU1CQWY4d0RRWUpLb1pJaHZjTkFRRUxCUUFEZ2dFQkFDRTFZOHpzZHdxMElJNkZ0Rng4VzRzTXdRdUcKczBGdjRiclVuY3V5bHRRM1c1L04zTnJsUHAwcUVGZFQ0SkkxY3lUUEx6L2h3WW1KTWFrZTRQUFlCUHQwMUcyMgpJSjc1eXkxNWlrRjJqc2J2dzFpMGZzUnZKOUxydWJpSlNhY1lIR216U0U3SGQ1QkJVVlRudFhSeVlDQmNMNGhEClo2ZzM0UjJMdlhYRkQwNmdmVzdOQ3NNWFdLM1c5ZDVwTXpCNXRtN1RiZEp4bkMySlpMRzV3VEpqVEJEekFZc1kKTkZMWFQvZGNGa29ZSzdEcDIyNWJpWVI3UDl3Ymk1WFA3STVmeGVSZnVHZG9Ea3c5TldrUTF5QnBEM1c4emNYbgpZNVdpeHNsbitET3BhaEkzYXVRRmhwVkQrM2FYT2ZDdjJvU1MzOFk2a1VrUFF6V0lJTFBvL2xRRmxYUT0KLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo=
    server: https://kubernetes.docker.internal:6443
  name: docker-desktop
contexts:
- context:
    cluster: docker-desktop
    user: docker-desktop
  name: docker-desktop
- context:
    cluster: docker-desktop
    user: docker-desktop
  name: docker-for-desktop
current-context: docker-desktop
kind: Config
preferences: {}
users:
- name: docker-desktop
  user:
    client-certificate-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUM5RENDQWR5Z0F3SUJBZ0lJWXU0MEdqMWEyUzR3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB4T1RFeU1qa3dOVEUxTXpoYUZ3MHlNREV5TWpnd05USTNOREJhTURZeApGekFWQmdOVkJBb1REbk41YzNSbGJUcHRZWE4wWlhKek1Sc3dHUVlEVlFRREV4SmtiMk5yWlhJdFptOXlMV1JsCmMydDBiM0F3Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLQW9JQkFRREkzVGY0UU1HaVQxZ1kKR0VwUW1TTXNYYldiaWg3Q2VJcG12YWs2VllKWWxLMUQzN2FncHlrdEIvWnhGUGJaRytCOHhTUGtuU1Z4Rll3TgpYaW8wMGNLNnBqaUpWVXJDVHo1K01CbkZqbUF4cUh3ektzbWo1V1dqblBBYnVlUmpkRVJnTTlkMExacGJEZmZmCjV6OGU2ZTB1TjFTMU1YUy9nTzlLVDJidjJEeW5mNytnRmdUcE1nOElldk5SaEtwMTdHbjRsQm14S2N0b1BBdUkKcUx0cVA0RGErcUh3TFFrNHBHTmNRR0M2a2FCL1lWaktSTHg4amVUSUIyalYvVG1LOUxBVzM5MmdKTEhIVmZzVQo0VUNBVnVLVTNXUm92cFlWMmtGNlpRZkY0MmlYRGZRNVJLRDFvdjNKdXJFNW1VUndJS1Z6ZFhlOWM1TU9SOTh1CnRMQndZQ1hqQWdNQkFBR2pKekFsTUE0R0ExVWREd0VCL3dRRUF3SUZvREFUQmdOVkhTVUVEREFLQmdnckJnRUYKQlFjREFqQU5CZ2txaGtpRzl3MEJBUXNGQUFPQ0FRRUFmKzU2Nkd6Z0pKMCtpQk9sV0xVY2daVVhZWTk2TDRLVApwMU5SeGxqczlhZTdDcnlIc1hYeHdVdUtFWGN0R3BEbXVidzhCWGx2UTQ1Y0JwZ1pueFJQN1Jtak16RnN2elc3CnVaUzM4UCszTGxudWo4bmJZNDFsT2ZmUy9sVzgxaThxdDdCQ281d2pIcWFabDVwRWp3alpwbWNRZ0c2T3J6bnAKSUtvK3FjYXZtdWNoTnI4YUdxK25nT2lqRHEwNU5IcC9lREtyMW82UkFRY3VJSlJGRDJTSzl4dG1aWVZEYWc4QgovY0J0MUFuQmE3OXk3NVBJZGdHMUgyN1M5RVZOWk5tbkZDNklJV2tpMUFCa21NSkJRdGhNQVdkeVV5VWdPMzdxClQ0UkRHZDdTZGpwSGhIdE9FeElqS2tJcXBoQ3dyWngzMDkrNlNvVWhvNkk5a3RLRWtaaVBpQT09Ci0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K
    client-key-data: LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFcEFJQkFBS0NBUUVBeU4wMytFREJvazlZR0JoS1VKa2pMRjIxbTRvZXduaUtacjJwT2xXQ1dKU3RROSsyCm9LY3BMUWYyY1JUMjJSdmdmTVVqNUowbGNSV01EVjRxTk5IQ3VxWTRpVlZLd2s4K2ZqQVp4WTVnTWFoOE15ckoKbytWbG81endHN25rWTNSRVlEUFhkQzJhV3czMzMrYy9IdW50TGpkVXRURjB2NER2U2s5bTc5ZzhwMysvb0JZRQo2VElQQ0hyelVZU3FkZXhwK0pRWnNTbkxhRHdMaUtpN2FqK0EydnFoOEMwSk9LUmpYRUJndXBHZ2YyRll5a1M4CmZJM2t5QWRvMWYwNWl2U3dGdC9kb0NTeHgxWDdGT0ZBZ0ZiaWxOMWthTDZXRmRwQmVtVUh4ZU5vbHczME9VU2cKOWFMOXlicXhPWmxFY0NDbGMzVjN2WE9URGtmZkxyU3djR0FsNHdJREFRQUJBb0lCQUNmWXdzYXJ5ZjN4OFk3dQpHcWY4aVI2L0JFenp6SUJWdTFjQVh2YmtpYlFhNG5ocGcraEE0UWsrNENPMHZmZDU4VUd2Tmh5ZkZCTm42OTJuCkJZWnU2a3R1dUI1K1hoTkg5eVMvVkExOTNoVmIwQyt5V0VmOE5QcU5JcEROZ3NJOENXaHdRRmlheDFreTN5NTYKeUduUWpDMno2a2o3bzZadDVJcUFUL0phbWtXNzF2ZzRNcnB3SDZkZGtxRkhOQUtmVitzMFJEUEE5NHNRazcxVgplUVBwNDhoVGIrbXlkTGFTa1U2ZFM3bkNpLzRremIycDlEVm1FczlzdVJzcVpzNzViZDRONGFwbFlPeWRsZlJYCmg2L0JWenlIV1ZEZnE5Y21nT3FLVGNlcndzMnlBUGUzaTlhTVUrcFc4NXZTeUF3b1BpMnprUGVYN0dhN3l3SjkKM01zeTdlRUNnWUVBNnVkRDZrQlI3d0Z2MEtPRFBlRWpyOU0xN21qSkljQXFIQlBwZkNnNHBwbTJNaTFOaThMVwo3b2ZiSGlaRG43WkQ1OGxGaTdWd29aeTYrOUF5cFd5blBQY3FsT3M3VGU3d1I4V29vamNzMis1RmhNd1YzU29PCis2ZkRubjdxNEhlWTV5dFg5ak92QXRoUXBZT25yQW1FY1pGV3FwaU1tS25iQ0ZTNWlUeGEvL0VDZ1lFQTJ1ZFkKeFQrSVhJY1dtSGtVZXFuZHIrcG84NTNRQnlyZnBpRVlyUUc4K29zcG5PM2ozNEFFUFEvUGZEYVNONE10WktzUwpmWEpoRjlIa1QyanNxZkt6MDBPMU5mU2hWY2xEd3hCQ21kbUpXV25xRmVvdWxnTkhRNnoxSzJqRTdyajllYmEwCkx0SnBTZkx6NXVtK0ZqVGRrY291YkRRRzVhQVFrc0ZQbnZzb2x4TUNnWUVBaldTWEpMR0NuL0tsYzFoNDd3NU4KaE5BRmJuUDBYVFJtSkhCMzRodnp2WlJZYnV1RitkSlZ2VTVaUGxTWjc5Q3VIeDZ2bGVDbzR4Nk1EbmJMaFhkWgpVd0VUeUgrdk9zSFFMK055RmZKUU5qRzk5cWxCbjlacEhtRmxCa291NXQ0V1UwOXJxdTZCTVowekxlMkpSNnlTCjVDa3ZtWkFwVU5zczFGN3JMd2Y5WG9FQ2dZQUNGMGVmeXJXUXZMR1lqeitFMUc2THFaK0xCQ3ppaEtSU1ArcXUKYkYvVHZOU083UzdLQ2IwQW9GQUpEYlJqMTFydHBUeXQraE8zV0lmbndrYlFjTU1LOTVDWmpWYWxMU0Q2a2dNdwoyUVVZMTR3bTNXL0lld3VKTi9PM2tHNmhJUjg2dEdZUU5HNVJDSU1QNTVlck9xSUxMSFU1RDE0cGYxZnBMdk9GCnZ6eHFCUUtCZ1FEZWlBMjZGUUllNEhvN1Q1b2I5eGo3anhzQmU5Z0xRQjlHQjUrZjJWTXlPKzdEUTh3Um01WUUKd01HdDIzU0R4Y0liV083WStuL3k2eFpwUjhPTjZRRUlHOE1xbVl4VnBSaWJXZVVNNTFEQ0QyR2ZUMlhsZ1dNQgpEMnhROGJQd1U0em12ZjZ2UkZiVWxPWXlrVjV6RDhvaThPNXBQMVV2MUZjNDlUWGxVMHNzN2c9PQotLS0tLUVORCBSU0EgUFJJVkFURSBLRVktLS0tLQo=
```
## CA certificate-authority-data  
> TLS 규약에 따라 Client에서 Server (API Server End Point, etcd, Controller Manager)의 인증을 위한 PKI 인증서임  
참조 : https://kubernetes.io/ko/docs/setup/best-practices/certificates/

```text
-----BEGIN CERTIFICATE-----
MIIC7jCCAdagAwIBAgIBADANBgkqhkiG9w0BAQsFADAoMRIwEAYDVQQKEwl0aGUt
cmFuY2gxEjAQBgNVBAMTCWNhdHRsZS1jYTAeFw0xOTEyMjkwNTQzMjdaFw0yOTEy
MjYwNTQzMjdaMCgxEjAQBgNVBAoTCXRoZS1yYW5jaDESMBAGA1UEAxMJY2F0dGxl
LWNhMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAyyNNCHHdNfcdDsPL
esV1HWL5DHLxJ0xuPODW/G6GytL2osIjWBlbP5i9AKYpIxhWQLHPhY/HKdFMXDyg
xz5+pXxMDTXNOJ/FmNLWyq5XdGH10dNT15TFJCC8jPEy8GfwvFCCEbUnMz337f5H
Wp8vZGg6rJ2Sluz0tD9AT+qv1jgJV4qI6nwT7th1mKEt/5ERF6pyGSBI/SAxtoGp
L9oFw6XyuD4y3J+k2GEADZhEOwtN53u1xbz6/2OL2uJJefqX8yX+ZKIfvlRF5ZNj
lWbMlTqfjYjiutK9H/fqykBCHz5zzvgUJU3DI+nYk573AvUoFUUdmowV5NMWgkdY
C9hAwwIDAQABoyMwITAOBgNVHQ8BAf8EBAMCAqQwDwYDVR0TAQH/BAUwAwEB/zAN
BgkqhkiG9w0BAQsFAAOCAQEAYC+6QPm6q7XoRiWB4QBuu1XMJh//uscmw8ZMig61
siwn51u8gHZfP77gqFEIzLnj/jkTbgPWAhYM3S+4aEe2B36Vlh295xDPySK9VJkg
LfiAuqQ+OYyJFHAzWOjs3TEH/MTByL8bTI5Vn0oK1Bpj8bHA7iYFUBc6bvrFegDy
iEEx4HTSob++FzxFKsXnAZVawS0vIop2byUIHsx3rTZayOfma0prAMG9AcYycwci
+7ybGsxwVgjlbe6fKhSF5RZ/r4TdrGs5h61LTesgtHtXU9eKigyjMyH0sMB5cmZt
qx0+fCSIt01jVgaOz3E4aDlAr7bM3MjLJXmcQhwMQhTNMw==
-----END CERTIFICATE-----
```

## kubectl config commands
https://kubernetes.io/ko/docs/reference/kubectl/cheatsheet/

kubectl이 통신하고 설정 정보를 수정하는 쿠버네티스 클러스터를 지정한다. 설정 파일에 대한 자세한 정보는 kubeconfig를 이용한 클러스터 간 인증 문서를 참고한다.

kubectl config view # 병합된 kubeconfig 설정을 표시한다.

### 동시에 여러 kubeconfig 파일을 사용하고 병합된 구성을 확인한다
KUBECONFIG=~/.kube/config:~/.kube/kubconfig2

kubectl config view

### e2e 사용자의 암호를 확인한다
kubectl config view -o jsonpath='{.users[?(@.name == "e2e")].user.password}'

kubectl config view -o jsonpath='{.users[].name}'    # 첫 번째 사용자 출력
kubectl config view -o jsonpath='{.users[*].name}'    # 사용자 리스트 조회
kubectl config get-contexts                          # 컨텍스트 리스트 출력
kubectl config current-context              # 현재 컨텍스트 출력
kubectl config use-context my-cluster-name  # my-cluster-name를 기본 컨텍스트로 설정

### 기본 인증을 지원하는 새로운 클러스터를 kubeconf에 추가한다
kubectl config set-credentials kubeuser/foo.kubernetes.com --username=kubeuser --password=kubepassword

### 해당 컨텍스트에서 모든 후속 kubectl 커맨드에 대한 네임스페이스를 영구적으로 저장한다
kubectl config set-context --current --namespace=ggckad-s2

### 특정 사용자와 네임스페이스를 사용하는 컨텍스트 설정
kubectl config set-context gce --user=cluster-admin --namespace=foo \
  && kubectl config use-context gce

kubectl config unset users.foo                       # foo 사용자 삭제