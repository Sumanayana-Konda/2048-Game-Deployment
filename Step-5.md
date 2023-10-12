## Step 5: Deploying the Load balancer

### User helm to create and attach the load balancer
<pre>
  helm install aws-load-balancer-controller eks/aws-load-balancer-controller \            
  -n kube-system \
  --set clusterName=<your-cluster-name> \
  --set serviceAccount.create=false \
  --set serviceAccount.name=aws-load-balancer-controller \
  --set region=<region> \
  --set vpcId=<your-vpc-id>
</pre>


#### After running this helm install command with the appropriate values for your cluster, it will deploy the AWS Load Balancer Controller 
#### into the specified namespace of your EKS cluster. The controller will then start managing load balancers based on the configurations you've provided.
