
How many containers exist in a pod ? 
 - kubectl get pod webapp -o jsonpath='{.spec.containers[*].name}' | wc -w
   
kubectl get pod webapp: Retrieves the Pod named webapp.

-o jsonpath='{...}': Formats the output using a JSONPath expression, which lets you extract specific fields from the Pod’s JSON definition.

{.spec.containers[*].name}: Navigates to the Pod’s spec → containers array → pulls the name of each container.

🧠 Here's how it works:
When you run kubectl get pod, you're querying the Kubernetes control plane.

The control plane stores Pod definitions and status in etcd, a distributed key-value store.

The API server exposes this data in JSON format, which kubectl can filter using jsonpath.
