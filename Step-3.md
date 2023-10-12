## Step 3: Configuring OIDC to perform Authentication

### Associate OpenID Authentication to EKS Cluster
<pre>
  eksctl utils associate-iam-oidc-provider --cluster $cluster_name --approve
</pre>
