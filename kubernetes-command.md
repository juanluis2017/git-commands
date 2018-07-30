Definiciones Generales

Docker: Docker is a software technology that provides operating-system-level virtualization to easily deploy applications in a sandbox (called containers) to run on Linux.

Images: An image is a read-only template with the necessary instructions required for the application to run.

Containers: Provides an isolated environment in which an app along with its environment is run.

Kubernetes: Kubernetes is an open source system for managing containerized applications across multiple hosts, providing basic mechanisms for deployment, maintenance, and scaling of applications.

Pods: A Pod is the basic building block of Kubernetes and represents a executable unit of work. A Pod usually contains a single container.

Services: A service tells other pods about the services your application provides.

Deployments: A Deployment controller provides declarative updates for Pods

Kubernetes Manifest file: Kubernetes manifests with deployments, services and pods can be defined in json or yaml. The file extensions .yaml, .yml, and .json can be used.


#### Kubernetes

Kubernetes es un sistema open source (GitHub) creado por Google para la gestión de aplicaciones en contenedores, un sistema de 
orquestación para contenedores Docker, permitiendo acciones como programar el despliegue, escalado y
la monitorización de nuestros contenedores, entre muchas otras más.



##### Tutoriales Paso a Paso



![Comenzando con Contenedores y Kubernetes](https://github.com/Azure/blackbelt-aks-hackfest/tree/master/labs/day1-labs)



![CI/CD con Aks y Vsts](https://almvm.azurewebsites.net/labs/vstsextend/kubernetes/)


Creacion de un cluster Kubernetes AKS

``` az aks create --resource-group myAKSCluster --name myAKSCluster --node-count 1 --generate-ssh-keys ```


Escalar un Cluster de Kubernetes

``` az aks scale --name [clusterName] --resource-group [myResourceGroup] --agent-count [numero de instancias] ```

Obtener la version actual de Kubernetes

``` az aks get-versions --name [ClusterName] --resource-group [myResourceGroup] --output table ```

Actualizar version de Kubernetes

``` az aks get-versions --name [ClusterName] --resource-group [myResourceGroup] --output table ```


Levantar Servidor Kubernetes de forma Local

``` az aks browse --resource-group [myResourceGroup]  --name [AKSName]  ```


Desplegar Credenciales 

``` az aks get-credentials –resource-group yourResourceGroup –-name yourAKSname ```

Revision de servicio en kubernetes

``` kubectl get service mhc-front --watch ```

 scale pod
 
``` kubectl scale --replicas=5 deployment/azure-vote-front ```

scale by metrics

``` kubectl autoscale deployment [site to scale] --cpu-percent=50 --min=3 --max=10 ```

retorna consumo actul de los distintos pods que esta en modo run

``` kubectl get hpa  ```


entrega la configuracion del cluster actualmente conectado

``` kubectl config current-context  ```

modifica el contexto a otro cluster

``` kubectl config use-context my-cluster-name ```

#### Get commands with basic output
kubectl get services                          # List all services in the namespace
kubectl get pods --all-namespaces             # List all pods in all namespaces
kubectl get pods -o wide                      # List all pods in the namespace, with more details
kubectl get deployment my-dep                 # List a particular deployment
kubectl get pods --include-uninitialized      # List all pods in the namespace, including uninitialized ones

#### Describe commands with verbose output
kubectl describe nodes my-node
kubectl describe pods my-pod

kubectl get services --sort-by=.metadata.name # List Services Sorted by Name

#### List pods Sorted by Restart Count
kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'

#### Get the version label of all pods with label app=cassandra
kubectl get pods --selector=app=cassandra rc -o \
  jsonpath='{.items[*].metadata.labels.version}'

#### Get all running pods in the namespace
kubectl get pods --field-selector=status.phase=Running

#### Get ExternalIPs of all nodes
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="ExternalIP")].address}'

#### List Names of Pods that belong to Particular RC
#### "jq" command useful for transformations that are too complex for jsonpath, it can be found at https://stedolan.github.io/jq/
sel=${$(kubectl get rc my-rc --output=json | jq -j '.spec.selector | to_entries | .[] | "\(.key)=\(.value),"')%?}
echo $(kubectl get pods --selector=$sel --output=jsonpath={.items..metadata.name})

#### Check which nodes are ready
JSONPATH='{range .items[*]}{@.metadata.name}:{range @.status.conditions[*]}{@.type}={@.status};{end}{end}' \
 && kubectl get nodes -o jsonpath="$JSONPATH" | grep "Ready=True"

#### List all Secrets currently in use by a pod
kubectl get pods -o json | jq '.items[].spec.containers[].env[]?.valueFrom.secretKeyRef.name' | grep -v null | sort | uniq

#### List Events sorted by timestamp
kubectl get events --sort-by=.metadata.creationTimestamp



creacion de cluster kubernetes

```az aks create -g RG_automotriz_AKS -n AutomotrizAKSCluster --generate-ssh-keys ```

lista cluster kubernetes

```az aks list -o table ```


lista de subredes

```az network vnet subnet list --resource-group RG_VPN--vnet-name VNET-AZR-DMZ-DEV--query [].id --output tsv```

creacion de cluster kubernetes asociado a una red especifica

``` az aks create --resource-group RG_AutomotrizAKS  --name AutomotrizAKS  --network-plugin azure --vnet-subnet-id 293c1183-8b08-4bbd-9f28-e042fd037525 --docker-bridge-address 172.17.0.1/16 --dns-service-ip 10.2.0.10 --service-cidr 10.2.0.0/24 ```

obtener credenciales de kubernetes

``` az aks get-credentials --resource-group RG_automotriz_AKS --name AutomotrizAKS ```

levantar Kubernetes

```az aks browse --resource-group RG_automotriz_AKS --name AutomotrizAKS ```
