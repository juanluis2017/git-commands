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


Escalar un Cluster de Kubernetes

``` az aks scale --name [clusterName] --resource-group [myResourceGroup] --agent-count [numero de instancias] ```

Obtener la version actual de Kubernetes

``` az aks get-versions --name [ClusterName] --resource-group [myResourceGroup] --output table ```

Actualizar version de Kubernetes

``` az aks get-versions --name [ClusterName] --resource-group [myResourceGroup] --output table ```


Levantar Servidor Kubernetes de forma Local

``` az aks browse --resource-group [myResourceGroup]  --name [AKSName]  ```


Desplegar Credenciales 

``` az aks get-credentials –resource-group yourResourceGroup –name yourAKSname ```








