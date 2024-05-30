#### Pod scheduling

Pod restarts due to liveness or readiness failuares are handled internally by
the node.

Based on its resource requirements.

200m = 200milicores => 20% of 1 core
MiB=mebibytes =>

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: timeserver
spec:
  replicas: 3
  selector:
    matchLabels:
      pod: timeserver-pod
  template:
    metadata:
      labels:
        pod: timeserver-pod
    spec:
      containers:
      - name: timserver-container
        image: docker.io/wdeniss/timeserver:3
        resources:
          requests:
            cpu: 200m
            memory: 250Mi
          limits:
            cpu: 300m
            memory: 400Mi

```
