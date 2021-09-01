1. clonar o projeto 
git clone https://github.com/luan-prates/pfa-docker.git

2. bildar as imagens

Node
```cd pfa-docker/node```
```docker build -t pfadocker/pfanode .```

Nginx
```cd ../nginx```
```docker build -t pfadocker/pfanginx .  ```

3. Criar a network
```docker network create pfa``` 


4. rodar os conteines

```docker run -d --network=pfa --name=pfanode -v $(pwd):/usr/src/app pfadocker/pfanode node index.js```
```docker run -d --network=pfa -p 8080:80 pfadocker/pfanginx```
