# Kubernetes Services Types : 

Kubernetes service types: 
    - ClusterIP (default)
     - NodePort 
      - LoadBalancer.


A NodePort is a type of Kubernetes Service that exposes your application to external traffic by opening a specific port on each node in the cluster.

Here’s how it works and when to use it:

🔍 What is a NodePort?
NodePort is one of the three main Kubernetes service types: ClusterIP (default), NodePort, and LoadBalancer.

It allows external clients to access your service by sending requests to a specific port on any node’s IP address.

Kubernetes automatically assigns a port from the range 30000–32767, or you can specify one manually.

🧭 How NodePort Works
When you create a NodePort service, Kubernetes:

Creates a ClusterIP service behind the scenes for internal routing.

Opens the specified port on every node in the cluster.

Routes incoming traffic from that port to the appropriate backend Pods.

✅ When to Use NodePort
Quick testing or development: Easy way to expose services without a cloud load balancer.

Bare-metal clusters: When cloud-native LoadBalancer isn’t available.

Simple external access: If you know the node IP and port, you can reach the service directly.

⚠️ Limitations
Manual IP and port management: You need to know the node’s IP and the assigned port.

Not ideal for production: Limited scalability and security compared to LoadBalancer or Ingress.

No built-in DNS or SSL termination: You’ll need additional configuration for HTTPS or domain routing.


