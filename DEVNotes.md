# Devnotes

* Prep your fork for go project so your go import contains your checkins
* git clone git@github.com:kubernetes/kubernetes.git
Fork the k8 repo to personal
* git remote add fork MYFORK
[Optional]
Just to keep the workflow consistent with other languages
* git remote rename origin upstream 
* git remote rename fork origin
[Checkout]
Assuming your keep origin and fork as is with no remote rename:
* git checkout -b fix-stuff
* git commit -m "some comment"
* git push fork fix-stuff
Reset master 
git fetch origin
git reset--hard origin/master

# Build
make 

# Built binary
_output:

```
.
|-- bin -> /opt/opensource/worksplace/go/src/github.com/kubernetes/kubernetes/_output/local/bin/linux/amd64
|-- dockerized
|   |-- bin
|   |   `-- linux
|   |       `-- amd64
|   |           |-- conversion-gen
|   |           |-- deepcopy-gen
|   |           |-- defaulter-gen
|   |           |-- e2e_node.test
|   |           |-- e2e.test
|   |           |-- gendocs
|   |           |-- genfeddocs
|   |           |-- genkubedocs
|   |           |-- genman
|   |           |-- genswaggertypedocs
|   |           |-- genyaml
|   |           |-- ginkgo
|   |           |-- hyperkube
|   |           |-- kubeadm
|   |           |-- kube-apiserver
|   |           |-- kube-controller-manager
|   |           |-- kubectl
|   |           |-- kube-discovery
|   |           |-- kube-dns
|   |           |-- kubelet
|   |           |-- kubemark
|   |           |-- kube-proxy
|   |           |-- kube-scheduler
|   |           |-- linkcheck
|   |           |-- mungedocs
|   |           |-- openapi-gen
|   |           |-- src
|   |           `-- teststale
|   `-- go
|-- images
|   `-- kube-build:build-c73d952f76-4-v1.7.1-2
|       |-- Dockerfile
|       |-- localtime
|       |-- rsyncd.password
|       `-- rsyncd.sh
`-- local
    |-- bin
    |   `-- linux
    |       `-- amd64
    |           |-- conversion-gen
    |           |-- deepcopy-gen
    |           |-- defaulter-gen
    |           |-- openapi-gen
    |           `-- teststale
    `-- go
        |-- bin
        |   |-- conversion-gen
        |   |-- deepcopy-gen
        |   |-- defaulter-gen
        |   |-- gendocs
        |   |-- genfeddocs
        |   |-- genkubedocs
        |   |-- genman
        |   |-- genswaggertypedocs
        |   |-- genyaml
        |   |-- ginkgo
        |   |-- hyperkube
        |   |-- kubeadm
        |   |-- kube-apiserver
        |   |-- kube-controller-manager
        |   |-- kube-discovery
        |   |-- kube-dns
        |   |-- kubelet
        |   |-- kubemark
        |   |-- kube-proxy
        |   |-- kube-scheduler
        |   |-- linkcheck
        |   |-- mungedocs
        |   |-- openapi-gen
        |   |-- src
        |   `-- teststale
        |-- pkg
        |   |-- linux_amd64
        |   |   `-- k8s.io
        |   |       `-- kubernetes
        |   |           |-- cmd
        |   |           |   |-- genutils.a
        |   |           |   |-- kube-apiserver
        |   |           |   |   |-- app
        |   |           |   |   |   `-- options.a
        |   |           |   |   `-- app.a
        |   |           |   |-- kube-controller-manager
        |   |           |   |   |-- app
        |   |           |   |   |   `-- options.a
        |   |           |   |   `-- app.a
        |   |           |   |-- kubelet
        |   |           |   |   |-- app
        |   |           |   |   |   `-- options.a
        |   |           |   |   `-- app.a
        |   |           |   |-- kube-proxy
        |   |           |   |   |-- app
        |   |           |   |   |   `-- options.a
        |   |           |   |   `-- app.a
        |   |           |   `-- libs
        |   |           |       `-- go2idl
        |   |           |           |-- conversion-gen
        |   |           |           |   `-- generators.a
        |   |           |           `-- openapi-gen
        |   |           |               `-- generators.a
        |   |           |-- federation
        |   |           |   |-- apis
        |   |           |   |   |-- core
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   `-- v1.a
        |   |           |   |   |-- core.a
        |   |           |   |   |-- federation
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1beta1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   `-- federation.a
        |   |           |   |-- client
        |   |           |   |   |-- cache.a
        |   |           |   |   `-- clientset_generated
        |   |           |   |       |-- federation_internalclientset
        |   |           |   |       |   `-- typed
        |   |           |   |       |       |-- core
        |   |           |   |       |       |   `-- internalversion.a
        |   |           |   |       |       |-- extensions
        |   |           |   |       |       |   `-- internalversion.a
        |   |           |   |       |       `-- federation
        |   |           |   |       |           `-- internalversion.a
        |   |           |   |       |-- federation_internalclientset.a
        |   |           |   |       |-- federation_release_1_5
        |   |           |   |       |   `-- typed
        |   |           |   |       |       |-- core
        |   |           |   |       |       |   `-- v1.a
        |   |           |   |       |       |-- extensions
        |   |           |   |       |       |   `-- v1beta1.a
        |   |           |   |       |       `-- federation
        |   |           |   |       |           `-- v1beta1.a
        |   |           |   |       `-- federation_release_1_5.a
        |   |           |   |-- cmd
        |   |           |   |   |-- federation-apiserver
        |   |           |   |   |   |-- app
        |   |           |   |   |   |   `-- options.a
        |   |           |   |   |   `-- app.a
        |   |           |   |   `-- federation-controller-manager
        |   |           |   |       |-- app
        |   |           |   |       |   `-- options.a
        |   |           |   |       `-- app.a
        |   |           |   |-- pkg
        |   |           |   |   |-- dnsprovider
        |   |           |   |   |   |-- providers
        |   |           |   |   |   |   |-- aws
        |   |           |   |   |   |   |   |-- route53
        |   |           |   |   |   |   |   |   `-- stubs.a
        |   |           |   |   |   |   |   `-- route53.a
        |   |           |   |   |   |   `-- google
        |   |           |   |   |   |       |-- clouddns
        |   |           |   |   |   |       |   |-- internal
        |   |           |   |   |   |       |   |   |-- interfaces.a
        |   |           |   |   |   |       |   |   `-- stubs.a
        |   |           |   |   |   |       |   `-- internal.a
        |   |           |   |   |   |       `-- clouddns.a
        |   |           |   |   |   `-- rrstype.a
        |   |           |   |   |-- dnsprovider.a
        |   |           |   |   `-- federation-controller
        |   |           |   |       |-- cluster.a
        |   |           |   |       |-- daemonset.a
        |   |           |   |       |-- deployment.a
        |   |           |   |       |-- ingress.a
        |   |           |   |       |-- namespace.a
        |   |           |   |       |-- replicaset.a
        |   |           |   |       |-- secret.a
        |   |           |   |       |-- service.a
        |   |           |   |       |-- util
        |   |           |   |       |   |-- deletionhelper.a
        |   |           |   |       |   |-- eventsink.a
        |   |           |   |       |   |-- planner.a
        |   |           |   |       |   `-- podanalyzer.a
        |   |           |   |       `-- util.a
        |   |           |   `-- registry
        |   |           |       |-- cluster
        |   |           |       |   `-- etcd.a
        |   |           |       `-- cluster.a
        |   |           |-- pkg
        |   |           |   |-- admission.a
        |   |           |   |-- api
        |   |           |   |   |-- annotations.a
        |   |           |   |   |-- endpoints.a
        |   |           |   |   |-- errors
        |   |           |   |   |   `-- storage.a
        |   |           |   |   |-- errors.a
        |   |           |   |   |-- events.a
        |   |           |   |   |-- install.a
        |   |           |   |   |-- meta
        |   |           |   |   |   `-- metatypes.a
        |   |           |   |   |-- meta.a
        |   |           |   |   |-- pod.a
        |   |           |   |   |-- resource.a
        |   |           |   |   |-- rest.a
        |   |           |   |   |-- service.a
        |   |           |   |   |-- unversioned
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- unversioned.a
        |   |           |   |   |-- util.a
        |   |           |   |   |-- v1.a
        |   |           |   |   |-- validation
        |   |           |   |   |   `-- path.a
        |   |           |   |   `-- validation.a
        |   |           |   |-- api.a
        |   |           |   |-- apimachinery
        |   |           |   |   |-- announced.a
        |   |           |   |   `-- registered.a
        |   |           |   |-- apimachinery.a
        |   |           |   |-- apis
        |   |           |   |   |-- abac
        |   |           |   |   |   |-- latest.a
        |   |           |   |   |   |-- v0.a
        |   |           |   |   |   `-- v1beta1.a
        |   |           |   |   |-- abac.a
        |   |           |   |   |-- apps
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1alpha1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- apps.a
        |   |           |   |   |-- authentication
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   `-- v1beta1.a
        |   |           |   |   |-- authentication.a
        |   |           |   |   |-- authorization
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1beta1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- authorization.a
        |   |           |   |   |-- autoscaling
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- autoscaling.a
        |   |           |   |   |-- batch
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1.a
        |   |           |   |   |   |-- v2alpha1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- batch.a
        |   |           |   |   |-- certificates
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1alpha1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- certificates.a
        |   |           |   |   |-- componentconfig
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   `-- v1alpha1.a
        |   |           |   |   |-- componentconfig.a
        |   |           |   |   |-- extensions
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1beta1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- extensions.a
        |   |           |   |   |-- imagepolicy
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   `-- v1alpha1.a
        |   |           |   |   |-- imagepolicy.a
        |   |           |   |   |-- policy
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1alpha1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- policy.a
        |   |           |   |   |-- rbac
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- v1alpha1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   |-- rbac.a
        |   |           |   |   |-- storage
        |   |           |   |   |   |-- install.a
        |   |           |   |   |   |-- util.a
        |   |           |   |   |   |-- v1beta1.a
        |   |           |   |   |   `-- validation.a
        |   |           |   |   `-- storage.a
        |   |           |   |-- apiserver
        |   |           |   |   |-- authenticator.a
        |   |           |   |   |-- filters.a
        |   |           |   |   |-- metrics.a
        |   |           |   |   |-- openapi.a
        |   |           |   |   `-- request.a
        |   |           |   |-- apiserver.a
        |   |           |   |-- auth
        |   |           |   |   |-- authenticator
        |   |           |   |   |   `-- bearertoken.a
        |   |           |   |   |-- authenticator.a
        |   |           |   |   |-- authorizer
        |   |           |   |   |   |-- abac.a
        |   |           |   |   |   `-- union.a
        |   |           |   |   |-- authorizer.a
        |   |           |   |   |-- group.a
        |   |           |   |   |-- handlers.a
        |   |           |   |   `-- user.a
        |   |           |   |-- capabilities.a
        |   |           |   |-- client
        |   |           |   |   |-- cache.a
        |   |           |   |   |-- chaosclient.a
        |   |           |   |   |-- clientset_generated
        |   |           |   |   |   |-- internalclientset
        |   |           |   |   |   |   |-- fake.a
        |   |           |   |   |   |   `-- typed
        |   |           |   |   |   |       |-- apps
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- authentication
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- authorization
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- autoscaling
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- batch
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- certificates
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- core
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- extensions
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- policy
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       |-- rbac
        |   |           |   |   |   |       |   |-- internalversion
        |   |           |   |   |   |       |   |   `-- fake.a
        |   |           |   |   |   |       |   `-- internalversion.a
        |   |           |   |   |   |       `-- storage
        |   |           |   |   |   |           |-- internalversion
        |   |           |   |   |   |           |   `-- fake.a
        |   |           |   |   |   |           `-- internalversion.a
        |   |           |   |   |   |-- internalclientset.a
        |   |           |   |   |   |-- release_1_5
        |   |           |   |   |   |   `-- typed
        |   |           |   |   |   |       |-- apps
        |   |           |   |   |   |       |   `-- v1alpha1.a
        |   |           |   |   |   |       |-- authentication
        |   |           |   |   |   |       |   `-- v1beta1.a
        |   |           |   |   |   |       |-- authorization
        |   |           |   |   |   |       |   `-- v1beta1.a
        |   |           |   |   |   |       |-- autoscaling
        |   |           |   |   |   |       |   `-- v1.a
        |   |           |   |   |   |       |-- batch
        |   |           |   |   |   |       |   |-- v1.a
        |   |           |   |   |   |       |   `-- v2alpha1.a
        |   |           |   |   |   |       |-- certificates
        |   |           |   |   |   |       |   `-- v1alpha1.a
        |   |           |   |   |   |       |-- core
        |   |           |   |   |   |       |   `-- v1.a
        |   |           |   |   |   |       |-- extensions
        |   |           |   |   |   |       |   `-- v1beta1.a
        |   |           |   |   |   |       |-- policy
        |   |           |   |   |   |       |   `-- v1alpha1.a
        |   |           |   |   |   |       |-- rbac
        |   |           |   |   |   |       |   `-- v1alpha1.a
        |   |           |   |   |   |       `-- storage
        |   |           |   |   |   |           `-- v1beta1.a
        |   |           |   |   |   `-- release_1_5.a
        |   |           |   |   |-- leaderelection
        |   |           |   |   |   `-- resourcelock.a
        |   |           |   |   |-- leaderelection.a
        |   |           |   |   |-- metrics
        |   |           |   |   |   `-- prometheus.a
        |   |           |   |   |-- metrics.a
        |   |           |   |   |-- record.a
        |   |           |   |   |-- restclient.a
        |   |           |   |   |-- retry.a
        |   |           |   |   |-- testing
        |   |           |   |   |   `-- core.a
        |   |           |   |   |-- transport.a
        |   |           |   |   |-- typed
        |   |           |   |   |   |-- discovery
        |   |           |   |   |   |   `-- fake.a
        |   |           |   |   |   |-- discovery.a
        |   |           |   |   |   `-- dynamic.a
        |   |           |   |   |-- unversioned
        |   |           |   |   |   |-- auth.a
        |   |           |   |   |   |-- clientcmd
        |   |           |   |   |   |   |-- api
        |   |           |   |   |   |   |   |-- latest.a
        |   |           |   |   |   |   |   `-- v1.a
        |   |           |   |   |   |   `-- api.a
        |   |           |   |   |   |-- clientcmd.a
        |   |           |   |   |   |-- portforward.a
        |   |           |   |   |   `-- remotecommand.a
        |   |           |   |   `-- unversioned.a
        |   |           |   |-- cloudprovider
        |   |           |   |   |-- providers
        |   |           |   |   |   |-- aws.a
        |   |           |   |   |   |-- azure.a
        |   |           |   |   |   |-- cloudstack.a
        |   |           |   |   |   |-- gce.a
        |   |           |   |   |   |-- mesos.a
        |   |           |   |   |   |-- openstack.a
        |   |           |   |   |   |-- ovirt.a
        |   |           |   |   |   |-- rackspace.a
        |   |           |   |   |   `-- vsphere.a
        |   |           |   |   `-- providers.a
        |   |           |   |-- cloudprovider.a
        |   |           |   |-- controller
        |   |           |   |   |-- certificates.a
        |   |           |   |   |-- daemon.a
        |   |           |   |   |-- deployment
        |   |           |   |   |   `-- util.a
        |   |           |   |   |-- deployment.a
        |   |           |   |   |-- disruption.a
        |   |           |   |   |-- endpoint.a
        |   |           |   |   |-- garbagecollector
        |   |           |   |   |   `-- metaonly.a
        |   |           |   |   |-- garbagecollector.a
        |   |           |   |   |-- informers.a
        |   |           |   |   |-- job.a
        |   |           |   |   |-- namespace.a
        |   |           |   |   |-- node.a
        |   |           |   |   |-- petset.a
        |   |           |   |   |-- podautoscaler
        |   |           |   |   |   `-- metrics.a
        |   |           |   |   |-- podautoscaler.a
        |   |           |   |   |-- podgc.a
        |   |           |   |   |-- replicaset.a
        |   |           |   |   |-- replication.a
        |   |           |   |   |-- resourcequota.a
        |   |           |   |   |-- route.a
        |   |           |   |   |-- scheduledjob.a
        |   |           |   |   |-- service.a
        |   |           |   |   |-- serviceaccount.a
        |   |           |   |   `-- volume
        |   |           |   |       |-- attachdetach
        |   |           |   |       |   |-- cache.a
        |   |           |   |       |   |-- populator.a
        |   |           |   |       |   |-- reconciler.a
        |   |           |   |       |   `-- statusupdater.a
        |   |           |   |       |-- attachdetach.a
        |   |           |   |       `-- persistentvolume.a
        |   |           |   |-- controller.a
        |   |           |   |-- conversion
        |   |           |   |   `-- queryparams.a
        |   |           |   |-- conversion.a
        |   |           |   |-- credentialprovider
        |   |           |   |   |-- aws.a
        |   |           |   |   `-- gcp.a
        |   |           |   |-- credentialprovider.a
        |   |           |   |-- fieldpath.a
        |   |           |   |-- fields.a
        |   |           |   |-- generated
        |   |           |   |   `-- openapi.a
        |   |           |   |-- genericapiserver
        |   |           |   |   |-- authorizer.a
        |   |           |   |   |-- filters.a
        |   |           |   |   |-- mux.a
        |   |           |   |   |-- openapi
        |   |           |   |   |   `-- common.a
        |   |           |   |   |-- openapi.a
        |   |           |   |   |-- options.a
        |   |           |   |   |-- routes
        |   |           |   |   |   `-- data
        |   |           |   |   |       `-- swagger.a
        |   |           |   |   |-- routes.a
        |   |           |   |   `-- validation.a
        |   |           |   |-- genericapiserver.a
        |   |           |   |-- healthz.a
        |   |           |   |-- httplog.a
        |   |           |   |-- kubectl
        |   |           |   |   |-- cmd
        |   |           |   |   |   |-- config.a
        |   |           |   |   |   |-- rollout.a
        |   |           |   |   |   |-- set.a
        |   |           |   |   |   |-- templates.a
        |   |           |   |   |   |-- util
        |   |           |   |   |   |   `-- editor.a
        |   |           |   |   |   `-- util.a
        |   |           |   |   |-- cmd.a
        |   |           |   |   |-- metricsutil.a
        |   |           |   |   `-- resource.a
        |   |           |   |-- kubectl.a
        |   |           |   |-- kubelet
        |   |           |   |   |-- api
        |   |           |   |   |   `-- v1alpha1
        |   |           |   |   |       |-- runtime.a
        |   |           |   |   |       `-- stats.a
        |   |           |   |   |-- api.a
        |   |           |   |   |-- cadvisor
        |   |           |   |   |   `-- testing.a
        |   |           |   |   |-- cadvisor.a
        |   |           |   |   |-- client.a
        |   |           |   |   |-- cm.a
        |   |           |   |   |-- config.a
        |   |           |   |   |-- container
        |   |           |   |   |   `-- testing.a
        |   |           |   |   |-- container.a
        |   |           |   |   |-- custommetrics.a
        |   |           |   |   |-- dockershim
        |   |           |   |   |   `-- remote.a
        |   |           |   |   |-- dockershim.a
        |   |           |   |   |-- dockertools.a
        |   |           |   |   |-- envvars.a
        |   |           |   |   |-- events.a
        |   |           |   |   |-- eviction.a
        |   |           |   |   |-- images.a
        |   |           |   |   |-- kuberuntime.a
        |   |           |   |   |-- leaky.a
        |   |           |   |   |-- lifecycle.a
        |   |           |   |   |-- metrics.a
        |   |           |   |   |-- network
        |   |           |   |   |   |-- cni.a
        |   |           |   |   |   |-- exec.a
        |   |           |   |   |   |-- hairpin.a
        |   |           |   |   |   |-- hostport.a
        |   |           |   |   |   `-- kubenet.a
        |   |           |   |   |-- network.a
        |   |           |   |   |-- pleg.a
        |   |           |   |   |-- pod.a
        |   |           |   |   |-- prober
        |   |           |   |   |   `-- results.a
        |   |           |   |   |-- prober.a
        |   |           |   |   |-- qos.a
        |   |           |   |   |-- remote.a
        |   |           |   |   |-- rkt.a
        |   |           |   |   |-- server
        |   |           |   |   |   |-- portforward.a
        |   |           |   |   |   |-- remotecommand.a
        |   |           |   |   |   |-- stats.a
        |   |           |   |   |   `-- streaming.a
        |   |           |   |   |-- server.a
        |   |           |   |   |-- status.a
        |   |           |   |   |-- sysctl.a
        |   |           |   |   |-- types.a
        |   |           |   |   |-- util
        |   |           |   |   |   |-- cache.a
        |   |           |   |   |   |-- csr.a
        |   |           |   |   |   |-- format.a
        |   |           |   |   |   |-- ioutils.a
        |   |           |   |   |   |-- queue.a
        |   |           |   |   |   `-- sliceutils.a
        |   |           |   |   |-- volumemanager
        |   |           |   |   |   |-- cache.a
        |   |           |   |   |   |-- populator.a
        |   |           |   |   |   `-- reconciler.a
        |   |           |   |   `-- volumemanager.a
        |   |           |   |-- kubelet.a
        |   |           |   |-- kubemark.a
        |   |           |   |-- labels.a
        |   |           |   |-- master
        |   |           |   |   |-- ports.a
        |   |           |   |   `-- thirdparty.a
        |   |           |   |-- master.a
        |   |           |   |-- probe
        |   |           |   |   |-- exec.a
        |   |           |   |   |-- http.a
        |   |           |   |   `-- tcp.a
        |   |           |   |-- probe.a
        |   |           |   |-- proxy
        |   |           |   |   |-- config.a
        |   |           |   |   |-- healthcheck.a
        |   |           |   |   |-- iptables.a
        |   |           |   |   `-- userspace.a
        |   |           |   |-- proxy.a
        |   |           |   |-- quota
        |   |           |   |   |-- evaluator
        |   |           |   |   |   `-- core.a
        |   |           |   |   |-- generic.a
        |   |           |   |   `-- install.a
        |   |           |   |-- quota.a
        |   |           |   |-- registry
        |   |           |   |   |-- apps
        |   |           |   |   |   |-- petset
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- petset.a
        |   |           |   |   |   `-- rest.a
        |   |           |   |   |-- authentication
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   `-- tokenreview.a
        |   |           |   |   |-- authorization
        |   |           |   |   |   |-- localsubjectaccessreview.a
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   |-- selfsubjectaccessreview.a
        |   |           |   |   |   |-- subjectaccessreview.a
        |   |           |   |   |   `-- util.a
        |   |           |   |   |-- autoscaling
        |   |           |   |   |   |-- horizontalpodautoscaler
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- horizontalpodautoscaler.a
        |   |           |   |   |   `-- rest.a
        |   |           |   |   |-- batch
        |   |           |   |   |   |-- job
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- job.a
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   |-- scheduledjob
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   `-- scheduledjob.a
        |   |           |   |   |-- cachesize.a
        |   |           |   |   |-- certificates
        |   |           |   |   |   |-- certificates
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- certificates.a
        |   |           |   |   |   `-- rest.a
        |   |           |   |   |-- core
        |   |           |   |   |   |-- componentstatus.a
        |   |           |   |   |   |-- configmap
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- configmap.a
        |   |           |   |   |   |-- controller
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- controller.a
        |   |           |   |   |   |-- endpoint
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- endpoint.a
        |   |           |   |   |   |-- event
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- event.a
        |   |           |   |   |   |-- limitrange
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- limitrange.a
        |   |           |   |   |   |-- namespace
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- namespace.a
        |   |           |   |   |   |-- node
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- rest.a
        |   |           |   |   |   |-- node.a
        |   |           |   |   |   |-- persistentvolume
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- persistentvolume.a
        |   |           |   |   |   |-- persistentvolumeclaim
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- persistentvolumeclaim.a
        |   |           |   |   |   |-- pod
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- rest.a
        |   |           |   |   |   |-- pod.a
        |   |           |   |   |   |-- podtemplate
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- podtemplate.a
        |   |           |   |   |   |-- rangeallocation.a
        |   |           |   |   |   |-- resourcequota
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- resourcequota.a
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   |-- secret
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- secret.a
        |   |           |   |   |   |-- service
        |   |           |   |   |   |   |-- allocator
        |   |           |   |   |   |   |   `-- etcd.a
        |   |           |   |   |   |   |-- allocator.a
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   |-- ipallocator
        |   |           |   |   |   |   |   `-- controller.a
        |   |           |   |   |   |   |-- ipallocator.a
        |   |           |   |   |   |   |-- portallocator
        |   |           |   |   |   |   |   `-- controller.a
        |   |           |   |   |   |   `-- portallocator.a
        |   |           |   |   |   |-- service.a
        |   |           |   |   |   |-- serviceaccount
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   `-- serviceaccount.a
        |   |           |   |   |-- extensions
        |   |           |   |   |   |-- controller
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- daemonset
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- daemonset.a
        |   |           |   |   |   |-- deployment
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- deployment.a
        |   |           |   |   |   |-- ingress
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- ingress.a
        |   |           |   |   |   |-- networkpolicy
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- networkpolicy.a
        |   |           |   |   |   |-- podsecuritypolicy
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- podsecuritypolicy.a
        |   |           |   |   |   |-- replicaset
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- replicaset.a
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   |-- thirdpartyresource
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- thirdpartyresource.a
        |   |           |   |   |   |-- thirdpartyresourcedata
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   `-- thirdpartyresourcedata.a
        |   |           |   |   |-- generic
        |   |           |   |   |   |-- registry.a
        |   |           |   |   |   `-- rest.a
        |   |           |   |   |-- generic.a
        |   |           |   |   |-- policy
        |   |           |   |   |   |-- poddisruptionbudget
        |   |           |   |   |   |   `-- etcd.a
        |   |           |   |   |   |-- poddisruptionbudget.a
        |   |           |   |   |   `-- rest.a
        |   |           |   |   |-- rbac
        |   |           |   |   |   |-- clusterrole
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- policybased.a
        |   |           |   |   |   |-- clusterrole.a
        |   |           |   |   |   |-- clusterrolebinding
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- policybased.a
        |   |           |   |   |   |-- clusterrolebinding.a
        |   |           |   |   |   |-- rest.a
        |   |           |   |   |   |-- role
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- policybased.a
        |   |           |   |   |   |-- role.a
        |   |           |   |   |   |-- rolebinding
        |   |           |   |   |   |   |-- etcd.a
        |   |           |   |   |   |   `-- policybased.a
        |   |           |   |   |   `-- rolebinding.a
        |   |           |   |   |-- rbac.a
        |   |           |   |   `-- storage
        |   |           |   |       |-- rest.a
        |   |           |   |       |-- storageclass
        |   |           |   |       |   `-- etcd.a
        |   |           |   |       `-- storageclass.a
        |   |           |   |-- routes.a
        |   |           |   |-- runtime
        |   |           |   |   |-- serializer
        |   |           |   |   |   |-- json.a
        |   |           |   |   |   |-- protobuf.a
        |   |           |   |   |   |-- recognizer.a
        |   |           |   |   |   |-- streaming.a
        |   |           |   |   |   `-- versioning.a
        |   |           |   |   `-- serializer.a
        |   |           |   |-- runtime.a
        |   |           |   |-- security
        |   |           |   |   |-- apparmor.a
        |   |           |   |   |-- podsecuritypolicy
        |   |           |   |   |   |-- apparmor.a
        |   |           |   |   |   |-- capabilities.a
        |   |           |   |   |   |-- group.a
        |   |           |   |   |   |-- seccomp.a
        |   |           |   |   |   |-- selinux.a
        |   |           |   |   |   |-- sysctl.a
        |   |           |   |   |   |-- user.a
        |   |           |   |   |   `-- util.a
        |   |           |   |   `-- podsecuritypolicy.a
        |   |           |   |-- securitycontext.a
        |   |           |   |-- selection.a
        |   |           |   |-- serviceaccount.a
        |   |           |   |-- ssh.a
        |   |           |   |-- storage
        |   |           |   |   |-- etcd
        |   |           |   |   |   |-- metrics.a
        |   |           |   |   |   `-- util.a
        |   |           |   |   |-- etcd3.a
        |   |           |   |   |-- etcd.a
        |   |           |   |   |-- storagebackend
        |   |           |   |   |   `-- factory.a
        |   |           |   |   `-- storagebackend.a
        |   |           |   |-- storage.a
        |   |           |   |-- types.a
        |   |           |   |-- util
        |   |           |   |   |-- async.a
        |   |           |   |   |-- bandwidth.a
        |   |           |   |   |-- cache.a
        |   |           |   |   |-- cert.a
        |   |           |   |   |-- chmod.a
        |   |           |   |   |-- chown.a
        |   |           |   |   |-- clock.a
        |   |           |   |   |-- config.a
        |   |           |   |   |-- configz.a
        |   |           |   |   |-- crlf.a
        |   |           |   |   |-- dbus.a
        |   |           |   |   |-- diff.a
        |   |           |   |   |-- ebtables.a
        |   |           |   |   |-- env.a
        |   |           |   |   |-- errors.a
        |   |           |   |   |-- exec.a
        |   |           |   |   |-- flag.a
        |   |           |   |   |-- flock.a
        |   |           |   |   |-- flowcontrol.a
        |   |           |   |   |-- flushwriter.a
        |   |           |   |   |-- framer.a
        |   |           |   |   |-- goroutinemap
        |   |           |   |   |   `-- exponentialbackoff.a
        |   |           |   |   |-- goroutinemap.a
        |   |           |   |   |-- hash.a
        |   |           |   |   |-- homedir.a
        |   |           |   |   |-- httpstream
        |   |           |   |   |   `-- spdy.a
        |   |           |   |   |-- httpstream.a
        |   |           |   |   |-- integer.a
        |   |           |   |   |-- interrupt.a
        |   |           |   |   |-- intstr.a
        |   |           |   |   |-- io.a
        |   |           |   |   |-- iptables
        |   |           |   |   |   `-- testing.a
        |   |           |   |   |-- iptables.a
        |   |           |   |   |-- json.a
        |   |           |   |   |-- jsonpath.a
        |   |           |   |   |-- keymutex.a
        |   |           |   |   |-- labels.a
        |   |           |   |   |-- limitwriter.a
        |   |           |   |   |-- logs.a
        |   |           |   |   |-- maps.a
        |   |           |   |   |-- metrics.a
        |   |           |   |   |-- mount.a
        |   |           |   |   |-- net
        |   |           |   |   |   `-- sets.a
        |   |           |   |   |-- net.a
        |   |           |   |   |-- node.a
        |   |           |   |   |-- oom.a
        |   |           |   |   |-- parsers.a
        |   |           |   |   |-- pod.a
        |   |           |   |   |-- procfs.a
        |   |           |   |   |-- proxy.a
        |   |           |   |   |-- rand.a
        |   |           |   |   |-- replicaset.a
        |   |           |   |   |-- resourcecontainer.a
        |   |           |   |   |-- rlimit.a
        |   |           |   |   |-- runtime.a
        |   |           |   |   |-- selinux.a
        |   |           |   |   |-- sets.a
        |   |           |   |   |-- slice.a
        |   |           |   |   |-- strategicpatch.a
        |   |           |   |   |-- strings.a
        |   |           |   |   |-- sysctl.a
        |   |           |   |   |-- system.a
        |   |           |   |   |-- term.a
        |   |           |   |   |-- uuid.a
        |   |           |   |   |-- validation
        |   |           |   |   |   `-- field.a
        |   |           |   |   |-- validation.a
        |   |           |   |   |-- wait.a
        |   |           |   |   |-- workqueue
        |   |           |   |   |   `-- prometheus.a
        |   |           |   |   |-- workqueue.a
        |   |           |   |   |-- wsstream.a
        |   |           |   |   `-- yaml.a
        |   |           |   |-- util.a
        |   |           |   |-- version
        |   |           |   |   |-- prometheus.a
        |   |           |   |   `-- verflag.a
        |   |           |   |-- version.a
        |   |           |   |-- volume
        |   |           |   |   |-- aws_ebs.a
        |   |           |   |   |-- azure_dd.a
        |   |           |   |   |-- azure_file.a
        |   |           |   |   |-- cephfs.a
        |   |           |   |   |-- cinder.a
        |   |           |   |   |-- configmap.a
        |   |           |   |   |-- downwardapi.a
        |   |           |   |   |-- empty_dir.a
        |   |           |   |   |-- fc.a
        |   |           |   |   |-- flexvolume.a
        |   |           |   |   |-- flocker.a
        |   |           |   |   |-- gce_pd.a
        |   |           |   |   |-- git_repo.a
        |   |           |   |   |-- glusterfs.a
        |   |           |   |   |-- host_path.a
        |   |           |   |   |-- iscsi.a
        |   |           |   |   |-- nfs.a
        |   |           |   |   |-- quobyte.a
        |   |           |   |   |-- rbd.a
        |   |           |   |   |-- secret.a
        |   |           |   |   |-- util
        |   |           |   |   |   |-- nestedpendingoperations.a
        |   |           |   |   |   |-- operationexecutor.a
        |   |           |   |   |   |-- types.a
        |   |           |   |   |   `-- volumehelper.a
        |   |           |   |   |-- util.a
        |   |           |   |   `-- vsphere_volume.a
        |   |           |   |-- volume.a
        |   |           |   |-- watch
        |   |           |   |   `-- versioned.a
        |   |           |   `-- watch.a
        |   |           |-- plugin
        |   |           |   |-- cmd
        |   |           |   |   `-- kube-scheduler
        |   |           |   |       |-- app
        |   |           |   |       |   `-- options.a
        |   |           |   |       `-- app.a
        |   |           |   `-- pkg
        |   |           |       |-- admission
        |   |           |       |   |-- admit.a
        |   |           |       |   |-- alwayspullimages.a
        |   |           |       |   |-- antiaffinity.a
        |   |           |       |   |-- deny.a
        |   |           |       |   |-- exec.a
        |   |           |       |   |-- gc.a
        |   |           |       |   |-- imagepolicy.a
        |   |           |       |   |-- initialresources.a
        |   |           |       |   |-- limitranger.a
        |   |           |       |   |-- namespace
        |   |           |       |   |   |-- autoprovision.a
        |   |           |       |   |   |-- exists.a
        |   |           |       |   |   `-- lifecycle.a
        |   |           |       |   |-- persistentvolume
        |   |           |       |   |   `-- label.a
        |   |           |       |   |-- podnodeselector.a
        |   |           |       |   |-- resourcequota.a
        |   |           |       |   |-- security
        |   |           |       |   |   `-- podsecuritypolicy.a
        |   |           |       |   |-- securitycontext
        |   |           |       |   |   `-- scdeny.a
        |   |           |       |   |-- serviceaccount.a
        |   |           |       |   `-- storageclass
        |   |           |       |       `-- default.a
        |   |           |       |-- auth
        |   |           |       |   |-- authenticator
        |   |           |       |   |   |-- password
        |   |           |       |   |   |   |-- keystone.a
        |   |           |       |   |   |   `-- passwordfile.a
        |   |           |       |   |   |-- request
        |   |           |       |   |   |   |-- anonymous.a
        |   |           |       |   |   |   |-- basicauth.a
        |   |           |       |   |   |   |-- headerrequest.a
        |   |           |       |   |   |   |-- union.a
        |   |           |       |   |   |   `-- x509.a
        |   |           |       |   |   `-- token
        |   |           |       |   |       |-- anytoken.a
        |   |           |       |   |       |-- oidc.a
        |   |           |       |   |       |-- tokenfile.a
        |   |           |       |   |       `-- webhook.a
        |   |           |       |   `-- authorizer
        |   |           |       |       |-- rbac
        |   |           |       |       |   `-- bootstrappolicy.a
        |   |           |       |       |-- rbac.a
        |   |           |       |       `-- webhook.a
        |   |           |       |-- client
        |   |           |       |   |-- auth
        |   |           |       |   |   |-- gcp.a
        |   |           |       |   |   `-- oidc.a
        |   |           |       |   `-- auth.a
        |   |           |       |-- scheduler
        |   |           |       |   |-- algorithm
        |   |           |       |   |   |-- predicates.a
        |   |           |       |   |   |-- priorities
        |   |           |       |   |   |   `-- util.a
        |   |           |       |   |   `-- priorities.a
        |   |           |       |   |-- algorithm.a
        |   |           |       |   |-- algorithmprovider
        |   |           |       |   |   `-- defaults.a
        |   |           |       |   |-- algorithmprovider.a
        |   |           |       |   |-- api
        |   |           |       |   |   |-- latest.a
        |   |           |       |   |   |-- v1.a
        |   |           |       |   |   `-- validation.a
        |   |           |       |   |-- api.a
        |   |           |       |   |-- factory.a
        |   |           |       |   |-- metrics.a
        |   |           |       |   `-- schedulercache.a
        |   |           |       |-- scheduler.a
        |   |           |       `-- webhook.a
        |   |           |-- test
        |   |           |   `-- utils.a
        |   |           |-- third_party
        |   |           |   `-- forked
        |   |           |       `-- golang
        |   |           |           |-- expansion.a
        |   |           |           |-- json.a
        |   |           |           |-- netutil.a
        |   |           |           |-- reflect.a
        |   |           |           `-- template.a
        |   |           `-- vendor
        |   |               |-- bitbucket.org
        |   |               |   `-- ww
        |   |               |       `-- goautoneg.a
        |   |               |-- cloud.google.com
        |   |               |   `-- go
        |   |               |       |-- compute
        |   |               |       |   `-- metadata.a
        |   |               |       `-- internal.a
        |   |               |-- github.com
        |   |               |   |-- abbot
        |   |               |   |   `-- go-http-auth.a
        |   |               |   |-- appc
        |   |               |   |   `-- spec
        |   |               |   |       |-- schema
        |   |               |   |       |   |-- common.a
        |   |               |   |       |   `-- types.a
        |   |               |   |       `-- schema.a
        |   |               |   |-- aws
        |   |               |   |   `-- aws-sdk-go
        |   |               |   |       |-- aws
        |   |               |   |       |   |-- awserr.a
        |   |               |   |       |   |-- awsutil.a
        |   |               |   |       |   |-- client
        |   |               |   |       |   |   `-- metadata.a
        |   |               |   |       |   |-- client.a
        |   |               |   |       |   |-- corehandlers.a
        |   |               |   |       |   |-- credentials
        |   |               |   |       |   |   `-- ec2rolecreds.a
        |   |               |   |       |   |-- credentials.a
        |   |               |   |       |   |-- defaults.a
        |   |               |   |       |   |-- ec2metadata.a
        |   |               |   |       |   |-- request.a
        |   |               |   |       |   `-- session.a
        |   |               |   |       |-- aws.a
        |   |               |   |       |-- private
        |   |               |   |       |   |-- endpoints.a
        |   |               |   |       |   |-- protocol
        |   |               |   |       |   |   |-- ec2query.a
        |   |               |   |       |   |   |-- json
        |   |               |   |       |   |   |   `-- jsonutil.a
        |   |               |   |       |   |   |-- jsonrpc.a
        |   |               |   |       |   |   |-- query
        |   |               |   |       |   |   |   `-- queryutil.a
        |   |               |   |       |   |   |-- query.a
        |   |               |   |       |   |   |-- rest.a
        |   |               |   |       |   |   |-- restxml.a
        |   |               |   |       |   |   `-- xml
        |   |               |   |       |   |       `-- xmlutil.a
        |   |               |   |       |   |-- signer
        |   |               |   |       |   |   `-- v4.a
        |   |               |   |       |   `-- waiter.a
        |   |               |   |       `-- service
        |   |               |   |           |-- autoscaling.a
        |   |               |   |           |-- ec2.a
        |   |               |   |           |-- ecr.a
        |   |               |   |           |-- elb.a
        |   |               |   |           `-- route53.a
        |   |               |   |-- Azure
        |   |               |   |   |-- azure-sdk-for-go
        |   |               |   |   |   `-- arm
        |   |               |   |   |       |-- compute.a
        |   |               |   |   |       `-- network.a
        |   |               |   |   `-- go-autorest
        |   |               |   |       |-- autorest
        |   |               |   |       |   |-- azure.a
        |   |               |   |       |   |-- date.a
        |   |               |   |       |   `-- to.a
        |   |               |   |       `-- autorest.a
        |   |               |   |-- beorn7
        |   |               |   |   `-- perks
        |   |               |   |       `-- quantile.a
        |   |               |   |-- blang
        |   |               |   |   `-- semver.a
        |   |               |   |-- cloudflare
        |   |               |   |   `-- cfssl
        |   |               |   |       |-- auth.a
        |   |               |   |       |-- certdb.a
        |   |               |   |       |-- config.a
        |   |               |   |       |-- crypto
        |   |               |   |       |   `-- pkcs7.a
        |   |               |   |       |-- csr.a
        |   |               |   |       |-- errors.a
        |   |               |   |       |-- helpers
        |   |               |   |       |   `-- derhelpers.a
        |   |               |   |       |-- helpers.a
        |   |               |   |       |-- info.a
        |   |               |   |       |-- log.a
        |   |               |   |       |-- ocsp
        |   |               |   |       |   `-- config.a
        |   |               |   |       |-- signer
        |   |               |   |       |   `-- local.a
        |   |               |   |       `-- signer.a
        |   |               |   |-- clusterhq
        |   |               |   |   `-- flocker-go.a
        |   |               |   |-- codegangsta
        |   |               |   |   `-- negroni.a
        |   |               |   |-- containernetworking
        |   |               |   |   `-- cni
        |   |               |   |       |-- libcni.a
        |   |               |   |       `-- pkg
        |   |               |   |           |-- invoke.a
        |   |               |   |           `-- types.a
        |   |               |   |-- coreos
        |   |               |   |   |-- etcd
        |   |               |   |   |   |-- auth
        |   |               |   |   |   |   `-- authpb.a
        |   |               |   |   |   |-- client.a
        |   |               |   |   |   |-- clientv3.a
        |   |               |   |   |   |-- etcdserver
        |   |               |   |   |   |   |-- api
        |   |               |   |   |   |   |   `-- v3rpc
        |   |               |   |   |   |   |       `-- rpctypes.a
        |   |               |   |   |   |   `-- etcdserverpb.a
        |   |               |   |   |   |-- mvcc
        |   |               |   |   |   |   `-- mvccpb.a
        |   |               |   |   |   `-- pkg
        |   |               |   |   |       |-- fileutil.a
        |   |               |   |   |       |-- pathutil.a
        |   |               |   |   |       |-- tlsutil.a
        |   |               |   |   |       |-- transport.a
        |   |               |   |   |       `-- types.a
        |   |               |   |   |-- go-oidc
        |   |               |   |   |   |-- http.a
        |   |               |   |   |   |-- jose.a
        |   |               |   |   |   |-- key.a
        |   |               |   |   |   |-- oauth2.a
        |   |               |   |   |   `-- oidc.a
        |   |               |   |   |-- go-semver
        |   |               |   |   |   `-- semver.a
        |   |               |   |   |-- go-systemd
        |   |               |   |   |   |-- daemon.a
        |   |               |   |   |   |-- dbus.a
        |   |               |   |   |   |-- journal.a
        |   |               |   |   |   |-- unit.a
        |   |               |   |   |   `-- util.a
        |   |               |   |   |-- pkg
        |   |               |   |   |   |-- capnslog.a
        |   |               |   |   |   |-- dlopen.a
        |   |               |   |   |   |-- health.a
        |   |               |   |   |   |-- httputil.a
        |   |               |   |   |   `-- timeutil.a
        |   |               |   |   `-- rkt
        |   |               |   |       `-- api
        |   |               |   |           `-- v1alpha.a
        |   |               |   |-- cpuguy83
        |   |               |   |   `-- go-md2man
        |   |               |   |       `-- md2man.a
        |   |               |   |-- davecgh
        |   |               |   |   `-- go-spew
        |   |               |   |       `-- spew.a
        |   |               |   |-- daviddengcn
        |   |               |   |   `-- go-colortext.a
        |   |               |   |-- dgrijalva
        |   |               |   |   `-- jwt-go.a
        |   |               |   |-- docker
        |   |               |   |   |-- distribution
        |   |               |   |   |   |-- digest.a
        |   |               |   |   |   `-- reference.a
        |   |               |   |   |-- docker
        |   |               |   |   |   `-- pkg
        |   |               |   |   |       |-- jsonlog.a
        |   |               |   |   |       |-- jsonmessage.a
        |   |               |   |   |       |-- mount.a
        |   |               |   |   |       |-- stdcopy.a
        |   |               |   |   |       |-- symlink.a
        |   |               |   |   |       |-- system.a
        |   |               |   |   |       `-- term.a
        |   |               |   |   |-- engine-api
        |   |               |   |   |   |-- client
        |   |               |   |   |   |   |-- transport
        |   |               |   |   |   |   |   `-- cancellable.a
        |   |               |   |   |   |   `-- transport.a
        |   |               |   |   |   |-- client.a
        |   |               |   |   |   |-- types
        |   |               |   |   |   |   |-- blkiodev.a
        |   |               |   |   |   |   |-- container.a
        |   |               |   |   |   |   |-- filters.a
        |   |               |   |   |   |   |-- network.a
        |   |               |   |   |   |   |-- reference.a
        |   |               |   |   |   |   |-- registry.a
        |   |               |   |   |   |   |-- strslice.a
        |   |               |   |   |   |   |-- time.a
        |   |               |   |   |   |   `-- versions.a
        |   |               |   |   |   `-- types.a
        |   |               |   |   |-- go-connections
        |   |               |   |   |   |-- nat.a
        |   |               |   |   |   |-- sockets.a
        |   |               |   |   |   `-- tlsconfig.a
        |   |               |   |   |-- go-units.a
        |   |               |   |   |-- spdystream
        |   |               |   |   |   `-- spdy.a
        |   |               |   |   `-- spdystream.a
        |   |               |   |-- elazarl
        |   |               |   |   `-- go-bindata-assetfs.a
        |   |               |   |-- emicklei
        |   |               |   |   |-- go-restful
        |   |               |   |   |   |-- log.a
        |   |               |   |   |   `-- swagger.a
        |   |               |   |   `-- go-restful.a
        |   |               |   |-- evanphx
        |   |               |   |   `-- json-patch.a
        |   |               |   |-- exponent-io
        |   |               |   |   `-- jsonpath.a
        |   |               |   |-- garyburd
        |   |               |   |   `-- redigo
        |   |               |   |       |-- internal.a
        |   |               |   |       `-- redis.a
        |   |               |   |-- ghodss
        |   |               |   |   `-- yaml.a
        |   |               |   |-- godbus
        |   |               |   |   `-- dbus.a
        |   |               |   |-- gogo
        |   |               |   |   `-- protobuf
        |   |               |   |       |-- proto.a
        |   |               |   |       `-- sortkeys.a
        |   |               |   |-- go-ini
        |   |               |   |   `-- ini.a
        |   |               |   |-- golang
        |   |               |   |   |-- glog.a
        |   |               |   |   |-- groupcache
        |   |               |   |   |   `-- lru.a
        |   |               |   |   |-- mock
        |   |               |   |   |   `-- gomock.a
        |   |               |   |   `-- protobuf
        |   |               |   |       |-- jsonpb.a
        |   |               |   |       `-- proto.a
        |   |               |   |-- google
        |   |               |   |   |-- cadvisor
        |   |               |   |   |   |-- api.a
        |   |               |   |   |   |-- cache
        |   |               |   |   |   |   `-- memory.a
        |   |               |   |   |   |-- collector.a
        |   |               |   |   |   |-- container
        |   |               |   |   |   |   |-- common.a
        |   |               |   |   |   |   |-- docker.a
        |   |               |   |   |   |   |-- libcontainer.a
        |   |               |   |   |   |   |-- raw.a
        |   |               |   |   |   |   |-- rkt.a
        |   |               |   |   |   |   `-- systemd.a
        |   |               |   |   |   |-- container.a
        |   |               |   |   |   |-- devicemapper.a
        |   |               |   |   |   |-- events.a
        |   |               |   |   |   |-- fs.a
        |   |               |   |   |   |-- healthz.a
        |   |               |   |   |   |-- http
        |   |               |   |   |   |   `-- mux.a
        |   |               |   |   |   |-- http.a
        |   |               |   |   |   |-- info
        |   |               |   |   |   |   |-- v1.a
        |   |               |   |   |   |   `-- v2.a
        |   |               |   |   |   |-- machine.a
        |   |               |   |   |   |-- manager
        |   |               |   |   |   |   |-- watcher
        |   |               |   |   |   |   |   |-- raw.a
        |   |               |   |   |   |   |   `-- rkt.a
        |   |               |   |   |   |   `-- watcher.a
        |   |               |   |   |   |-- manager.a
        |   |               |   |   |   |-- metrics.a
        |   |               |   |   |   |-- pages
        |   |               |   |   |   |   `-- static.a
        |   |               |   |   |   |-- pages.a
        |   |               |   |   |   |-- storage.a
        |   |               |   |   |   |-- summary.a
        |   |               |   |   |   |-- utils
        |   |               |   |   |   |   |-- cloudinfo.a
        |   |               |   |   |   |   |-- cpuload
        |   |               |   |   |   |   |   `-- netlink.a
        |   |               |   |   |   |   |-- cpuload.a
        |   |               |   |   |   |   |-- docker.a
        |   |               |   |   |   |   |-- oomparser.a
        |   |               |   |   |   |   |-- sysfs.a
        |   |               |   |   |   |   |-- sysinfo.a
        |   |               |   |   |   |   `-- tail.a
        |   |               |   |   |   |-- utils.a
        |   |               |   |   |   |-- validate.a
        |   |               |   |   |   `-- version.a
        |   |               |   |   |-- certificate-transparency
        |   |               |   |   |   |-- go
        |   |               |   |   |   |   |-- asn1.a
        |   |               |   |   |   |   |-- client.a
        |   |               |   |   |   |   |-- x509
        |   |               |   |   |   |   |   `-- pkix.a
        |   |               |   |   |   |   `-- x509.a
        |   |               |   |   |   `-- go.a
        |   |               |   |   `-- gofuzz.a
        |   |               |   |-- go-openapi
        |   |               |   |   |-- jsonpointer.a
        |   |               |   |   |-- jsonreference.a
        |   |               |   |   |-- spec.a
        |   |               |   |   `-- swag.a
        |   |               |   |-- gorilla
        |   |               |   |   |-- context.a
        |   |               |   |   `-- mux.a
        |   |               |   |-- grpc-ecosystem
        |   |               |   |   `-- grpc-gateway
        |   |               |   |       |-- runtime
        |   |               |   |       |   `-- internal.a
        |   |               |   |       |-- runtime.a
        |   |               |   |       `-- utilities.a
        |   |               |   |-- hashicorp
        |   |               |   |   |-- golang-lru
        |   |               |   |   |   `-- simplelru.a
        |   |               |   |   `-- golang-lru.a
        |   |               |   |-- hawkular
        |   |               |   |   `-- hawkular-client-go
        |   |               |   |       `-- metrics.a
        |   |               |   |-- heketi
        |   |               |   |   `-- heketi
        |   |               |   |       |-- client
        |   |               |   |       |   `-- api
        |   |               |   |       |       `-- go-client.a
        |   |               |   |       `-- pkg
        |   |               |   |           |-- glusterfs
        |   |               |   |           |   `-- api.a
        |   |               |   |           `-- utils.a
        |   |               |   |-- howeyc
        |   |               |   |   `-- gopass.a
        |   |               |   |-- imdario
        |   |               |   |   `-- mergo.a
        |   |               |   |-- influxdata
        |   |               |   |   `-- influxdb
        |   |               |   |       |-- client.a
        |   |               |   |       |-- models.a
        |   |               |   |       `-- pkg
        |   |               |   |           `-- escape.a
        |   |               |   |-- jmespath
        |   |               |   |   `-- go-jmespath.a
        |   |               |   |-- jonboulle
        |   |               |   |   `-- clockwork.a
        |   |               |   |-- juju
        |   |               |   |   `-- ratelimit.a
        |   |               |   |-- kr
        |   |               |   |   `-- pty.a
        |   |               |   |-- lpabon
        |   |               |   |   `-- godbc.a
        |   |               |   |-- mailru
        |   |               |   |   `-- easyjson
        |   |               |   |       |-- buffer.a
        |   |               |   |       |-- jlexer.a
        |   |               |   |       `-- jwriter.a
        |   |               |   |-- MakeNowJust
        |   |               |   |   `-- heredoc.a
        |   |               |   |-- matttproud
        |   |               |   |   `-- golang_protobuf_extensions
        |   |               |   |       `-- pbutil.a
        |   |               |   |-- mesos
        |   |               |   |   `-- mesos-go
        |   |               |   |       |-- detector
        |   |               |   |       |   `-- zoo.a
        |   |               |   |       |-- detector.a
        |   |               |   |       |-- mesosproto.a
        |   |               |   |       |-- mesosutil.a
        |   |               |   |       `-- upid.a
        |   |               |   |-- mistifyio
        |   |               |   |   `-- go-zfs.a
        |   |               |   |-- mitchellh
        |   |               |   |   |-- go-wordwrap.a
        |   |               |   |   `-- mapstructure.a
        |   |               |   |-- mreiferson
        |   |               |   |   `-- go-httpclient.a
        |   |               |   |-- mvdan
        |   |               |   |   `-- xurls.a
        |   |               |   |-- mxk
        |   |               |   |   `-- go-flowrate
        |   |               |   |       `-- flowrate.a
        |   |               |   |-- onsi
        |   |               |   |   `-- ginkgo
        |   |               |   |       |-- config.a
        |   |               |   |       |-- ginkgo
        |   |               |   |       |   |-- convert.a
        |   |               |   |       |   |-- interrupthandler.a
        |   |               |   |       |   |-- nodot.a
        |   |               |   |       |   |-- testrunner.a
        |   |               |   |       |   |-- testsuite.a
        |   |               |   |       |   `-- watch.a
        |   |               |   |       |-- internal
        |   |               |   |       |   `-- remote.a
        |   |               |   |       |-- reporters
        |   |               |   |       |   `-- stenographer.a
        |   |               |   |       |-- reporters.a
        |   |               |   |       `-- types.a
        |   |               |   |-- opencontainers
        |   |               |   |   `-- runc
        |   |               |   |       |-- libcontainer
        |   |               |   |       |   |-- apparmor.a
        |   |               |   |       |   |-- cgroups
        |   |               |   |       |   |   |-- fs.a
        |   |               |   |       |   |   `-- systemd.a
        |   |               |   |       |   |-- cgroups.a
        |   |               |   |       |   |-- configs
        |   |               |   |       |   |   `-- validate.a
        |   |               |   |       |   |-- configs.a
        |   |               |   |       |   |-- criurpc.a
        |   |               |   |       |   |-- keys.a
        |   |               |   |       |   |-- label.a
        |   |               |   |       |   |-- seccomp.a
        |   |               |   |       |   |-- selinux.a
        |   |               |   |       |   |-- stacktrace.a
        |   |               |   |       |   |-- system.a
        |   |               |   |       |   |-- user.a
        |   |               |   |       |   `-- utils.a
        |   |               |   |       `-- libcontainer.a
        |   |               |   |-- pborman
        |   |               |   |   `-- uuid.a
        |   |               |   |-- pmezard
        |   |               |   |   `-- go-difflib
        |   |               |   |       `-- difflib.a
        |   |               |   |-- prometheus
        |   |               |   |   |-- client_golang
        |   |               |   |   |   `-- prometheus.a
        |   |               |   |   |-- client_model
        |   |               |   |   |   `-- go.a
        |   |               |   |   |-- common
        |   |               |   |   |   |-- expfmt.a
        |   |               |   |   |   `-- model.a
        |   |               |   |   `-- procfs.a
        |   |               |   |-- PuerkitoBio
        |   |               |   |   |-- purell.a
        |   |               |   |   `-- urlesc.a
        |   |               |   |-- quobyte
        |   |               |   |   `-- api.a
        |   |               |   |-- rackspace
        |   |               |   |   |-- gophercloud
        |   |               |   |   |   |-- openstack
        |   |               |   |   |   |   |-- blockstorage
        |   |               |   |   |   |   |   `-- v1
        |   |               |   |   |   |   |       `-- volumes.a
        |   |               |   |   |   |   |-- common
        |   |               |   |   |   |   |   `-- extensions.a
        |   |               |   |   |   |   |-- compute
        |   |               |   |   |   |   |   `-- v2
        |   |               |   |   |   |   |       |-- extensions
        |   |               |   |   |   |   |       |   |-- bootfromvolume.a
        |   |               |   |   |   |   |       |   |-- diskconfig.a
        |   |               |   |   |   |   |       |   `-- volumeattach.a
        |   |               |   |   |   |   |       |-- flavors.a
        |   |               |   |   |   |   |       |-- images.a
        |   |               |   |   |   |   |       `-- servers.a
        |   |               |   |   |   |   |-- identity
        |   |               |   |   |   |   |   |-- v2
        |   |               |   |   |   |   |   |   |-- tenants.a
        |   |               |   |   |   |   |   |   `-- tokens.a
        |   |               |   |   |   |   |   `-- v3
        |   |               |   |   |   |   |       |-- extensions
        |   |               |   |   |   |   |       |   `-- trust.a
        |   |               |   |   |   |   |       `-- tokens.a
        |   |               |   |   |   |   |-- networking
        |   |               |   |   |   |   |   `-- v2
        |   |               |   |   |   |   |       |-- extensions
        |   |               |   |   |   |   |       |   |-- layer3
        |   |               |   |   |   |   |       |   |   `-- floatingips.a
        |   |               |   |   |   |   |       |   |-- lbaas
        |   |               |   |   |   |   |       |   |   |-- members.a
        |   |               |   |   |   |   |       |   |   |-- monitors.a
        |   |               |   |   |   |   |       |   |   |-- pools.a
        |   |               |   |   |   |   |       |   |   `-- vips.a
        |   |               |   |   |   |   |       |   |-- lbaas_v2
        |   |               |   |   |   |   |       |   |   |-- listeners.a
        |   |               |   |   |   |   |       |   |   |-- loadbalancers.a
        |   |               |   |   |   |   |       |   |   |-- monitors.a
        |   |               |   |   |   |   |       |   |   `-- pools.a
        |   |               |   |   |   |   |       |   `-- security
        |   |               |   |   |   |   |       |       |-- groups.a
        |   |               |   |   |   |   |       |       `-- rules.a
        |   |               |   |   |   |   |       |-- extensions.a
        |   |               |   |   |   |   |       `-- ports.a
        |   |               |   |   |   |   `-- utils.a
        |   |               |   |   |   |-- openstack.a
        |   |               |   |   |   |-- pagination.a
        |   |               |   |   |   |-- rackspace
        |   |               |   |   |   |   |-- blockstorage
        |   |               |   |   |   |   |   `-- v1
        |   |               |   |   |   |   |       `-- volumes.a
        |   |               |   |   |   |   |-- compute
        |   |               |   |   |   |   |   `-- v2
        |   |               |   |   |   |   |       |-- servers.a
        |   |               |   |   |   |   |       `-- volumeattach.a
        |   |               |   |   |   |   `-- identity
        |   |               |   |   |   |       `-- v2
        |   |               |   |   |   |           `-- tokens.a
        |   |               |   |   |   `-- rackspace.a
        |   |               |   |   `-- gophercloud.a
        |   |               |   |-- renstrom
        |   |               |   |   `-- dedent.a
        |   |               |   |-- robfig
        |   |               |   |   `-- cron.a
        |   |               |   |-- russross
        |   |               |   |   `-- blackfriday.a
        |   |               |   |-- samuel
        |   |               |   |   `-- go-zookeeper
        |   |               |   |       `-- zk.a
        |   |               |   |-- shurcooL
        |   |               |   |   `-- sanitized_anchor_name.a
        |   |               |   |-- Sirupsen
        |   |               |   |   `-- logrus.a
        |   |               |   |-- spf13
        |   |               |   |   |-- cobra
        |   |               |   |   |   `-- doc.a
        |   |               |   |   |-- cobra.a
        |   |               |   |   `-- pflag.a
        |   |               |   |-- stretchr
        |   |               |   |   |-- objx.a
        |   |               |   |   `-- testify
        |   |               |   |       |-- assert.a
        |   |               |   |       `-- mock.a
        |   |               |   |-- syndtr
        |   |               |   |   `-- gocapability
        |   |               |   |       `-- capability.a
        |   |               |   |-- ugorji
        |   |               |   |   `-- go
        |   |               |   |       `-- codec.a
        |   |               |   |-- vishvananda
        |   |               |   |   |-- netlink
        |   |               |   |   |   `-- nl.a
        |   |               |   |   `-- netlink.a
        |   |               |   |-- vmware
        |   |               |   |   |-- govmomi
        |   |               |   |   |   |-- find.a
        |   |               |   |   |   |-- list.a
        |   |               |   |   |   |-- object.a
        |   |               |   |   |   |-- property.a
        |   |               |   |   |   |-- session.a
        |   |               |   |   |   |-- task.a
        |   |               |   |   |   |-- vim25
        |   |               |   |   |   |   |-- debug.a
        |   |               |   |   |   |   |-- methods.a
        |   |               |   |   |   |   |-- mo.a
        |   |               |   |   |   |   |-- progress.a
        |   |               |   |   |   |   |-- soap.a
        |   |               |   |   |   |   |-- types.a
        |   |               |   |   |   |   `-- xml.a
        |   |               |   |   |   `-- vim25.a
        |   |               |   |   `-- govmomi.a
        |   |               |   |-- xanzy
        |   |               |   |   `-- go-cloudstack
        |   |               |   |       `-- cloudstack.a
        |   |               |   `-- xyproto
        |   |               |       `-- simpleredis.a
        |   |               |-- go4.org
        |   |               |   `-- errorutil.a
        |   |               |-- golang.org
        |   |               |   `-- x
        |   |               |       |-- crypto
        |   |               |       |   |-- curve25519.a
        |   |               |       |   |-- pkcs12
        |   |               |       |   |   `-- internal
        |   |               |       |   |       `-- rc2.a
        |   |               |       |   |-- pkcs12.a
        |   |               |       |   |-- ssh
        |   |               |       |   |   `-- terminal.a
        |   |               |       |   `-- ssh.a
        |   |               |       |-- exp
        |   |               |       |   `-- inotify.a
        |   |               |       |-- net
        |   |               |       |   |-- context
        |   |               |       |   |   `-- ctxhttp.a
        |   |               |       |   |-- context.a
        |   |               |       |   |-- html
        |   |               |       |   |   `-- atom.a
        |   |               |       |   |-- html.a
        |   |               |       |   |-- http2
        |   |               |       |   |   `-- hpack.a
        |   |               |       |   |-- http2.a
        |   |               |       |   |-- idna.a
        |   |               |       |   |-- internal
        |   |               |       |   |   `-- timeseries.a
        |   |               |       |   |-- lex
        |   |               |       |   |   `-- httplex.a
        |   |               |       |   |-- proxy.a
        |   |               |       |   |-- trace.a
        |   |               |       |   `-- websocket.a
        |   |               |       |-- oauth2
        |   |               |       |   |-- google.a
        |   |               |       |   |-- internal.a
        |   |               |       |   |-- jws.a
        |   |               |       |   `-- jwt.a
        |   |               |       |-- oauth2.a
        |   |               |       |-- sys
        |   |               |       |   `-- unix.a
        |   |               |       `-- text
        |   |               |           |-- cases.a
        |   |               |           |-- internal
        |   |               |           |   `-- tag.a
        |   |               |           |-- language.a
        |   |               |           |-- runes.a
        |   |               |           |-- secure
        |   |               |           |   |-- bidirule.a
        |   |               |           |   `-- precis.a
        |   |               |           |-- transform.a
        |   |               |           |-- unicode
        |   |               |           |   |-- bidi.a
        |   |               |           |   `-- norm.a
        |   |               |           `-- width.a
        |   |               |-- google.golang.org
        |   |               |   |-- api
        |   |               |   |   |-- cloudmonitoring
        |   |               |   |   |   `-- v2beta2.a
        |   |               |   |   |-- compute
        |   |               |   |   |   `-- v1.a
        |   |               |   |   |-- container
        |   |               |   |   |   `-- v1.a
        |   |               |   |   |-- dns
        |   |               |   |   |   `-- v1.a
        |   |               |   |   |-- gensupport.a
        |   |               |   |   |-- googleapi
        |   |               |   |   |   `-- internal
        |   |               |   |   |       `-- uritemplates.a
        |   |               |   |   `-- googleapi.a
        |   |               |   |-- grpc
        |   |               |   |   |-- codes.a
        |   |               |   |   |-- credentials.a
        |   |               |   |   |-- grpclog.a
        |   |               |   |   |-- internal.a
        |   |               |   |   |-- metadata.a
        |   |               |   |   |-- naming.a
        |   |               |   |   |-- peer.a
        |   |               |   |   `-- transport.a
        |   |               |   `-- grpc.a
        |   |               |-- gopkg.in
        |   |               |   |-- gcfg.v1
        |   |               |   |   |-- scanner.a
        |   |               |   |   |-- token.a
        |   |               |   |   `-- types.a
        |   |               |   |-- gcfg.v1.a
        |   |               |   |-- inf.v0.a
        |   |               |   |-- natefinch
        |   |               |   |   `-- lumberjack.v2.a
        |   |               |   `-- yaml.v2.a
        |   |               `-- k8s.io
        |   |                   |-- client-go
        |   |                   |   `-- pkg
        |   |                   |       |-- api
        |   |                   |       |   |-- meta
        |   |                   |       |   |   `-- metatypes.a
        |   |                   |       |   |-- meta.a
        |   |                   |       |   |-- resource.a
        |   |                   |       |   `-- unversioned.a
        |   |                   |       |-- api.a
        |   |                   |       |-- auth
        |   |                   |       |   `-- user.a
        |   |                   |       |-- conversion
        |   |                   |       |   `-- queryparams.a
        |   |                   |       |-- conversion.a
        |   |                   |       |-- fields.a
        |   |                   |       |-- genericapiserver
        |   |                   |       |   `-- openapi
        |   |                   |       |       `-- common.a
        |   |                   |       |-- labels.a
        |   |                   |       |-- runtime
        |   |                   |       |   |-- serializer
        |   |                   |       |   |   |-- json.a
        |   |                   |       |   |   |-- protobuf.a
        |   |                   |       |   |   |-- recognizer.a
        |   |                   |       |   |   `-- versioning.a
        |   |                   |       |   `-- serializer.a
        |   |                   |       |-- runtime.a
        |   |                   |       |-- selection.a
        |   |                   |       |-- third_party
        |   |                   |       |   `-- forked
        |   |                   |       |       `-- golang
        |   |                   |       |           `-- reflect.a
        |   |                   |       |-- types.a
        |   |                   |       `-- util
        |   |                   |           |-- errors.a
        |   |                   |           |-- framer.a
        |   |                   |           |-- intstr.a
        |   |                   |           |-- json.a
        |   |                   |           |-- labels.a
        |   |                   |           |-- rand.a
        |   |                   |           |-- runtime.a
        |   |                   |           |-- sets.a
        |   |                   |           |-- uuid.a
        |   |                   |           |-- validation
        |   |                   |           |   `-- field.a
        |   |                   |           |-- validation.a
        |   |                   |           `-- yaml.a
        |   |                   |-- gengo
        |   |                   |   |-- args.a
        |   |                   |   |-- examples
        |   |                   |   |   |-- deepcopy-gen
        |   |                   |   |   |   `-- generators.a
        |   |                   |   |   |-- defaulter-gen
        |   |                   |   |   |   `-- generators.a
        |   |                   |   |   `-- set-gen
        |   |                   |   |       `-- sets.a
        |   |                   |   |-- generator.a
        |   |                   |   |-- namer.a
        |   |                   |   |-- parser.a
        |   |                   |   `-- types.a
        |   |                   `-- heapster
        |   |                       `-- metrics
        |   |                           |-- api
        |   |                           |   `-- v1
        |   |                           |       `-- types.a
        |   |                           `-- apis
        |   |                               `-- metrics
        |   |                                   `-- v1alpha1.a
        |   `-- linux_amd64_cgo
        |       `-- k8s.io
        |           `-- kubernetes
        |               |-- cmd
        |               |   |-- kubeadm
        |               |   |   |-- app
        |               |   |   |   |-- apis
        |               |   |   |   |   |-- kubeadm
        |               |   |   |   |   |   |-- install.a
        |               |   |   |   |   |   `-- v1alpha1.a
        |               |   |   |   |   `-- kubeadm.a
        |               |   |   |   |-- cmd.a
        |               |   |   |   |-- images.a
        |               |   |   |   |-- master.a
        |               |   |   |   |-- node.a
        |               |   |   |   |-- preflight.a
        |               |   |   |   `-- util.a
        |               |   |   `-- app.a
        |               |   |-- kube-apiserver
        |               |   |   |-- app
        |               |   |   |   `-- options.a
        |               |   |   `-- app.a
        |               |   |-- kube-controller-manager
        |               |   |   |-- app
        |               |   |   |   `-- options.a
        |               |   |   `-- app.a
        |               |   |-- kubectl
        |               |   |   `-- app.a
        |               |   |-- kube-discovery
        |               |   |   `-- app.a
        |               |   |-- kube-dns
        |               |   |   |-- app
        |               |   |   |   `-- options.a
        |               |   |   `-- app.a
        |               |   `-- kube-proxy
        |               |       |-- app
        |               |       |   `-- options.a
        |               |       `-- app.a
        |               |-- federation
        |               |   |-- apis
        |               |   |   |-- federation
        |               |   |   |   |-- install.a
        |               |   |   |   `-- v1beta1.a
        |               |   |   `-- federation.a
        |               |   `-- client
        |               |       `-- clientset_generated
        |               |           |-- federation_internalclientset
        |               |           |   `-- typed
        |               |           |       |-- core
        |               |           |       |   `-- internalversion.a
        |               |           |       |-- extensions
        |               |           |       |   `-- internalversion.a
        |               |           |       `-- federation
        |               |           |           `-- internalversion.a
        |               |           `-- federation_internalclientset.a
        |               |-- pkg
        |               |   |-- admission.a
        |               |   |-- api
        |               |   |   |-- annotations.a
        |               |   |   |-- endpoints.a
        |               |   |   |-- errors
        |               |   |   |   `-- storage.a
        |               |   |   |-- errors.a
        |               |   |   |-- events.a
        |               |   |   |-- install.a
        |               |   |   |-- meta
        |               |   |   |   `-- metatypes.a
        |               |   |   |-- meta.a
        |               |   |   |-- pod.a
        |               |   |   |-- resource.a
        |               |   |   |-- rest.a
        |               |   |   |-- service.a
        |               |   |   |-- unversioned
        |               |   |   |   `-- validation.a
        |               |   |   |-- unversioned.a
        |               |   |   |-- util.a
        |               |   |   |-- v1.a
        |               |   |   |-- validation
        |               |   |   |   `-- path.a
        |               |   |   `-- validation.a
        |               |   |-- api.a
        |               |   |-- apimachinery
        |               |   |   |-- announced.a
        |               |   |   `-- registered.a
        |               |   |-- apimachinery.a
        |               |   |-- apis
        |               |   |   |-- abac
        |               |   |   |   |-- latest.a
        |               |   |   |   |-- v0.a
        |               |   |   |   `-- v1beta1.a
        |               |   |   |-- abac.a
        |               |   |   |-- apps
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1alpha1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- apps.a
        |               |   |   |-- authentication
        |               |   |   |   |-- install.a
        |               |   |   |   `-- v1beta1.a
        |               |   |   |-- authentication.a
        |               |   |   |-- authorization
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1beta1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- authorization.a
        |               |   |   |-- autoscaling
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- autoscaling.a
        |               |   |   |-- batch
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1.a
        |               |   |   |   |-- v2alpha1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- batch.a
        |               |   |   |-- certificates
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1alpha1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- certificates.a
        |               |   |   |-- componentconfig
        |               |   |   |   |-- install.a
        |               |   |   |   `-- v1alpha1.a
        |               |   |   |-- componentconfig.a
        |               |   |   |-- extensions
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1beta1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- extensions.a
        |               |   |   |-- imagepolicy
        |               |   |   |   |-- install.a
        |               |   |   |   `-- v1alpha1.a
        |               |   |   |-- imagepolicy.a
        |               |   |   |-- policy
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1alpha1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- policy.a
        |               |   |   |-- rbac
        |               |   |   |   |-- install.a
        |               |   |   |   |-- v1alpha1.a
        |               |   |   |   `-- validation.a
        |               |   |   |-- rbac.a
        |               |   |   |-- storage
        |               |   |   |   |-- install.a
        |               |   |   |   |-- util.a
        |               |   |   |   |-- v1beta1.a
        |               |   |   |   `-- validation.a
        |               |   |   `-- storage.a
        |               |   |-- apiserver
        |               |   |   |-- authenticator.a
        |               |   |   |-- filters.a
        |               |   |   |-- metrics.a
        |               |   |   |-- openapi.a
        |               |   |   `-- request.a
        |               |   |-- apiserver.a
        |               |   |-- auth
        |               |   |   |-- authenticator
        |               |   |   |   `-- bearertoken.a
        |               |   |   |-- authenticator.a
        |               |   |   |-- authorizer
        |               |   |   |   |-- abac.a
        |               |   |   |   `-- union.a
        |               |   |   |-- authorizer.a
        |               |   |   |-- group.a
        |               |   |   |-- handlers.a
        |               |   |   `-- user.a
        |               |   |-- capabilities.a
        |               |   |-- client
        |               |   |   |-- cache.a
        |               |   |   |-- clientset_generated
        |               |   |   |   |-- internalclientset
        |               |   |   |   |   |-- fake.a
        |               |   |   |   |   `-- typed
        |               |   |   |   |       |-- apps
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- authentication
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- authorization
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- autoscaling
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- batch
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- certificates
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- core
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- extensions
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- policy
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       |-- rbac
        |               |   |   |   |       |   |-- internalversion
        |               |   |   |   |       |   |   `-- fake.a
        |               |   |   |   |       |   `-- internalversion.a
        |               |   |   |   |       `-- storage
        |               |   |   |   |           |-- internalversion
        |               |   |   |   |           |   `-- fake.a
        |               |   |   |   |           `-- internalversion.a
        |               |   |   |   `-- internalclientset.a
        |               |   |   |-- leaderelection
        |               |   |   |   `-- resourcelock.a
        |               |   |   |-- leaderelection.a
        |               |   |   |-- metrics
        |               |   |   |   `-- prometheus.a
        |               |   |   |-- metrics.a
        |               |   |   |-- record.a
        |               |   |   |-- restclient.a
        |               |   |   |-- retry.a
        |               |   |   |-- testing
        |               |   |   |   `-- core.a
        |               |   |   |-- transport.a
        |               |   |   |-- typed
        |               |   |   |   |-- discovery
        |               |   |   |   |   `-- fake.a
        |               |   |   |   |-- discovery.a
        |               |   |   |   `-- dynamic.a
        |               |   |   |-- unversioned
        |               |   |   |   |-- auth.a
        |               |   |   |   |-- clientcmd
        |               |   |   |   |   |-- api
        |               |   |   |   |   |   |-- latest.a
        |               |   |   |   |   |   `-- v1.a
        |               |   |   |   |   `-- api.a
        |               |   |   |   |-- clientcmd.a
        |               |   |   |   |-- portforward.a
        |               |   |   |   `-- remotecommand.a
        |               |   |   `-- unversioned.a
        |               |   |-- cloudprovider
        |               |   |   |-- providers
        |               |   |   |   |-- aws.a
        |               |   |   |   |-- azure.a
        |               |   |   |   |-- cloudstack.a
        |               |   |   |   |-- gce.a
        |               |   |   |   |-- mesos.a
        |               |   |   |   |-- openstack.a
        |               |   |   |   |-- ovirt.a
        |               |   |   |   |-- rackspace.a
        |               |   |   |   `-- vsphere.a
        |               |   |   `-- providers.a
        |               |   |-- cloudprovider.a
        |               |   |-- controller
        |               |   |   |-- certificates.a
        |               |   |   |-- daemon.a
        |               |   |   |-- deployment
        |               |   |   |   `-- util.a
        |               |   |   |-- deployment.a
        |               |   |   |-- disruption.a
        |               |   |   |-- endpoint.a
        |               |   |   |-- garbagecollector
        |               |   |   |   `-- metaonly.a
        |               |   |   |-- garbagecollector.a
        |               |   |   |-- informers.a
        |               |   |   |-- job.a
        |               |   |   |-- namespace.a
        |               |   |   |-- node.a
        |               |   |   |-- petset.a
        |               |   |   |-- podautoscaler
        |               |   |   |   `-- metrics.a
        |               |   |   |-- podautoscaler.a
        |               |   |   |-- podgc.a
        |               |   |   |-- replicaset.a
        |               |   |   |-- replication.a
        |               |   |   |-- resourcequota.a
        |               |   |   |-- route.a
        |               |   |   |-- scheduledjob.a
        |               |   |   |-- service.a
        |               |   |   |-- serviceaccount.a
        |               |   |   `-- volume
        |               |   |       |-- attachdetach
        |               |   |       |   |-- cache.a
        |               |   |       |   |-- populator.a
        |               |   |       |   |-- reconciler.a
        |               |   |       |   `-- statusupdater.a
        |               |   |       |-- attachdetach.a
        |               |   |       `-- persistentvolume.a
        |               |   |-- controller.a
        |               |   |-- conversion
        |               |   |   `-- queryparams.a
        |               |   |-- conversion.a
        |               |   |-- credentialprovider
        |               |   |   `-- aws.a
        |               |   |-- credentialprovider.a
        |               |   |-- dns
        |               |   |   `-- util.a
        |               |   |-- dns.a
        |               |   |-- fieldpath.a
        |               |   |-- fields.a
        |               |   |-- generated
        |               |   |   `-- openapi.a
        |               |   |-- genericapiserver
        |               |   |   |-- authorizer.a
        |               |   |   |-- filters.a
        |               |   |   |-- mux.a
        |               |   |   |-- openapi
        |               |   |   |   `-- common.a
        |               |   |   |-- openapi.a
        |               |   |   |-- options.a
        |               |   |   |-- routes
        |               |   |   |   `-- data
        |               |   |   |       `-- swagger.a
        |               |   |   |-- routes.a
        |               |   |   `-- validation.a
        |               |   |-- genericapiserver.a
        |               |   |-- healthz.a
        |               |   |-- httplog.a
        |               |   |-- kubectl
        |               |   |   |-- cmd
        |               |   |   |   |-- config.a
        |               |   |   |   |-- rollout.a
        |               |   |   |   |-- set.a
        |               |   |   |   |-- templates.a
        |               |   |   |   |-- util
        |               |   |   |   |   `-- editor.a
        |               |   |   |   `-- util.a
        |               |   |   |-- cmd.a
        |               |   |   |-- metricsutil.a
        |               |   |   `-- resource.a
        |               |   |-- kubectl.a
        |               |   |-- kubelet
        |               |   |   |-- client.a
        |               |   |   |-- events.a
        |               |   |   |-- leaky.a
        |               |   |   |-- qos.a
        |               |   |   |-- server
        |               |   |   |   |-- portforward.a
        |               |   |   |   `-- remotecommand.a
        |               |   |   |-- types.a
        |               |   |   `-- util
        |               |   |       |-- csr.a
        |               |   |       `-- format.a
        |               |   |-- labels.a
        |               |   |-- master
        |               |   |   |-- ports.a
        |               |   |   `-- thirdparty.a
        |               |   |-- master.a
        |               |   |-- probe
        |               |   |   `-- http.a
        |               |   |-- probe.a
        |               |   |-- proxy
        |               |   |   |-- config.a
        |               |   |   |-- healthcheck.a
        |               |   |   |-- iptables.a
        |               |   |   `-- userspace.a
        |               |   |-- proxy.a
        |               |   |-- quota
        |               |   |   |-- evaluator
        |               |   |   |   `-- core.a
        |               |   |   |-- generic.a
        |               |   |   `-- install.a
        |               |   |-- quota.a
        |               |   |-- registry
        |               |   |   |-- apps
        |               |   |   |   |-- petset
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- petset.a
        |               |   |   |   `-- rest.a
        |               |   |   |-- authentication
        |               |   |   |   |-- rest.a
        |               |   |   |   `-- tokenreview.a
        |               |   |   |-- authorization
        |               |   |   |   |-- localsubjectaccessreview.a
        |               |   |   |   |-- rest.a
        |               |   |   |   |-- selfsubjectaccessreview.a
        |               |   |   |   |-- subjectaccessreview.a
        |               |   |   |   `-- util.a
        |               |   |   |-- autoscaling
        |               |   |   |   |-- horizontalpodautoscaler
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- horizontalpodautoscaler.a
        |               |   |   |   `-- rest.a
        |               |   |   |-- batch
        |               |   |   |   |-- job
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- job.a
        |               |   |   |   |-- rest.a
        |               |   |   |   |-- scheduledjob
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   `-- scheduledjob.a
        |               |   |   |-- cachesize.a
        |               |   |   |-- certificates
        |               |   |   |   |-- certificates
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- certificates.a
        |               |   |   |   `-- rest.a
        |               |   |   |-- core
        |               |   |   |   |-- componentstatus.a
        |               |   |   |   |-- configmap
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- configmap.a
        |               |   |   |   |-- controller
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- controller.a
        |               |   |   |   |-- endpoint
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- endpoint.a
        |               |   |   |   |-- event
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- event.a
        |               |   |   |   |-- limitrange
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- limitrange.a
        |               |   |   |   |-- namespace
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- namespace.a
        |               |   |   |   |-- node
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- rest.a
        |               |   |   |   |-- node.a
        |               |   |   |   |-- persistentvolume
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- persistentvolume.a
        |               |   |   |   |-- persistentvolumeclaim
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- persistentvolumeclaim.a
        |               |   |   |   |-- pod
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- rest.a
        |               |   |   |   |-- pod.a
        |               |   |   |   |-- podtemplate
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- podtemplate.a
        |               |   |   |   |-- rangeallocation.a
        |               |   |   |   |-- resourcequota
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- resourcequota.a
        |               |   |   |   |-- rest.a
        |               |   |   |   |-- secret
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- secret.a
        |               |   |   |   |-- service
        |               |   |   |   |   |-- allocator
        |               |   |   |   |   |   `-- etcd.a
        |               |   |   |   |   |-- allocator.a
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   |-- ipallocator
        |               |   |   |   |   |   `-- controller.a
        |               |   |   |   |   |-- ipallocator.a
        |               |   |   |   |   |-- portallocator
        |               |   |   |   |   |   `-- controller.a
        |               |   |   |   |   `-- portallocator.a
        |               |   |   |   |-- service.a
        |               |   |   |   |-- serviceaccount
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   `-- serviceaccount.a
        |               |   |   |-- extensions
        |               |   |   |   |-- controller
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- daemonset
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- daemonset.a
        |               |   |   |   |-- deployment
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- deployment.a
        |               |   |   |   |-- ingress
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- ingress.a
        |               |   |   |   |-- networkpolicy
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- networkpolicy.a
        |               |   |   |   |-- podsecuritypolicy
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- podsecuritypolicy.a
        |               |   |   |   |-- replicaset
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- replicaset.a
        |               |   |   |   |-- rest.a
        |               |   |   |   |-- thirdpartyresource
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- thirdpartyresource.a
        |               |   |   |   |-- thirdpartyresourcedata
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   `-- thirdpartyresourcedata.a
        |               |   |   |-- generic
        |               |   |   |   |-- registry.a
        |               |   |   |   `-- rest.a
        |               |   |   |-- generic.a
        |               |   |   |-- policy
        |               |   |   |   |-- poddisruptionbudget
        |               |   |   |   |   `-- etcd.a
        |               |   |   |   |-- poddisruptionbudget.a
        |               |   |   |   `-- rest.a
        |               |   |   |-- rbac
        |               |   |   |   |-- clusterrole
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- policybased.a
        |               |   |   |   |-- clusterrole.a
        |               |   |   |   |-- clusterrolebinding
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- policybased.a
        |               |   |   |   |-- clusterrolebinding.a
        |               |   |   |   |-- rest.a
        |               |   |   |   |-- role
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- policybased.a
        |               |   |   |   |-- role.a
        |               |   |   |   |-- rolebinding
        |               |   |   |   |   |-- etcd.a
        |               |   |   |   |   `-- policybased.a
        |               |   |   |   `-- rolebinding.a
        |               |   |   |-- rbac.a
        |               |   |   `-- storage
        |               |   |       |-- rest.a
        |               |   |       |-- storageclass
        |               |   |       |   `-- etcd.a
        |               |   |       `-- storageclass.a
        |               |   |-- routes.a
        |               |   |-- runtime
        |               |   |   |-- serializer
        |               |   |   |   |-- json.a
        |               |   |   |   |-- protobuf.a
        |               |   |   |   |-- recognizer.a
        |               |   |   |   |-- streaming.a
        |               |   |   |   `-- versioning.a
        |               |   |   `-- serializer.a
        |               |   |-- runtime.a
        |               |   |-- security
        |               |   |   |-- apparmor.a
        |               |   |   |-- podsecuritypolicy
        |               |   |   |   |-- apparmor.a
        |               |   |   |   |-- capabilities.a
        |               |   |   |   |-- group.a
        |               |   |   |   |-- seccomp.a
        |               |   |   |   |-- selinux.a
        |               |   |   |   |-- sysctl.a
        |               |   |   |   |-- user.a
        |               |   |   |   `-- util.a
        |               |   |   `-- podsecuritypolicy.a
        |               |   |-- securitycontext.a
        |               |   |-- selection.a
        |               |   |-- serviceaccount.a
        |               |   |-- ssh.a
        |               |   |-- storage
        |               |   |   |-- etcd
        |               |   |   |   |-- metrics.a
        |               |   |   |   `-- util.a
        |               |   |   |-- etcd3.a
        |               |   |   |-- etcd.a
        |               |   |   |-- storagebackend
        |               |   |   |   `-- factory.a
        |               |   |   `-- storagebackend.a
        |               |   |-- storage.a
        |               |   |-- types.a
        |               |   |-- util
        |               |   |   |-- async.a
        |               |   |   |-- cache.a
        |               |   |   |-- cert.a
        |               |   |   |-- chmod.a
        |               |   |   |-- chown.a
        |               |   |   |-- clock.a
        |               |   |   |-- config.a
        |               |   |   |-- configz.a
        |               |   |   |-- crlf.a
        |               |   |   |-- dbus.a
        |               |   |   |-- diff.a
        |               |   |   |-- env.a
        |               |   |   |-- errors.a
        |               |   |   |-- exec.a
        |               |   |   |-- flag.a
        |               |   |   |-- flowcontrol.a
        |               |   |   |-- flushwriter.a
        |               |   |   |-- framer.a
        |               |   |   |-- goroutinemap
        |               |   |   |   `-- exponentialbackoff.a
        |               |   |   |-- goroutinemap.a
        |               |   |   |-- hash.a
        |               |   |   |-- homedir.a
        |               |   |   |-- httpstream
        |               |   |   |   `-- spdy.a
        |               |   |   |-- httpstream.a
        |               |   |   |-- initsystem.a
        |               |   |   |-- integer.a
        |               |   |   |-- interrupt.a
        |               |   |   |-- intstr.a
        |               |   |   |-- io.a
        |               |   |   |-- iptables.a
        |               |   |   |-- json.a
        |               |   |   |-- jsonpath.a
        |               |   |   |-- keymutex.a
        |               |   |   |-- labels.a
        |               |   |   |-- logs.a
        |               |   |   |-- maps.a
        |               |   |   |-- metrics.a
        |               |   |   |-- mount.a
        |               |   |   |-- net
        |               |   |   |   `-- sets.a
        |               |   |   |-- net.a
        |               |   |   |-- node.a
        |               |   |   |-- oom.a
        |               |   |   |-- parsers.a
        |               |   |   |-- pod.a
        |               |   |   |-- proxy.a
        |               |   |   |-- rand.a
        |               |   |   |-- replicaset.a
        |               |   |   |-- resourcecontainer.a
        |               |   |   |-- runtime.a
        |               |   |   |-- sets.a
        |               |   |   |-- slice.a
        |               |   |   |-- strategicpatch.a
        |               |   |   |-- strings.a
        |               |   |   |-- sysctl.a
        |               |   |   |-- system.a
        |               |   |   |-- term.a
        |               |   |   |-- uuid.a
        |               |   |   |-- validation
        |               |   |   |   `-- field.a
        |               |   |   |-- validation.a
        |               |   |   |-- wait.a
        |               |   |   |-- workqueue
        |               |   |   |   `-- prometheus.a
        |               |   |   |-- workqueue.a
        |               |   |   |-- wsstream.a
        |               |   |   `-- yaml.a
        |               |   |-- util.a
        |               |   |-- version
        |               |   |   |-- prometheus.a
        |               |   |   `-- verflag.a
        |               |   |-- version.a
        |               |   |-- volume
        |               |   |   |-- aws_ebs.a
        |               |   |   |-- azure_dd.a
        |               |   |   |-- cinder.a
        |               |   |   |-- flexvolume.a
        |               |   |   |-- flocker.a
        |               |   |   |-- gce_pd.a
        |               |   |   |-- glusterfs.a
        |               |   |   |-- host_path.a
        |               |   |   |-- nfs.a
        |               |   |   |-- quobyte.a
        |               |   |   |-- rbd.a
        |               |   |   |-- util
        |               |   |   |   |-- nestedpendingoperations.a
        |               |   |   |   |-- operationexecutor.a
        |               |   |   |   |-- types.a
        |               |   |   |   `-- volumehelper.a
        |               |   |   |-- util.a
        |               |   |   `-- vsphere_volume.a
        |               |   |-- volume.a
        |               |   |-- watch
        |               |   |   `-- versioned.a
        |               |   `-- watch.a
        |               |-- plugin
        |               |   |-- cmd
        |               |   |   `-- kube-scheduler
        |               |   |       |-- app
        |               |   |       |   `-- options.a
        |               |   |       `-- app.a
        |               |   `-- pkg
        |               |       |-- admission
        |               |       |   |-- admit.a
        |               |       |   |-- alwayspullimages.a
        |               |       |   |-- antiaffinity.a
        |               |       |   |-- deny.a
        |               |       |   |-- exec.a
        |               |       |   |-- gc.a
        |               |       |   |-- imagepolicy.a
        |               |       |   |-- initialresources.a
        |               |       |   |-- limitranger.a
        |               |       |   |-- namespace
        |               |       |   |   |-- autoprovision.a
        |               |       |   |   |-- exists.a
        |               |       |   |   `-- lifecycle.a
        |               |       |   |-- persistentvolume
        |               |       |   |   `-- label.a
        |               |       |   |-- podnodeselector.a
        |               |       |   |-- resourcequota.a
        |               |       |   |-- security
        |               |       |   |   `-- podsecuritypolicy.a
        |               |       |   |-- securitycontext
        |               |       |   |   `-- scdeny.a
        |               |       |   |-- serviceaccount.a
        |               |       |   `-- storageclass
        |               |       |       `-- default.a
        |               |       |-- auth
        |               |       |   |-- authenticator
        |               |       |   |   |-- password
        |               |       |   |   |   |-- keystone.a
        |               |       |   |   |   `-- passwordfile.a
        |               |       |   |   |-- request
        |               |       |   |   |   |-- anonymous.a
        |               |       |   |   |   |-- basicauth.a
        |               |       |   |   |   |-- headerrequest.a
        |               |       |   |   |   |-- union.a
        |               |       |   |   |   `-- x509.a
        |               |       |   |   `-- token
        |               |       |   |       |-- anytoken.a
        |               |       |   |       |-- oidc.a
        |               |       |   |       |-- tokenfile.a
        |               |       |   |       `-- webhook.a
        |               |       |   `-- authorizer
        |               |       |       |-- rbac
        |               |       |       |   `-- bootstrappolicy.a
        |               |       |       |-- rbac.a
        |               |       |       `-- webhook.a
        |               |       |-- client
        |               |       |   |-- auth
        |               |       |   |   |-- gcp.a
        |               |       |   |   `-- oidc.a
        |               |       |   `-- auth.a
        |               |       |-- scheduler
        |               |       |   |-- algorithm
        |               |       |   |   |-- predicates.a
        |               |       |   |   |-- priorities
        |               |       |   |   |   `-- util.a
        |               |       |   |   `-- priorities.a
        |               |       |   |-- algorithm.a
        |               |       |   |-- algorithmprovider
        |               |       |   |   `-- defaults.a
        |               |       |   |-- algorithmprovider.a
        |               |       |   |-- api
        |               |       |   |   |-- latest.a
        |               |       |   |   |-- v1.a
        |               |       |   |   `-- validation.a
        |               |       |   |-- api.a
        |               |       |   |-- factory.a
        |               |       |   |-- metrics.a
        |               |       |   `-- schedulercache.a
        |               |       |-- scheduler.a
        |               |       `-- webhook.a
        |               |-- third_party
        |               |   `-- forked
        |               |       `-- golang
        |               |           |-- json.a
        |               |           |-- netutil.a
        |               |           |-- reflect.a
        |               |           `-- template.a
        |               `-- vendor
        |                   |-- bitbucket.org
        |                   |   `-- ww
        |                   |       `-- goautoneg.a
        |                   |-- cloud.google.com
        |                   |   `-- go
        |                   |       |-- compute
        |                   |       |   `-- metadata.a
        |                   |       `-- internal.a
        |                   |-- github.com
        |                   |   |-- aws
        |                   |   |   `-- aws-sdk-go
        |                   |   |       |-- aws
        |                   |   |       |   |-- awserr.a
        |                   |   |       |   |-- awsutil.a
        |                   |   |       |   |-- client
        |                   |   |       |   |   `-- metadata.a
        |                   |   |       |   |-- client.a
        |                   |   |       |   |-- corehandlers.a
        |                   |   |       |   |-- credentials
        |                   |   |       |   |   `-- ec2rolecreds.a
        |                   |   |       |   |-- credentials.a
        |                   |   |       |   |-- defaults.a
        |                   |   |       |   |-- ec2metadata.a
        |                   |   |       |   |-- request.a
        |                   |   |       |   `-- session.a
        |                   |   |       |-- aws.a
        |                   |   |       |-- private
        |                   |   |       |   |-- endpoints.a
        |                   |   |       |   |-- protocol
        |                   |   |       |   |   |-- ec2query.a
        |                   |   |       |   |   |-- json
        |                   |   |       |   |   |   `-- jsonutil.a
        |                   |   |       |   |   |-- jsonrpc.a
        |                   |   |       |   |   |-- query
        |                   |   |       |   |   |   `-- queryutil.a
        |                   |   |       |   |   |-- query.a
        |                   |   |       |   |   |-- rest.a
        |                   |   |       |   |   `-- xml
        |                   |   |       |   |       `-- xmlutil.a
        |                   |   |       |   |-- signer
        |                   |   |       |   |   `-- v4.a
        |                   |   |       |   `-- waiter.a
        |                   |   |       `-- service
        |                   |   |           |-- autoscaling.a
        |                   |   |           |-- ec2.a
        |                   |   |           |-- ecr.a
        |                   |   |           `-- elb.a
        |                   |   |-- Azure
        |                   |   |   |-- azure-sdk-for-go
        |                   |   |   |   `-- arm
        |                   |   |   |       |-- compute.a
        |                   |   |   |       `-- network.a
        |                   |   |   `-- go-autorest
        |                   |   |       |-- autorest
        |                   |   |       |   |-- azure.a
        |                   |   |       |   |-- date.a
        |                   |   |       |   `-- to.a
        |                   |   |       `-- autorest.a
        |                   |   |-- beorn7
        |                   |   |   `-- perks
        |                   |   |       `-- quantile.a
        |                   |   |-- blang
        |                   |   |   `-- semver.a
        |                   |   |-- cloudflare
        |                   |   |   `-- cfssl
        |                   |   |       |-- auth.a
        |                   |   |       |-- certdb.a
        |                   |   |       |-- config.a
        |                   |   |       |-- crypto
        |                   |   |       |   `-- pkcs7.a
        |                   |   |       |-- csr.a
        |                   |   |       |-- errors.a
        |                   |   |       |-- helpers
        |                   |   |       |   `-- derhelpers.a
        |                   |   |       |-- helpers.a
        |                   |   |       |-- info.a
        |                   |   |       |-- log.a
        |                   |   |       |-- ocsp
        |                   |   |       |   `-- config.a
        |                   |   |       |-- signer
        |                   |   |       |   `-- local.a
        |                   |   |       `-- signer.a
        |                   |   |-- clusterhq
        |                   |   |   `-- flocker-go.a
        |                   |   |-- coreos
        |                   |   |   |-- etcd
        |                   |   |   |   |-- auth
        |                   |   |   |   |   `-- authpb.a
        |                   |   |   |   |-- client.a
        |                   |   |   |   |-- clientv3.a
        |                   |   |   |   |-- etcdserver
        |                   |   |   |   |   |-- api
        |                   |   |   |   |   |   `-- v3rpc
        |                   |   |   |   |   |       `-- rpctypes.a
        |                   |   |   |   |   `-- etcdserverpb.a
        |                   |   |   |   |-- mvcc
        |                   |   |   |   |   `-- mvccpb.a
        |                   |   |   |   `-- pkg
        |                   |   |   |       |-- fileutil.a
        |                   |   |   |       |-- pathutil.a
        |                   |   |   |       |-- tlsutil.a
        |                   |   |   |       |-- transport.a
        |                   |   |   |       `-- types.a
        |                   |   |   |-- go-oidc
        |                   |   |   |   |-- http.a
        |                   |   |   |   |-- jose.a
        |                   |   |   |   |-- key.a
        |                   |   |   |   |-- oauth2.a
        |                   |   |   |   `-- oidc.a
        |                   |   |   |-- go-semver
        |                   |   |   |   `-- semver.a
        |                   |   |   |-- go-systemd
        |                   |   |   |   |-- activation.a
        |                   |   |   |   |-- daemon.a
        |                   |   |   |   `-- journal.a
        |                   |   |   `-- pkg
        |                   |   |       |-- capnslog.a
        |                   |   |       |-- health.a
        |                   |   |       |-- httputil.a
        |                   |   |       `-- timeutil.a
        |                   |   |-- davecgh
        |                   |   |   `-- go-spew
        |                   |   |       `-- spew.a
        |                   |   |-- daviddengcn
        |                   |   |   `-- go-colortext.a
        |                   |   |-- dgrijalva
        |                   |   |   `-- jwt-go.a
        |                   |   |-- docker
        |                   |   |   |-- distribution
        |                   |   |   |   |-- digest.a
        |                   |   |   |   `-- reference.a
        |                   |   |   |-- docker
        |                   |   |   |   `-- pkg
        |                   |   |   |       `-- term.a
        |                   |   |   |-- engine-api
        |                   |   |   |   |-- types
        |                   |   |   |   |   |-- blkiodev.a
        |                   |   |   |   |   |-- container.a
        |                   |   |   |   |   |-- filters.a
        |                   |   |   |   |   |-- network.a
        |                   |   |   |   |   |-- registry.a
        |                   |   |   |   |   |-- strslice.a
        |                   |   |   |   |   `-- versions.a
        |                   |   |   |   `-- types.a
        |                   |   |   |-- go-connections
        |                   |   |   |   `-- nat.a
        |                   |   |   |-- go-units.a
        |                   |   |   |-- spdystream
        |                   |   |   |   `-- spdy.a
        |                   |   |   `-- spdystream.a
        |                   |   |-- elazarl
        |                   |   |   `-- go-bindata-assetfs.a
        |                   |   |-- emicklei
        |                   |   |   |-- go-restful
        |                   |   |   |   |-- log.a
        |                   |   |   |   `-- swagger.a
        |                   |   |   `-- go-restful.a
        |                   |   |-- evanphx
        |                   |   |   `-- json-patch.a
        |                   |   |-- exponent-io
        |                   |   |   `-- jsonpath.a
        |                   |   |-- ghodss
        |                   |   |   `-- yaml.a
        |                   |   |-- godbus
        |                   |   |   `-- dbus.a
        |                   |   |-- gogo
        |                   |   |   `-- protobuf
        |                   |   |       |-- proto.a
        |                   |   |       `-- sortkeys.a
        |                   |   |-- go-ini
        |                   |   |   `-- ini.a
        |                   |   |-- golang
        |                   |   |   |-- glog.a
        |                   |   |   |-- groupcache
        |                   |   |   |   `-- lru.a
        |                   |   |   `-- protobuf
        |                   |   |       |-- jsonpb.a
        |                   |   |       `-- proto.a
        |                   |   |-- google
        |                   |   |   |-- certificate-transparency
        |                   |   |   |   |-- go
        |                   |   |   |   |   |-- asn1.a
        |                   |   |   |   |   |-- client.a
        |                   |   |   |   |   |-- x509
        |                   |   |   |   |   |   `-- pkix.a
        |                   |   |   |   |   `-- x509.a
        |                   |   |   |   `-- go.a
        |                   |   |   `-- gofuzz.a
        |                   |   |-- go-openapi
        |                   |   |   |-- jsonpointer.a
        |                   |   |   |-- jsonreference.a
        |                   |   |   |-- spec.a
        |                   |   |   `-- swag.a
        |                   |   |-- gorilla
        |                   |   |   |-- context.a
        |                   |   |   `-- mux.a
        |                   |   |-- grpc-ecosystem
        |                   |   |   `-- grpc-gateway
        |                   |   |       |-- runtime
        |                   |   |       |   `-- internal.a
        |                   |   |       |-- runtime.a
        |                   |   |       `-- utilities.a
        |                   |   |-- hashicorp
        |                   |   |   |-- golang-lru
        |                   |   |   |   `-- simplelru.a
        |                   |   |   `-- golang-lru.a
        |                   |   |-- hawkular
        |                   |   |   `-- hawkular-client-go
        |                   |   |       `-- metrics.a
        |                   |   |-- heketi
        |                   |   |   `-- heketi
        |                   |   |       |-- client
        |                   |   |       |   `-- api
        |                   |   |       |       `-- go-client.a
        |                   |   |       `-- pkg
        |                   |   |           |-- glusterfs
        |                   |   |           |   `-- api.a
        |                   |   |           `-- utils.a
        |                   |   |-- howeyc
        |                   |   |   `-- gopass.a
        |                   |   |-- imdario
        |                   |   |   `-- mergo.a
        |                   |   |-- influxdata
        |                   |   |   `-- influxdb
        |                   |   |       |-- client.a
        |                   |   |       |-- models.a
        |                   |   |       `-- pkg
        |                   |   |           `-- escape.a
        |                   |   |-- jmespath
        |                   |   |   `-- go-jmespath.a
        |                   |   |-- jonboulle
        |                   |   |   `-- clockwork.a
        |                   |   |-- juju
        |                   |   |   `-- ratelimit.a
        |                   |   |-- lpabon
        |                   |   |   `-- godbc.a
        |                   |   |-- mailru
        |                   |   |   `-- easyjson
        |                   |   |       |-- buffer.a
        |                   |   |       |-- jlexer.a
        |                   |   |       `-- jwriter.a
        |                   |   |-- MakeNowJust
        |                   |   |   `-- heredoc.a
        |                   |   |-- matttproud
        |                   |   |   `-- golang_protobuf_extensions
        |                   |   |       `-- pbutil.a
        |                   |   |-- mesos
        |                   |   |   `-- mesos-go
        |                   |   |       |-- detector
        |                   |   |       |   `-- zoo.a
        |                   |   |       |-- detector.a
        |                   |   |       |-- mesosproto.a
        |                   |   |       |-- mesosutil.a
        |                   |   |       `-- upid.a
        |                   |   |-- miekg
        |                   |   |   `-- dns.a
        |                   |   |-- mitchellh
        |                   |   |   |-- go-wordwrap.a
        |                   |   |   `-- mapstructure.a
        |                   |   |-- mreiferson
        |                   |   |   `-- go-httpclient.a
        |                   |   |-- mxk
        |                   |   |   `-- go-flowrate
        |                   |   |       `-- flowrate.a
        |                   |   |-- opencontainers
        |                   |   |   `-- runc
        |                   |   |       `-- libcontainer
        |                   |   |           |-- cgroups
        |                   |   |           |   `-- fs.a
        |                   |   |           |-- cgroups.a
        |                   |   |           |-- configs.a
        |                   |   |           |-- system.a
        |                   |   |           `-- utils.a
        |                   |   |-- pborman
        |                   |   |   `-- uuid.a
        |                   |   |-- prometheus
        |                   |   |   |-- client_golang
        |                   |   |   |   `-- prometheus.a
        |                   |   |   |-- client_model
        |                   |   |   |   `-- go.a
        |                   |   |   |-- common
        |                   |   |   |   |-- expfmt.a
        |                   |   |   |   `-- model.a
        |                   |   |   `-- procfs.a
        |                   |   |-- PuerkitoBio
        |                   |   |   |-- purell.a
        |                   |   |   `-- urlesc.a
        |                   |   |-- quobyte
        |                   |   |   `-- api.a
        |                   |   |-- rackspace
        |                   |   |   |-- gophercloud
        |                   |   |   |   |-- openstack
        |                   |   |   |   |   |-- blockstorage
        |                   |   |   |   |   |   `-- v1
        |                   |   |   |   |   |       `-- volumes.a
        |                   |   |   |   |   |-- common
        |                   |   |   |   |   |   `-- extensions.a
        |                   |   |   |   |   |-- compute
        |                   |   |   |   |   |   `-- v2
        |                   |   |   |   |   |       |-- extensions
        |                   |   |   |   |   |       |   |-- bootfromvolume.a
        |                   |   |   |   |   |       |   |-- diskconfig.a
        |                   |   |   |   |   |       |   `-- volumeattach.a
        |                   |   |   |   |   |       |-- flavors.a
        |                   |   |   |   |   |       |-- images.a
        |                   |   |   |   |   |       `-- servers.a
        |                   |   |   |   |   |-- identity
        |                   |   |   |   |   |   |-- v2
        |                   |   |   |   |   |   |   |-- tenants.a
        |                   |   |   |   |   |   |   `-- tokens.a
        |                   |   |   |   |   |   `-- v3
        |                   |   |   |   |   |       |-- extensions
        |                   |   |   |   |   |       |   `-- trust.a
        |                   |   |   |   |   |       `-- tokens.a
        |                   |   |   |   |   |-- networking
        |                   |   |   |   |   |   `-- v2
        |                   |   |   |   |   |       |-- extensions
        |                   |   |   |   |   |       |   |-- layer3
        |                   |   |   |   |   |       |   |   `-- floatingips.a
        |                   |   |   |   |   |       |   |-- lbaas
        |                   |   |   |   |   |       |   |   |-- members.a
        |                   |   |   |   |   |       |   |   |-- monitors.a
        |                   |   |   |   |   |       |   |   |-- pools.a
        |                   |   |   |   |   |       |   |   `-- vips.a
        |                   |   |   |   |   |       |   |-- lbaas_v2
        |                   |   |   |   |   |       |   |   |-- listeners.a
        |                   |   |   |   |   |       |   |   |-- loadbalancers.a
        |                   |   |   |   |   |       |   |   |-- monitors.a
        |                   |   |   |   |   |       |   |   `-- pools.a
        |                   |   |   |   |   |       |   `-- security
        |                   |   |   |   |   |       |       |-- groups.a
        |                   |   |   |   |   |       |       `-- rules.a
        |                   |   |   |   |   |       |-- extensions.a
        |                   |   |   |   |   |       `-- ports.a
        |                   |   |   |   |   `-- utils.a
        |                   |   |   |   |-- openstack.a
        |                   |   |   |   |-- pagination.a
        |                   |   |   |   |-- rackspace
        |                   |   |   |   |   |-- blockstorage
        |                   |   |   |   |   |   `-- v1
        |                   |   |   |   |   |       `-- volumes.a
        |                   |   |   |   |   |-- compute
        |                   |   |   |   |   |   `-- v2
        |                   |   |   |   |   |       |-- servers.a
        |                   |   |   |   |   |       `-- volumeattach.a
        |                   |   |   |   |   `-- identity
        |                   |   |   |   |       `-- v2
        |                   |   |   |   |           `-- tokens.a
        |                   |   |   |   `-- rackspace.a
        |                   |   |   `-- gophercloud.a
        |                   |   |-- renstrom
        |                   |   |   `-- dedent.a
        |                   |   |-- robfig
        |                   |   |   `-- cron.a
        |                   |   |-- russross
        |                   |   |   `-- blackfriday.a
        |                   |   |-- samuel
        |                   |   |   `-- go-zookeeper
        |                   |   |       `-- zk.a
        |                   |   |-- shurcooL
        |                   |   |   `-- sanitized_anchor_name.a
        |                   |   |-- Sirupsen
        |                   |   |   `-- logrus.a
        |                   |   |-- skynetservices
        |                   |   |   `-- skydns
        |                   |   |       |-- cache.a
        |                   |   |       |-- metrics.a
        |                   |   |       |-- msg.a
        |                   |   |       |-- server.a
        |                   |   |       `-- singleflight.a
        |                   |   |-- spf13
        |                   |   |   |-- cobra.a
        |                   |   |   `-- pflag.a
        |                   |   |-- square
        |                   |   |   |-- go-jose
        |                   |   |   |   |-- cipher.a
        |                   |   |   |   `-- json.a
        |                   |   |   `-- go-jose.a
        |                   |   |-- ugorji
        |                   |   |   `-- go
        |                   |   |       `-- codec.a
        |                   |   |-- vmware
        |                   |   |   |-- govmomi
        |                   |   |   |   |-- find.a
        |                   |   |   |   |-- list.a
        |                   |   |   |   |-- object.a
        |                   |   |   |   |-- property.a
        |                   |   |   |   |-- session.a
        |                   |   |   |   |-- task.a
        |                   |   |   |   |-- vim25
        |                   |   |   |   |   |-- debug.a
        |                   |   |   |   |   |-- methods.a
        |                   |   |   |   |   |-- mo.a
        |                   |   |   |   |   |-- progress.a
        |                   |   |   |   |   |-- soap.a
        |                   |   |   |   |   |-- types.a
        |                   |   |   |   |   `-- xml.a
        |                   |   |   |   `-- vim25.a
        |                   |   |   `-- govmomi.a
        |                   |   `-- xanzy
        |                   |       `-- go-cloudstack
        |                   |           `-- cloudstack.a
        |                   |-- golang.org
        |                   |   `-- x
        |                   |       |-- crypto
        |                   |       |   |-- curve25519.a
        |                   |       |   |-- pkcs12
        |                   |       |   |   `-- internal
        |                   |       |   |       `-- rc2.a
        |                   |       |   |-- pkcs12.a
        |                   |       |   |-- ssh
        |                   |       |   |   `-- terminal.a
        |                   |       |   `-- ssh.a
        |                   |       |-- net
        |                   |       |   |-- context
        |                   |       |   |   `-- ctxhttp.a
        |                   |       |   |-- context.a
        |                   |       |   |-- html
        |                   |       |   |   `-- atom.a
        |                   |       |   |-- html.a
        |                   |       |   |-- http2
        |                   |       |   |   `-- hpack.a
        |                   |       |   |-- http2.a
        |                   |       |   |-- idna.a
        |                   |       |   |-- internal
        |                   |       |   |   `-- timeseries.a
        |                   |       |   |-- lex
        |                   |       |   |   `-- httplex.a
        |                   |       |   |-- trace.a
        |                   |       |   `-- websocket.a
        |                   |       |-- oauth2
        |                   |       |   |-- google.a
        |                   |       |   |-- internal.a
        |                   |       |   |-- jws.a
        |                   |       |   `-- jwt.a
        |                   |       |-- oauth2.a
        |                   |       `-- text
        |                   |           |-- cases.a
        |                   |           |-- internal
        |                   |           |   `-- tag.a
        |                   |           |-- language.a
        |                   |           |-- runes.a
        |                   |           |-- secure
        |                   |           |   |-- bidirule.a
        |                   |           |   `-- precis.a
        |                   |           |-- transform.a
        |                   |           |-- unicode
        |                   |           |   |-- bidi.a
        |                   |           |   `-- norm.a
        |                   |           `-- width.a
        |                   |-- google.golang.org
        |                   |   |-- api
        |                   |   |   |-- cloudmonitoring
        |                   |   |   |   `-- v2beta2.a
        |                   |   |   |-- compute
        |                   |   |   |   `-- v1.a
        |                   |   |   |-- container
        |                   |   |   |   `-- v1.a
        |                   |   |   |-- gensupport.a
        |                   |   |   |-- googleapi
        |                   |   |   |   `-- internal
        |                   |   |   |       `-- uritemplates.a
        |                   |   |   `-- googleapi.a
        |                   |   |-- grpc
        |                   |   |   |-- codes.a
        |                   |   |   |-- credentials.a
        |                   |   |   |-- grpclog.a
        |                   |   |   |-- internal.a
        |                   |   |   |-- metadata.a
        |                   |   |   |-- naming.a
        |                   |   |   |-- peer.a
        |                   |   |   `-- transport.a
        |                   |   `-- grpc.a
        |                   |-- gopkg.in
        |                   |   |-- gcfg.v1
        |                   |   |   |-- scanner.a
        |                   |   |   |-- token.a
        |                   |   |   `-- types.a
        |                   |   |-- gcfg.v1.a
        |                   |   |-- inf.v0.a
        |                   |   |-- natefinch
        |                   |   |   `-- lumberjack.v2.a
        |                   |   `-- yaml.v2.a
        |                   `-- k8s.io
        |                       `-- heapster
        |                           `-- metrics
        |                               |-- api
        |                               |   `-- v1
        |                               |       `-- types.a
        |                               `-- apis
        |                                   `-- metrics
        |                                       `-- v1alpha1.a
        `-- src
            `-- k8s.io
                `-- kubernetes -> /opt/opensource/worksplace/go/src/github.com/kubernetes/kubernetes

```

## Build A Small K8 Cluster with Docker
* Find the folder that contains kubelet, kube-discovery etc to a folder and PATH contains it
* Make need root priviledges (/usr/local/bin/kubectl?)
* export K8S_VERSION=vYOUR_VERSION
* Start Docker
```
docker run \
--volume=/:/rootfs:ro \
--volume=/sys:/sys:ro \
--volume=/var/lib/docker/:/var/lib/docker:rw \
--volume=/var/lib/kubelet/:/var/lib/kubelet:rw \
--volume=/var/run:/var/run:rw \
--net=host \
--pid=host \
--privileged=true \
--name=kubelet \
-d \
gcr.io/google_containers/hyperkube-amd64:${K8S_VERSION} <<< is this just a tag? \
/hyperkube kubelet \
--containerized \
--hostname-override="127.0.0.1" \
--address="0.0.0.0" \
--api-servers=http://localhost:8080 \
--config=/etc/kubernetes/manifests \
--cluster-dns=10.0.0.10 \
--cluster-domain=cluster.local \
--allow-privileged=true --v=2
```
* Create Cluster
```
kubectl config set-cluster test-doc --server=http://localhost:8080
kubectl config set-context test-doc --cluster=test-doc
kubectl config use-context test-doc
```


