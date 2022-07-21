# Tanzu Integration with vRealize Operations Manager and vRealize Log Insights

###  please note that these configuration should be revised before adding them into production

_______________________________________________________________________________________________

#### environment
- vSphere 7
- vRealize Operations Manager 8.6.3
-- Kubernetes Management Pack 1.7.0.19827046
- vRealize Log Insights 8.8.0
- Prometheus 1.75.0 - using tanzu package
- Fluent Bit 2.27.0 - using tanzu package

_______________________________________________________________________________________________

#### vRealize Operations Manager
For this demo we're using vRealize Operations Manager Kubernetes Management Pack native integration with Prometheus collector (providing metrics)

The default integrations is providing platform (k8s) metrics

In order to provide applications specific metrics we need to perform the following actions

#### deploy telegraf sidecar
examples
- manifest/hello-observability-logs-v3.yaml
- manifest/hello-observability-v2.yaml
- manifest/complete-demo.yaml (this is the weaveworks demo app)

#### define prometheus target (pointing to the telegraf sidecar)
example
- manifest/prometheus-data-values.yaml

_______________________________________________________________________________________________

#### vRealize Log Insights
For this demo we're using vRealize Log Insights and Fluent Bit which is installed as a daemonset configured to send logging to vRealize Log Insights

_______________________________________________________________________________________________

### Prometheus
Instructions can be found [here](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.5/vmware-tanzu-kubernetes-grid-15/GUID-packages-prometheus.html)

example
- manifest/prometheus-data-values.yaml

_______________________________________________________________________________________________

### Fluent Bit
Instructions can be found [here](https://docs.vmware.com/en/VMware-Tanzu-Kubernetes-Grid/1.5/vmware-tanzu-kubernetes-grid-15/GUID-packages-logging-fluentbit.html)

example
- manifest/fluent-bit-data-values.yaml