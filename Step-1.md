## Step 1:  Creation of EKS cluster

### To create EKS cluster utilizing eksctl follow these steps:
<pre>
eksctl create cluster --name demo-cluster --region us-east-1 --fargate
</pre>
### To delete the cluster
<pre>
eksctl delete cluster --name demo-cluster --region us-east-1
</pre>

#### Use this command to get the details of the cluster that is created.
<pre>
aws eks update-kubeconfig --name kubernetes-project --region us-east-1 
</pre>
