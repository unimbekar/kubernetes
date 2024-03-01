<pre>
history
    1  minikube start
    2  kubectl get all
    3  kubectl create deploy myweb --image=nginx --replicas=3
    4  kubectl get all
    5  history
    6  kubectl get all
    7  kubectl create -h
    8  kubectl create -h | less
    9  kubectl get all
   10  kubectl get pods
   11  history
   12  kubectl completion -h | less
   13  source <(kubectl completion bash)
   14  kubectl create deployment -h | less
   15  history
   16  kubectl get all
   17  kubectl delete pod myweb-9794cbc77-5mrpk 
   18  kubectl get all
   19  kubectl get pods myweb-9794cbc77-q6r89 -o yaml | less
   20  history
   21  kubectl get all
   22  kubectl scale deployment myweb --replicas 4
   23  kubectl get all
   24  history
   25  kubectl get all
   26  kubectl get all --show-labels
   27  kubectl get all --selector app=myweb
   28  history
   29  kubectl describe pod myweb-9794cbc77-q6r89 | less
   30  kubectl get deployments.apps myweb -o yaml | less
   31  kubectl create deploy mynginx --image=nginx --dry-run=client -o yaml > mydeploy.yaml
   32  vim mydeploy.yaml 
   33  kubectl explain deploy
   34  kubectl explain deploys.spec | less
   35  kubectl explain deploy.spec | less
   36  vim mydeploy.yaml 
   37  history
   38  kubectl crete -f mydeploy.yaml 
   39  kubectl create -f mydeploy.yaml 
   40  kubectl delete -f mydeploy.yaml 
   41  kubectl apply -f mydeploy.yaml 
   42  kubectl get all
   43  vim mydeploy.yaml 
   44  kubectl apply -f mydeploy.yaml 
   45  kubectl get all
   46  kubectl get deploy
   47  kubectl get deploy myweb -o yaml > myweb.yaml
   48  vim myweb.yaml 
   49  kubectl get ns
   50  kubectl get pods
   51  kubectl get pods -n kube-system
   52  kubectl create ns secret
   53  kubectl get ns
   54  kubectl run anotherweb --image=nginx -n secret
   55  kubectl get pods
   56  kubectl get pods -n secret
   57  kubectl get pods -A
   58  history
   59  kubectl create deploy mydb --image=mariadb --replicas=3
   60  kubectl get all
   61  kubectl describe pod mydb-7bbb588c85-9ftd9 
   62  kubectl logs mydb-7bbb588c85-v4jz8 
   63  kubectl get all --selector app=mariadb
   64  kubectl get all --selector app=mydb
   65  kubectl set env deploy/mydb MARIADB_ROOT_PASSWORD=secret
   66  kubectl get all --selector app=mydb
   67  kubectl set env --help | less
   68  history
   69  kubectl get pods -o wide
   70  kubectl create deployment nginxsvc --image=nginx
   71  kubectl get all --selector app=nginxsvc
   72  kubectl scale deploy nginxsvc --replicas=3
   73  kubectl get all --selector app=nginxsvc
   74  kubectl expose deploy nginxsvc --port=80
   75  kubectl get all --selector app=nginxsvc
   76  curl 10.106.95.234
   77  minikube ip
   78  kubectl describe svc nginxsvc 
   79  kubectl get endpoints
   80  kubectl get svc
   81  minikube ssh
   82  kubectl edit svc nginxsvc 
   83  kubectl get svc
   84  minikube ip
   85  curl 192.168.49.2:32628
   86  history
   87  kubectl explain pod.spec.volumes | less
   88  vim morevolumes.yaml 
   89  kubectl apply -f morevolumes.yaml 
   90  kubectl get pods morevol 
   91  kubectl describe pod morevol | less
   92  kubectl exec -it morevol -c centos1 -- touch /centos1/test
   93  kubectl exec -it morevol -c centos2 -- ls -l /centos2
   94  ls
   95  vim pv.yaml
   96  kubectl apply -f pv.yaml 
   97  kubectl get all
   98  kubectl get pv,pvc
   99  vim pvc.yaml 
  100  kubectl apply -f pvc.yaml 
  101  kubectl get pv,pvc
  102  vim pv-pod.yaml 
  103  kubectl apply -f pv-pod.yaml 
  104  vim pv-pod.yaml 
  105  kubectl exec -it pv-pod -- touch /usr/share/nginx/html/myfile.no
  106  kubectl exec -it pv-pod -- ls -l /usr/share/nginx/html/
  107  kubectl get pv,pvc
  108  kubectl describe pv pvc-cfc7a3be-0f05-42a1-aa59-ea9576d4b818 
  109  minikube ssh
  110  history
  111  ls
  112  cat resources.txt 
  113  kubectl create deploy mynewdb --image=mysql --replicas=3
  114  kubectl get pods --selector app=mynewdb
  115  kubectl create cm mynewdbvars --from-literal=MYSQL_ROOT_PASSWORD=password
  116  kubectl describe cm mynewdbvars 
  117  kubectl get pods --selector app=mynewdb
  118  kubectl set env --from=configmap/mynewdbvars deploy/mynewdb
  119  kubectl get all --selector app=mynewdb
  120  kubectl get pods mynewdb-6884d5cccd-x8lmg -o yaml | less
  121  kubectl create secret -h | less
  122  kubectl create secret generic -h | less
  123  kubectl create secret generic --from-literal=MYSQL_ROOT_PASSWORD=password
  124  kubectl create secret generic mysecretpw --from-literal=MYSQL_ROOT_PASSWORD=password
  125  kubectl describe secret mysecretpw 
  126  kubectl get secret mysecretpw -o yaml
  127  echo cGFzc3dvcmQ= | base64 -d
  128  reset
  129  kubectl set env --from=secret/mysecretpw deploy/mynewdb
  130  kubectl get pods mynewdb-c567d4cfc-phdz7 -o yaml | less
  131  kubectl get svc
  132  kubectl get all --selector app=nginxsvc
  133  minikube addons list
  134  minikube addon enable ingress
  135  minikube addons enable ingress
  136  kubectl get pods -n kube-system 
  137  kubectl get ns
  138  kubectl get pods -n ingress-nginx 
  139  kubectl create ing -h | less
  140  #kubectl create ingress simple --rule="foo.com/bar=svc1:8080,tls=my-cert"
  141  kubectl get svc
  142  kubectl create ing nginxsvc --rule="myapp.info=nginxsvc:80"
  143  kubectl create ing nginxsvc --rule="myapp.info/=nginxsvc:80"
  144  sudo vim /etc/hosts
  145  minikube ip
  146  sudo vim /etc/hosts
  147  curl myapp.info
  148  kubectl describe ing nginxsvc 
  149  less resources.txt 
  150  history
</pre>
