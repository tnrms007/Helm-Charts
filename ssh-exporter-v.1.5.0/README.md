1. GitHub - treydock/ssh_exporter 를 그대로 사용하기에는 kubernetes에서 사용 할 수 없어서 custom manifest 만들고 helm chart 로 만듦
2. Kuberentes Resources: Configmap 2개, serviceAccount 1개,service 1개, depolyment 1개
3. _helpers 등은 구조가 간단하기때문에 만들지 않음.
4. ssh_exporter는 말그대로 ssh 원격연결후 특정명령어로 실제 서버에 접근이 되는가를 검증하는 exporter로 다양한 로직을 원하면 custom exporter 만들면 된다. 
5. helm install ssh-exporter ./helm-chart-dir -n [namespace]
6. 해당 Chart는 helm hook, argocd syncwave가 적용되어있음.