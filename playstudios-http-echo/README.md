##Description
This helm chart deploys the [`http-echo`] docker image in local kubernetes using Helm 3/Kind/Docker Desktop Windows.

My changes are in 2 files "values.yaml", "templates\deployment.yaml"

##Completed the basic setup guidance

##Installing the Chart (Powershell)
helm install playstudios-echo-app ".\playstudios-http-echo" --namespace ingress-nginx


##My local test result
PS C:\Users\HNC\PlayStudios\Devops-Challenge> helm install playstudios-echo-app ".\playstudios-http-echo" --namespace ingress-nginx
NAME: playstudios-echo-app
LAST DEPLOYED: Mon Jan 17 22:42:52 2022
NAMESPACE: ingress-nginx
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  http://localhost/


PS C:\Users\HNC\PlayStudios\Devops-Challenge\playstudios-http-echo> kubectl -n ingress-nginx get svc,pods,deployments,ingress
NAME                                                 TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)                      AGE
service/ingress-nginx-controller                     NodePort    10.96.88.135   <none>        80:30687/TCP,443:30112/TCP   3d12h
service/ingress-nginx-controller-admission           ClusterIP   10.96.13.69    <none>        443/TCP                      3d12h
service/playstudios-echo-app-playstudios-http-echo   ClusterIP   10.96.86.252   <none>        5678/TCP                     11s

NAME                                                              READY   STATUS      RESTARTS   AGE
pod/ingress-nginx-admission-create-s6v9b                          0/1     Completed   0          3d12h
pod/ingress-nginx-admission-patch-hmkdj                           0/1     Completed   0          3d12h
pod/ingress-nginx-controller-5d848765b5-lkcgt                     1/1     Running     5          3d12h
pod/playstudios-echo-app-playstudios-http-echo-5656dc5d59-2d7gj   1/1     Running     0          11s

NAME                                                         READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/ingress-nginx-controller                     1/1     1            1           3d12h
deployment.apps/playstudios-echo-app-playstudios-http-echo   1/1     1            1           11s

NAME                                                                   CLASS    HOSTS       ADDRESS   PORTS   AGE
ingress.networking.k8s.io/playstudios-echo-app-playstudios-http-echo   <none>   localhost             80      11s

PS C:\Users\HNC\PlayStudios\Devops-Challenge\playstudios-http-echo> curl.exe localhost:8080
Hello from Playstudios team...
