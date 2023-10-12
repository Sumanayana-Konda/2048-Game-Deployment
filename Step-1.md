## Step 1:  Creation of EKS cluster

### To create EKS cluster utilizing eksctl follow these steps:
<pre>
eksctl create cluster --name demo-cluster --region us-east-1 --fargate
</pre>
### To delete the cluster
<pre>
eksctl delete cluster --name demo-cluster --region us-east-1
</pre>

