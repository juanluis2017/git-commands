##### Docker commands 

- despligue version instalada de docker

``` docker version ```

- generar imagen en docker

``` docker build ./aci-helloworld -t aci-tutorial-app ```



docker images
```docker images ```

Desplegar imagen localmente

``` docker run -d -p 8080:80 aci-tutorial-app ```

Run the container locally

lista imagenes disponibles

```docker ps ```

realiza stop a contenedor

```docker stop 'containerID'```


``` docker ps -a ```


- Elimina una imagen de docker

```docker rmi 'id imagen'```

docker run hello-world


- Descarga y crea imagen dockerizada servidor NGingx

```docker pull nginx```

- Levanta servidor NGingx

```docker run -p 80:80 ngingx```

- Elimina contenedores

```docker rm```

elimina las imagenes docker 

```docker rmi ```  

#### Subir Imagenes a Docker Containeri Registry ACR

ejemplo
https://docs.microsoft.com/en-us/azure/container-instances/container-instances-tutorial-prepare-acr

para subir una imagen existe a azure container registry se debe seguir los siguientes pasos a travez de Azure CLI

1 abrir consola de powershell
2 realizar login mediante el comando az login
3 copiar url y codigo para autentificarse en portal https://microsoft.com/devicelogin
4 una vez logueado se debe loguear a su vez en al ACR a traves del comando az acr login --name [nombre del ACR creado]

#### Lista de contenedores registrados

```az acr show --name <acrName> --query loginServer --output table ```
  
5 para subir la imagen docker al registry se debe ingresar el siguiente commando

``` docker tag aci-tutorial-app <acrLoginServer>/aci-tutorial-app:v1 ```

6  hacer login en Contenedor de imagenes azure

``` docker login myregistry.azurecr.io -u xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -p myPassword ```


7  subir imagen docker a contenedor de registro ACR


```docker push <acrLoginServer>/aci-tutorial-app:v1 ```

 ###### Crear grupo de recursos
 
``` az group create --name myResourceGroup --location eastus ```

``` az acr create --resource-group myResourceGroup --name <acrName> --sku Basic --admin-enabled true ```





