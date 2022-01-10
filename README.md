**0 - Configure kubectl first**

**1 - Downloading and installing istioctl:**

https://istio.io/latest/docs/setup/getting-started/#download
https://istio.io/latest/docs/setup/getting-started/#install


**2 - Instaling manifests into the cluster:**

(demo profile contains all the features)
*istioctl install --set profile=demo -y*

**3 - Add a namespace label to instruct Istio to automatically inject Envoy sidecar proxies when you deploy your application:**

*kubectl label namespace app istio-injection=enabled*

**4 - Basic validation:**

istioctl analyze --namespace app

**5 - If you are using minikube:**

5.1 - you must change istio-ingresgateway service type from LoadBalancer to NodePort (namespace is 'istio-system');

5.2 - Get the NodePort for the ports you want to access like "http2";

5.3 - Get the Ip using "minikube ip";

**5 - Install addons folder**

**6 - Installing kiali:**

https://istio.io/latest/docs/tasks/observability/kiali/

*istioctl dashboard kiali*

**7 - Installing jaeger:**

https://istio.io/latest/docs/tasks/observability/distributed-tracing/jaeger/

*istioctl dashboard jaeger*
