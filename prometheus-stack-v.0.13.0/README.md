1. prometheus helm chart 를 offline 운영환경 에서 사용하기에는 dependency 와 version up이 너무 빠름.
2. https://github.com/prometheus-operator/kube-prometheus 에 kube-prometheus-stack을 사용하면 적어도 kubernetes version에 stable을 맞출 수 있음.
3. 해당 chart에서 몇몇 파일들을 수정하여 custom helm chart를 만듦

-- 기존과 변경점 --
# 모든 application 공통 변경점.
common change: 
1. version 관련 값들 전부 제거
2. image, namespace, replicas, limits resources 변수 값 처리.
3. networkPolicy.yaml 삭제.
4. AlertRule 들 삭제.
5. RecordRule prometheus-prometheusRule.yaml 로 통합.


# 기존 kube-prometheus stack의 manifest 내용과 변경 된 file
Chagne file List:
1. grafana-config.yaml 에서 UTC를 KTC로 변경
2. kubeStateMetrics-serviceMonitor.yaml 에서 regex: pod,endpoint 삭제
3. nodeExporter-daemoset.yaml 에서 --collector.systemd 및 systemd 정규식 표현 추가 (kubelet,containerd)
4. prometheus-clusterole.yaml 에서 https://github.com/techiescamp/kubernetes-prometheus/blob/master/clusterRole.yaml 참조하여 변경