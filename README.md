## 1. Build Docker image 
```commandline
docker build -t python-rest-api .
```

## 2. Run Docker image
```commandline
docker run -p 9001:9001 python-rest-api
```

## we have deployed this flask server to the microK8s with helm chart
![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/c7c23d33-face-4fba-b39f-eb9be0744cad)

## First we have to create Helm folder with containing all the neccessry files
$ helm create python-flask-rest-api
