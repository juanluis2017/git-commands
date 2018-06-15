##### Docker commands 

- despligue version instalada de docker

``` docker version ```

- generar imagen en docker

``` docker build ./aci-helloworld -t aci-tutorial-app ```



docker images
```docker images ```

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
