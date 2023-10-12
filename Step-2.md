## Step-2: Creating Fargate profile and deploying the app.

### Create Fargate Profile:

<pre>
  eksctl create fargateprofile \
    --cluster kubernetes-project \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace game-2048
</pre>

### OR
sample_app.md
<pre>
  apiVersion: apps/v1
kind: Deployment
metadata:
  name: eks-sample-linux-deployment
  labels:
    app: eks-sample-linux-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: eks-sample-linux-app
  template:
    metadata:
      labels:
        app: eks-sample-linux-app
    spec:
      affinity:
        nodeAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
            nodeSelectorTerms:
            - matchExpressions:
              - key: kubernetes.io/arch
                operator: In
                values:
                - amd64
                - arm64
      containers:
      - name: nginx
        image: public.ecr.aws/nginx/nginx:1.23
        ports:
        - name: http
          containerPort: 80
        imagePullPolicy: IfNotPresent
      nodeSelector:
        kubernetes.io/os: linux
</pre>

### Use this command to get the details about pod 2048 or the game deployed
<pre>
  kubectl get pods -n game-2048
</pre>
