   22  kubectl describe get sa aws-pca-issuer -o yaml
   23  kubectl describe get sa aws-pca-issuer -o yaml -n aws-pca-issuer
   24  kubectl get sa aws-pca-issuer -o yaml -n aws-pca-issuer
   25  kubectl get certificate -n acm-pca-lab-demo
   26  kubectl get certificate -n acm-pca-lab-demo -w
   27  kubectl delete -f  eks-cert.yaml 
   28  kubectl apply-f eks-cert.yaml 
   29  kubectl apply -f eks-cert.yaml 
   30  kubectl get certificate -n acm-pca-lab-demo -w
   31  kubectl get secret -n acm-pca-lab-demo
   32  kubectl get certificate -n acm-pca-lab-demo eks-cert -o yaml
   33  kubectl get secret eks-example-cert -n acm-pca-lab-demo -o yaml
   34  kubectl get secret eks-example-cert -n acm-pca-lab-demo -o 'go-template={{index .data "tls.crt"}} | base64 --decode | openssl x509 -noout -text
   35  kubectl get secret eks-example-cert -n acm-pca-lab-demo -o 'go-template={{index .data "tls.crt"}}' | base64 --decode | openssl x509 -noout -text
   36  vi hello-world.yaml
   37  kubectl apply -f hello-world.yaml 
   38  vi hello-world.yaml
   39  kubectl apply -f hello-world.yaml 
   40  vi hello-world.yaml
   41  kubectl apply -f hello-world.yaml 
   42  vi hello-world.yaml
   43  kubectl apply -f hello-world.yaml 
   44  kubectl get pod acm-pca-lab-demo
   45  kubectl get pod -n acm-pca-lab-demo
   46  vi example-ingress.yaml
   47  kubectl get svc -n ingress-nginx
   48  vi example-ingress.yaml 
   49  kubectl apply -f example-ingress.yaml 
   50  kubectl get ingress -n acm-pca-lab-demo
   51  cd
   52  kubectl get pod -n acm-pca-lab-demo
   53  cd
   54  ls
   55  kubectl get certificate -n acm-pca-lab-demo
   56  kubectl get certificate -n acm-pca-lab-demo eks-cert -o yaml
   57  vi eks-cert.yaml 
   58  vi example-ingress.yaml 
   59  kubectl get ingress -n acm-pca-lab-demo
   60  kubectl apply -f example-ingress.yaml 
   61  kubectl get ingress -n acm-pca-lab-demo
   62  openssl s_client -showcerts -servername app.kloudln.com -connect app.kloudln.com:443
   63  kubectl get svc -n ingress-nginx
   64  vi eks-cert.yaml 
   65  vi example-ingress.yaml 
   66  kubectl get ingress-class
   67  kubectl get ingressclass
   68  vi example-ingress.yaml 
   69  kubectl apply -f example-ingress.yaml 
   70  kubectl delete -f example-ingress.yaml 
   71  kubectl apply -f example-ingress.yaml 
   72  cd
   73  ls
   74  vi eks-cert.yaml 
   75  kubectl get svc -n ingress-nginx
   76  vi example-ingress.yaml 
   77  vi example-ingress.yaml 
   78  vi example-ingress.yaml 
   79  kubectl apply -f example-ingress.yaml 
   80  kubectl get endpoints -n acm-pca-lab-demo
   81  vi hello-world.yaml 
   82  kubectl apply -f hello-world.yaml 
   83  kubectl get endpoints -n acm-pca-lab-demo
   84  vi hello-world.yaml 
   85  kubetl get svc -n acm-pca-lab-demo
   86  kubectl get svc -n acm-pca-lab-demo
   87  curl 10.100.238.244
   88  vi hello-world.yaml 
   89  kubectl apply -f hello-world.yaml 
   90  curl 10.100.238.244
   91  kubectl get pod -n acm-pca-lab-demo
   92  kubectl exec hello-world-664859d5c5-6tp9h  -n acm-pca-lab-demo -- curl localhost
   93  kubectl exec hello-world-664859d5c5-6tp9h  -n acm-pca-lab-demo -- curl localhost:8080
   94  kubectl exec hello-world-664859d5c5-6tp9h  -n acm-pca-lab-demo -- bash
   95  kubectl exec -it hello-world-664859d5c5-6tp9h  -n acm-pca-lab-demo -- bash
   96  vi hello-world.yaml 
   97  kubectl apply -f hello-world.yaml 
   98  vi example-ingress.yaml 
   99  kubectl apply -f example-ingress.yaml 
  100  vi eks-cert.yaml 
  101  kubectl apply -f eks-cert.yaml 
  102  vi example-ingress.yaml 
  103  kubectl apply -f example-ingress.yaml 
  104  openssl s_client -showcerts -servername app.kloudln.com -connect app.kloudln.com:443
  105  vi eks-cert.yaml 
  106  vi example-ingress.yaml 
  107  vi hello-world.yaml 
  108  ls
  109  vi cluster-issuer.yaml 
  110  vi get_helm.sh 
  111  sudo vi get_helm.sh 
  112  echo | openssl s_client -showcerts -servername app.kloudln.com -connect app.kloudln.com:443
  113  echo | openssl s_client -showcerts -servername app.kloudln.com -connect app.kloudln.com:443 | openssl x509 -inform x509 pem -noout -text
  114  echo | openssl s_client -showcerts -servername app.kloudln.com -connect app.kloudln.com:443 | openssl x509 -inform  pem -noout -text
  115  ls
  116  vi cluster-issuer.yaml 
  117  cd
  118  curl -o iam_policy.json https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.4.1/docs/install/iam_policy.json
  119  ls
  120  vi iam_policy.json 
  121  aws iam create-policy --policy-name AWSLoadBalancerControllerIAMPolicy --policy-document file://iam_policy.json 
  122  eksctl create iamserviceaccount --cluster=acm-pca-lab --namespace=kube-system --name=aws-load-balancer-controller --role-name "AmazonEKSLoadBalancerControllerRole --attach-policy-arn=arn:aws:iam::366425941000:policy/AWSLoadBalancerControllerIAMPolicy
  123  "
  124  eksctl create iamserviceaccount --cluster=acm-pca-lab --namespace=kube-system --name=aws-load-balancer-controller --role-name "AmazonEKSLoadBalancerControllerRole" --attach-policy-arn=arn:aws:iam::366425941000:policy/AWSLoadBalancerControllerIAMPolicy
  125  helm repo add eks https://aws.github.io/eks-charts
  126  helm upgrade --install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system --set clusterName=acm-pca-lab --set serviceAccount.create=false --set serviceAccount.name=aws-load-balancer-controller
  127  kubectl get pod -n kube-system
  128  kubectl get sa -n kube-system
  129  kubectl get deployment -n kube-system
  130  kubectl get pod -n kube-system
  131  kubectl describe deployment -n kube-system aws-load-balancer-controller
  132  kubectl describe deployment -n kube-system aws-load-balancer-controller
  133  kubectl get events
  134  kubectl get events -n kube-system
  135  cd
  136  kubectl get deployment -n kube-system
  137  kubectl get events
  138  kubectl get events -n kube-system
  139  aws iam create-policy     --policy-name AWSLoadBalancerControllerIAMPolicy     --policy-document file://iam_policy.json
  140    --cluster=acm-pca-lab   --namespace=kube-system   --name=aws-load-balancer-controller   --role-name "AmazonEKSLoadBalancerControllerRole"   --attach-policy-arn=arn:aws:iam::366425941000:policy/AWSLoadBalancerControllerIAMPolicy   --approve
  141  eksctl create iamserviceaccount   --cluster=acm-pca-lab   --namespace=kube-system   --name=aws-load-balancer-controller   --role-name "AmazonEKSLoadBalancerControllerRole"   --attach-policy-arn=arn:aws:iam::366425941000:policy/AWSLoadBalancerControllerIAMPolicy   --approve
  142  cd
  143  kubectl get events -n kube-system
  144  kubectl get pod -n kube-system
  145  kubectl get deployment -n kube-system
  146  helm list -n kube-system
  147  helm uninstall aws-load-balancer-controller -n kube-system
  148  kubectl get deployment -n kube-system
  149  helm upgrade --install aws-load-balancer-controller eks/aws-load-balancer-controller -n kube-system --set clusterName=acm-pca-lab --set serviceAccount.create=false --set serviceAccount.name=aws-load-balancer-controller
  150  kubectl get deployment -n kube-system
  151  vi nlb-tls-app.yaml
  152  vi nlb-tls-app.yaml
  153  echo $hostname
  154  hostname -i
  155  vi nlb-tls-app.yaml
  156  kubectl apply -f nlb-tls-app.yaml 
  157  kubectl get pod
  158  kubectl get pod -w
  159  kubectl get pod -w
  160  kubectl get svc -w
  161  kubectl get pod -w
  162  kubectl describe pod nlb-tls-app-547b78746-s5l8s 
  163  vi nlb-lab-tls.yaml
  164  kubectl apply -f nlb-tls-app.yaml 
  165  kubectl apply -f nlb-lab-tls.yaml 
  166  kubectl get certificate
  167  kubectl get pod -w
  168  kubectl describe pod nlb-tls-app-547b78746-s5l8s 
  169  vi nlb-lab-tls.yaml 
  170  kubectl apply -f nlb-lab-tls.yaml 
  171  openssl x509 -showcerts -connect nlb.kloudln.com:443 -servername nlb.kloudln.com
  172  openssl s_client -showcerts -connect nlb.kloudln.com:443 -servername nlb.kloudln.com
  173  kubectl delete -f nlb-lab-tls.yaml 
  174  kubectl apply -f nlb-lab-tls.yaml 
  175  vi nlb-lab-tls.yaml 
  176  openssl s_client -showcerts -connect nlb.kloudln.com:443 -servername nlb.kloudln.com
  177  echo | openssl s_client -showcerts -connect nlb.kloudln.com:443 -servername nlb.kloudln.com
  178  history
  179  vi nlb-lab-tls.yaml 
  180  kubectl get certificate
  181  kubectl describe certificate nlb-lab-tls-cert
  182  kubectl get pod
  183  kubectl delete pod nlb-tls-app-547b78746-s5l8s
  184  kubectl get pod
  185  echo | openssl s_client -showcerts -connect nlb.kloudln.com:443 -servername nlb.kloudln.com
  186  ls
  187  vi nlb-lab-tls.yaml 
  188  cat nlb-tls-app.yaml 
  189  ls
  190  cd
  191  vi nginx-deployment.yaml
  192  mv nginx-deployment.yaml echo-deployment.yaml 
  193  kubectl apply -f echo-deployment.yaml 
  194  kubectl get pod -w
  195  vi echo-service.yaml 
  196  cd
  197  ls
  198  vi echo-service.yaml
  199  vi echo-service.yaml
  200  vi echo-service.yaml
  201  vi .echo-service.yaml.swp 
  202  vi echo-service.yaml
  203  rm .echo-service.yaml.swp 
  204  vi echo-service.yaml
  205  kubectl apply -f echo-service.yaml 
  206  kubectl get svc -w
  207  echo | openssl s_client -showcerts -connect app.lab.kloudln.com:443 -servername app.lab.kloudln.com
  208  echo | openssl s_client -showcerts -connect app.lab.kloudln.com:443 -servername app.lab.kloudln.com | openssl x509 -inform PEM -noout -text
  209  cat echo-deployment.yaml 
  210  cat echo-service.yaml 
  211  kubectl create deployment nginx --image=nginx -o yaml --dry-run=client > nginx-deployment.yaml
  212  kubectl apply -f nginx-deployment.yaml 
  213  kubectl create service loadbalancer nginx --tcp=80:80
  214  kubectl get svc 
  215  kubectl edit svc nginx
  216  cd
  217  kubectl edit service nginx
  218  ls
  219  kubectl edit service nginx
  220  clear
  221  cat nginx-deployment.yaml 
  222  history
  223  kubectl get svc nginx -oyaml > nginx-service.yaml
  224  cat nginx-service.yaml 
  225  cd
  226  kubectl get pod -n acm-pca-lab-demo
  227  kubectl get certificate -n acm-pca-lab-demo
  228  kubectl get certificate, secret -n acm-pca-lab-demo
  229  kubectl get certificate,secret -n acm-pca-lab-demo
  230  kubectl config get contexts
  231  kubectl config get-context
  232  kubectl config get-contexts
  233  cd
  234  cp eks-cert.yaml eks-cert-multi-domain.yaml
  235  vi eks-cert-multi-domain.yaml 
  236  kubectl create namespace work
  237  kubectl apply -f eks-cert-multi-domain.yaml 
  238  kubectl get certificate -n work
  239  kubectl get secret -n work
  240  cp example-ingress.yaml work-ingress.yaml
  241  vi work-ingress.yaml 
  242  kubectl create deployment app-work -n work --image=httpd
  243  kubectl create service clusterip app-work --tcp=80:80 -n work
  244  kubectl apply -f work-ingress.yaml 
  245  kubectl get ingresss,pod,svc -n work
  246  kubectl get ingress,pod,svc -n work
  247  vi cluster-issuer.yaml 
  248  kubectl get awspcaclusterissuer 
  249  vi work-ingress.yaml 
  250  kubectl get svc -n ingress-nginx
  251  echo | openssl s_client -connect app.work.kloudln.com:443 -servername app.work.kloudln.com
  252  kubectl create deployment test-work -n work --image nginx
  253  kubectl create svc clusterip test-work --tcp=80:80 -n work
  254  vi work-ingress.yaml 
  255  kubectl apply -f work-ingress.yaml 
  256  kubectl get ingress -n work
  257  kubectl get svc -n ingress-nginx
  258  kubectl apply -f echo-deployment -n work
  259  kubectl apply -f echo-deployment.yaml -n work
  260  kubectl apply -f echo-service.yaml -n work
  261  vi work-ingress.yaml 
  262  kubectl apply -f work-ingress.yaml 
  263  kubectl get ingress -n work
  264  cd
  265  kubectl get pod
  266  kubectl get pod -n work
  267  kubectl get ingress -n work
  268  vi work-ingress.yaml 
  269  vi  eks-cert-multi-domain.yaml 
  270  ls
  271  vi  eks-cert-multi-domain.yaml 
  272  kubectl get namespaces
  273  kubectl get awspcaclusterissuer
  274  vi rolof-certificate-issuer.yaml
  275  mv rolof-certificate-issuer.yaml lms-cert.yaml
  276  vi rolof-certificate-issuer.yaml
  277  kubectl apply -f rolof-certificate-issuer.yaml 
  278  kubectl get awspcaissuer
  279  kubectl get awspcaclusterissuer
  280  vi lms-cert.yaml 
  281  kubectl apply -f lms-cert.yaml 
  282  kubectl create namespace lms
  283  kubectl apply -f lms-cert.yaml 
  284  kubectl get certificate -n lms
  285  kubectl get certificate -n lms
  286  kubectl get certificate -n lms
  287  kubectl get certificate -n lms -w
  288  kubectl describe certificate -n lms lms-cert
  289  vi rolof-certificate-issuer.yaml 
  290  aws sts get-caller-identity
  291  kubectl get certificate -n lms
  292  cd
  293  aws sts get-caller-identity
  294  kubectl get cert -n lms
  295  kubectl delete cert lms-cert -n lmis
  296  kubectl delete cert lms-cert -n lms
  297  kubectl apply -f lms-cert.yaml 
  298  kubectl get cert -n lms
  299  kubectl get cert -n lms -w
  300  kubectl describe cert lms -n lms
  301  kubectl delete cert lms-cert
  302  kubectl delete cert lms-cert -n lms
  303  kubectl get awspcaclusterissuer
  304  kubectl describe awspcaclusterissuer rolof-cert-issuer
  305  aws sts get-caller-identity
  306  kubectl get cert -n lms
  307  kubectl get certificate -n lms
  308  cd
  309  kubectl apply -f lms-cert.yaml 
  310  kubectl get certificate -n lms
  311  kubectl get certificate -n lms
  312  kubectl get event -n lms
  313  cd
  314  ls
  315  kubectl get sa -n aws-pca-issuer
  316  kubectl get role -n aws-pca-issuer
  317  kubectl get rolebinding -n aws-pca-issuer
  318  kubectl get pod -n aws-pca-issuer
  319  kubectl logs -f aws-pca-issuer-aws-privateca-issuer-5687976b7f-gfwkc  -n aws-pca-issuer
  320  kubectl apply -f rolof-certificate-issuer.yaml 
  321  kubectl delete -f rolof-certificate-issuer.yaml 
  322  kubectl get awspcaclusterissuer
  323  kubectl apply -f rolof-certificate-issuer.yaml 
  324  kubectl get awspcaclusterissuer
  325  vi lms-cert.yaml 
  326  kubectl get namespace lms
  327  kubectl create namespace lms
  328  vi lms-cert.yaml 
  329  kubectl apply -f lms-cert.yaml 
  330  ls -al pca-iam-policy.json 
  331  chown $(id -u):$(id -u) pca-iam-policy.json 
  332  sudo chown $(id -u):$(id -u) pca-iam-policy.json 
  333  cd
  334  ls
  335  kubectl get cert -n lms
  336  kubectl delete cert lms -n lms
  337  kubectl delete cert lms-cert -n lms
  338  vi lms-cert.yaml 
  339  vi eks-cert.yaml 
  340  vi lms-cert.yaml 
  341  kubectl apply -f lms-cert.yaml 
  342  kubectl get cert -n lms
  343  kubectl delete -f rolof-certificate-issuer.yaml 
  344  vi rolof-certificate-issuer.yaml
  345  kubectl apply -f rolof-certificate-issuer.yaml
  346  vi lms-cert.yaml 
  347  vi lms-cert.yaml 
  348  kubectl apply -f lms-cert.yaml 
  349  vi lms-cert.yaml 
  350  kubectl apply -f lms-cert.yaml 
  351  kubectl get cert -n lms
  352  cat cluster-issuer.yaml 
  353  cat rolof-certificate-issuer.yaml 
  354  kubectl delete -f lms-cert.yaml 
  355  vi lms-cert.yaml 
  356  kubectl delete -f lms-cert.yaml 
  357  kubectl get secret,cert -n lms
  358  kubectl get secret,cert -n lms
  359  vi lms-cert.yaml 
  360  kubectl delete -f lms-cert.yaml 
  361  kubectl get secret,cert -n lms
  362  kubectl delete secret/rolof-cert-secret -n lms
  363  kubectl delete namespace lms
  364  vi rolof-certificate-issuer.yaml 
  365  kubectl logs -f aws-pca-issuer-aws-privateca-issuer-5687976b7f-gfwkc  -n aws-pca-issuer
  366  vi pca-iam-policy.json 
  367  vi pca-iam-policy.json 
  368  pwd
  369  ls -al pca-iam-policy.json
  370  vi pca-iam-policy.json
  371  aws iam help
  372  aws iam put-role-policy help
  373  aws iam create-policy --policy-name AWSPCAIssuerIAMPolicy --policy-document file://pca-iam-policy.json
  374  aws iam put-role-policy --policy-name AWSPCAIssuerIAMPolicy --policy-document file://pca-iam-policy.json
  375  cd
  376  aws iam create-policy --put-role-policy AWSPCAIssuerIAMPolicy --policy-document file://pca-iam-policy.json --role-name eksctl-acm-pca-lab-addon-iamserviceaccount-a-Role1-MPX8CP92SJ8R
  377  aws iam create-policy --put-role-policy AWSPCAIssuerIAMPolicy --policy-document file://pca-iam-policy.json --role-name eksctl-acm-pca-lab-addon-iamserviceaccount-a-Role1-MPX8CP92SJ8R --policy-name AWSPCAIssuerIAMPolicy
  378  aws iam help
  379  aws iam put-role-policy help
  380  aws iam put-role-policy AWSPCAIssuerIAMPolicy --policy-document file://pca-iam-policy.json --role-name eksctl-acm-pca-lab-addon-iamserviceaccount-a-Role1-MPX8CP92SJ8R --policy-name AWSPCAIssuerIAMPolicy
  381  aws iam put-role-policy --policy-document file://pca-iam-policy.json --role-name eksctl-acm-pca-lab-addon-iamserviceaccount-a-Role1-MPX8CP92SJ8R --policy-name AWSPCAIssuerIAMPolicy
  382  kubectl get certificate -n lms
  383  kubectl get certificate -n lms
  384  kubectl delete -f rolof-certificate-issuer.yaml 
  385  kubectl apply -f rolof-certificate-issuer.yaml 
  386  kubectl get certificate -n lms
  387  kubectl delete -f lms-cert.yaml 
  388  kubectl apply -f lms-cert.yaml 
  389  kubectl get certificate -n lms
  390  kubectl get certificate -n lms
  391  vi lms-cert.yaml 
  392  kubectl get secret -n lms
  393  vi lms-cert.yaml 
  394  kubectl apply -f lms-cert.yaml 
  395  kubectl get secret -n lms
  396  kubectl get secret -n lms
  397  kubectl get secret -n lms
  398  kubectl delete secret rolof-cert-secret  -n lms
  399  kubectl get secret -n lms
  400  kubectl apply -f lms-cert.yaml 
  401  kubectl get secret -n lms
  402  kubectl delete -f lms-cert.yaml 
  403  kubectl apply -f lms-cert.yaml 
  404  kubectl get secret -n lms
  405  kubectl get secret -n lms
  406  kubectl delete -f lms-cert.yaml 
  407  vi lms-cert.yaml 
  408  kubectl apply -f lms-cert.yaml 
  409  kubectl get secret -n lms
  410  kubectl get cert -n lms
  411  kubectl create deployment lms-admin -n lms --image=httpd
  412  kubectl create svc lms-admin -n lms --tcp=80:80
  413  kubectl create svc clusterip lms-admin -n lms --tcp=80:80
  414  kubectl create ingress lms --help
  415  kubectl create ingress lms --class=nginx --rule=admin.lms.kloudln.com/*=lms-admin:80,tls=lms-cert-secret --dry-run=client -o yaml > lms-ingress.yaml
  416  vi lms-ingress.yaml 
  417  vi lms-ingress.yaml 
  418  kubectl apply -f lms-ingress.yaml 
  419  kubectl get ingress -n lms
  420  vi lms-ingress.yaml 
  421  vi lms-cert.yaml 
  422  vi lms-ingress.yaml 
  423  kubectl apply -f lms-ingress.yaml 
  424  kubectl get pod -n aws-pca-issuer
  425  kubectl get pod,sa -n aws-pca-issuer
  426  kubectl logs -f pod/aws-pca-issuer-aws-privateca-issuer-5687976b7f-gfwkc  -n aws-pca-issuer
  427  kubectl get secret
  428  kubectl get secret nlb-tls-app-secret -o yaml
  429  kubectl get secret nlb-tls-app-secret -o jsonpath '{.data.ca.crt}''
  430  kubectl get secret nlb-tls-app-secret -o jsonpath '{.data.ca.crt}'
  431  kubectl get secret nlb-tls-app-secret -o jsonpath "{ .data.ca.crt }"
  432  kubectl get secret nlb-tls-app-secret -o jsonpath "{ .data } {.ca.crt}"
  433  kubectl get secret nlb-tls-app-secret -o jsonpath "{ .data[].ca.crt}"
  434  kubectl get secret nlb-tls-app-secret -o jsonpath "{ .data }"
  435  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data }"
  436  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data.ca.crt }"
  437  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data[].ca.crt }"
  438  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data[] .ca.crt }"
  439  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data } {.ca.crt }"
  440  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data[*].ca.crt }"
  441  kubectl get secret nlb-tls-app-secret -o jsonpath="{ .data[*].ca.crt }"
  442  kubectl get secret nlb-tls-app-secret -o 'go-template={{index .data "tls.crt" }}'
  443  kubectl get secret nlb-tls-app-secret -o 'go-template={{index .data "tls.crt" }}' | base64 -d
  444  kubectl get secret nlb-tls-app-secret -o 'go-template={{index .data "tls.crt" }}' | base64 -d > ca.crt
  445  openssl x509 -in ca.crt -noout -text
  446  cd
  447  kubectl get pod
  448  kubectl delete -f echo-deployment.yaml 
  449  kubectl delete -f echo-service.yaml 
  450  kubectl get pod
  451  kubectl get svc
  452  vi nlb-lab-tls.yaml 
  453  vi nlb-tls-app.yaml 
  454  kubectl delete -f nlb-lab-tls.yaml 
  455  kubectl delete -f nlb-tls-app.yaml 
  456  kubectl get svc
  457  ls nginx-deployment.yaml 
  458  vi nginx-deployment.yaml
  459  vi nginx-service.yaml 
  460  kubectl delete -f nginx-service.yaml 
  461  kubectl get pod,svc
  462  kubectl get pod
  463  kubectl get ingress
  464  kubectl get deployment 
  465  vi nginx-deployment.yaml 
  466  kubectl delete -f nginx-deployment.yaml 
  467  kubectl get deployment 
  468  kubectl get pod
  469  kubectl get namespaces
  470  kubectl get pod,svc,ingress,secret -n work
  471  kubectl get pod,svc,ingress,secret,cert -n work
  472  vi echo-deployment.yaml 
  473  vi echo-service.yaml 
  474  kubectl delete -f echo-deployment.yaml -n work
  475  kubectl delete -f echo-service.yaml -n work
  476  kubectl get pod,svc,ingress,secret,cert -n work
  477  ls
  478  kubectl delete deployment app-work -n work
  479  kubectl delete deployment test-work -n work
  480  kubectl delete service test-work -n work
  481  kubectl delete service app-work -n work
  482  vi work-ingress.yaml 
  483  kubectl delete -f work-ingress.yaml 
  484  kubectl get namespace
  485  kubectl delete namespace work
  486  kubectl get pod,svc,secret,cert -n lms
  487  kubectl delete deployment lms-admin -n lms
  488  kubectl delete svc -n lms-admin -n lms
  489  kubectl delete svc lms-admin -n lms
  490  kubectl get pod,svc,secret,cert -n lms
  491  kubectl delete -f lms-ingress.yaml 
  492  kubectl delete -f lms-cert.yaml 
  493  kubectl delete namespace lms
  494  kubectl get namespaces
  495  kubectl get pod,svc,ingress,cert -n acm-pca-lab-demo
  496  kubectl delete -f hello-world.yaml 
  497  kubectl delete -f example-ingress.yaml 
  498  kubectl get cert -n acm-pca-lab-demo
  499  kubectl delete -f eks-cert.yaml 
  500  kubectl get cert -n acm-pca-lab-demo
  501  cd
  502  ls
  503  git status
  504  yum install git -y
  505  sudo yum install git -y
  506  git status
  507  git remote add origin https://github.com/tutugodfrey/acm-pca-lab-k8s.git
  508  git init
  509  git remote add origin https://github.com/tutugodfrey/acm-pca-lab-k8s.git
  510  git branch
  511  git status
  512  ls
  513  mkdir pca-k8s-2
  514  mv *.yaml pca-k8s-2
  515  ls pca-k8s-2
  516  mv *.json pca-k8s-2
  517  mv .git/ pca-k8s-2/
  518  ls
  519  rm pca-iam-policy.json’ 
  520  touch pca-k8s-2/README.md
  521  history > pca-k8s-2/README.md
