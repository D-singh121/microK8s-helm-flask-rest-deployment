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
$ helm create python-flask-helm-folder
![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/0e331d16-dd97-407b-8d46-21f120a88c15)

## Modify the Chart.yaml file
  comment the app version line
  ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/7d4f5d9c-1231-4949-a34c-757ae121e82f)
  
## Modify the values.yaml file 
  change the image name , port number and service-type to NodePort
  ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/f15acca0-1bd8-4d4e-8ff6-3c03576f5c21)
  ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/73f665ba-dfdc-4039-a914-4b8dc11ea9c3)
  
  on template/deployment.yaml comment the redenessProbe and livenessProbe  sections.
  ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/f1a6574a-1bb1-426f-8a8d-f8e5f38a9324)

## Install the helm chart folder
  $ helm install my-python-helm-chart  python-flask-helm-folder
  ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/9c2f9b48-fc65-4819-a3cf-f0a7bb22c9a4)

## Last step to uninstall helm chart and stop all deployment in single command
 $ helm uninstall my-python-helm-chart
 ![image](https://github.com/D-singh121/microK8s-helm-flask-rest-deployment/assets/108144751/df119f8e-13c0-4238-b135-a7f8129a8658)





  

