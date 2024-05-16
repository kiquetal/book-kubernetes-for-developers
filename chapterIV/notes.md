#### Chapter IV- Automated operations

The health of the containers is determined by two separate probes: liveness, which determines whether the container is running,
and readiness, which indicates when the container is able to receive traffic.

### Readiness example

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: timeserver
spec:
  replicas: 3
  selector:
    matchLabels:
      pod: timeserver-prod
  template:
    metadata:
      labels:
        pod: timesever-prod
    spec:
      containers:
        - name: timeserver-container
          image: docker.io/wdenniss/timesever:1
          readinessProbe:
            initialDelaySeconds: 15
	    periodSeconds: 30
            httpGet:
              path: /
	      port: 80
              scheme: HTTP
            timeoutSeconds: 2
            failureThreshold: 1
            successThreshold: 1

```


