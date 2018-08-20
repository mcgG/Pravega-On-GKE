# GKE

1. Go to GKE console and choose `Create Cluster` 
   > To run both parvega and prevega serach cluster, it is recommended to create a 6 nodes, 1vCPU for each node \( memory in total\) clsuter, you can expand the resource anytime if you met with _unschedulable issue._
2. `gcloud sdk` is needed to access to GKE, please follow [this](https://cloud.google.com/sdk/docs/quickstart-linux) link. 
   1. > Note: gcloud sdk does not support Cygwin
3. After cluster created, click \`Connect\`, and   
   ![](/assets/connect1)

4. Run this command from your local terminal  
   ![](/assets/connect2.png)

5. As shown
   ![](/assets/connect3.png)
6. Install `kubectl` with `gcloud components install kubectl`
7. Check physical nodes in your cluster

   ```bash
      > Kubectl get nodes

      # Example output
      # NAME                                       STATUS    ROLES     AGE       VERSION
      # gke-cluster-1-default-pool-73bd74ac-d674   Ready     <none>    25m       v1.9.7-gke.5
      # gke-cluster-1-default-pool-73bd74ac-fbk3   Ready     <none>    25m       v1.9.7-gke.5
      # gke-cluster-1-default-pool-73bd74ac-kj2n   Ready     <none>    25m       v1.9.7-gke.5
      # gke-cluster-1-default-pool-73bd74ac-m7x0   Ready     <none>    25m       v1.9.7-gke.5
      # gke-cluster-1-default-pool-73bd74ac-q2h1   Ready     <none>    25m       v1.9.7-gke.5
      # gke-cluster-1-default-pool-73bd74ac-vlgb   Ready     <none>    25m       v1.9.7-gke.5
   ```

8. To deploy pravega-cluster please refer to [this](https://github.com/pravega/pravega-operator)
9. To deploy pravega-search-operator please refer to [this](https://asdstash.isus.emc.com/projects/NAUT/repos/platform/browse/go/pravega-search-operator?at=refs%2Fheads%2Ffeature-pravega-search-operator)



