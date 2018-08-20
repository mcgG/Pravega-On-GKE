# Pravega on GKE

1. Go to GKE console and choose `Create Cluster` 
   > To run both parvega and prevega serach cluster, it is recommended to create a 6 nodes, 1vCPU for each node \( memory in total\) clsuter, you can expand the resource anytime if you met with _unschedulable issue._
2. `gcloud sdk` is needed to access to GKE, please follow [this](https://cloud.google.com/sdk/docs/quickstart-linux) link. 
   > Note: gcloud sdk does not support Cygwin
3. After cluster created, click \`Connect\`, and  
   ![](/assets/connect1)

4. Run this command from your local terminal  
   ![](/assets/connect2.png)

5. As shown  
   ![](/assets/connect3.png)

6. Install `kubectl` with `gcloud components install kubectl`

7. Install `Helm` on GKE

   1. ```bash
      # helm config
      > helm init
      > kubectl create serviceaccount --namespace kube-system tiller
      > kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
      > kubectl patch deploy --namespace kube-system tiller-deploy -p '{"spec":{"template":{"spec":{"serviceAccount":"tiller"}}}}'
      ```

8. Check physical nodes in your cluster

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

9. To deploy pravega-cluster please refer to [pravega-operator](https://github.com/pravega/pravega-operator)

10. To deploy pravega-search-operator please refer to [pravega-search-operator](https://asdstash.isus.emc.com/projects/NAUT/repos/platform/browse/go/pravega-search-operator/src/dellemc.com/pravega-search-operator?at=feature-pravega-search-operator)



