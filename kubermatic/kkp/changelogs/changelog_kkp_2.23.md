### API Changes

- Add component override settings for etcd that allow configuring the type of anti-affinity ([#12313](https://github.com/kubermatic/kubermatic/pull/12313))

### Breaking Changes

- The `kubermatic-installer` now recognizes CSIDrivers automatically and will use them when creating the `kubermatic-fast` StorageClass. Admins can still choose to simply copy the default StorageClass if it's heavily customized by continuing to specify `--storageclass copy-default`.ACTION REQUIRED: The flag value `gce` was renamed to `gcp` for `--storageclass` ([#12012](https://github.com/kubermatic/kubermatic/pull/12012))

### Bugfixes

- [EE] Fix worker-name handing in resource-quota updates ([#11943](https://github.com/kubermatic/kubermatic/pull/11943))
- Addons: openstack: service account for CSI snapshot webhook server ([#12201](https://github.com/kubermatic/kubermatic/pull/12201))
- Applications: fix OOM on usercluster-controller by limiting the history of helm releases ([#12089](https://github.com/kubermatic/kubermatic/pull/12089))
- Bugfix: don't override floating IP settings from user input for OpenStack initial MD ([#12261](https://github.com/kubermatic/kubermatic/pull/12261))
- Bugfix: include etcd-launcher and gatekeeper images in kubermatic-installer mirror-images ([#12130](https://github.com/kubermatic/kubermatic/pull/12130))
- Bugfix: include metering images in kubermatic-installer mirror-images ([#12144](https://github.com/kubermatic/kubermatic/pull/12144))
- Do not try to watch `Cluster` resources on the master in `usersshkey-synchronizer` and use Seeds as correct source instead ([#12271](https://github.com/kubermatic/kubermatic/pull/12271))
- Fix a bug that causes dedicated Seeds to be stuck in deletion ([#12131](https://github.com/kubermatic/kubermatic/pull/12131))
- Fix a bug that lead to metering reports overwriting each other when used with multiple seeds. Report names now include the Seed name as a Prefix ([#12221](https://github.com/kubermatic/kubermatic/pull/12221))
- Fix a bug where KKP managed vSphere folders are enforced but shouldn't ([#11962](https://github.com/kubermatic/kubermatic/pull/11962))
- Fix calculation of node CPU utilisation in Grafana dashboards for multi-core nodes ([#12034](https://github.com/kubermatic/kubermatic/pull/12034))
- Fix kubermatic-master-controller-manager trying to discover the `kubermaticv1.Cluster` resource type, which does not exist on standalone masters ([#12188](https://github.com/kubermatic/kubermatic/pull/12188))
- Fix metering CronJobs after KKP upgrades ([#12139](https://github.com/kubermatic/kubermatic/pull/12139))
- Fix MLA stack constantly updating Grafana datasources ([#12182](https://github.com/kubermatic/kubermatic/pull/12182))
- Fix mla-monitoring-agent configuration being invalid when custom scraping configuration is provided ([#11988](https://github.com/kubermatic/kubermatic/pull/11988))
- Fix potential path traversal in mirror-images command ([#12293](https://github.com/kubermatic/kubermatic/pull/12293))
- Fix wrong labels in cluster/project metrics when uppercase labels were used ([#11947](https://github.com/kubermatic/kubermatic/pull/11947))
- Installer: mla: --mla-skip-minio and --mla-skip-minio-lifecycle-mgr work properly now ([#12140](https://github.com/kubermatic/kubermatic/pull/12140))
- Metrics server write timeout increased ([#12314](https://github.com/kubermatic/kubermatic/pull/12314))
- Missing CRDs for VPA and KKP resources are correctly installed onto Seeds ([#12117](https://github.com/kubermatic/kubermatic/pull/12117))
- Pull `kas-network-proxy/proxy-server:v0.0.35` and `kas-network-proxy/proxy-agent:v0.0.35` image from `registry.k8s.io` instead of legacy GCR registry (`eu.gcr.io/k8s-artifacts-prod`) ([#12067](https://github.com/kubermatic/kubermatic/pull/12067))
- Revert CRD split between master and seed by installing all CRDs on the master again ([#12282](https://github.com/kubermatic/kubermatic/pull/12282))
- Set proper NodePort range in Cilium config if non-default range is used ([#11963](https://github.com/kubermatic/kubermatic/pull/11963))
- Support for configuring additional volumes for the UI ([#12103](https://github.com/kubermatic/kubermatic/pull/12103))
- The MLA stack is now able to recover from a lost Grafana volume, properly recreating organizations for KKP projects ([#12195](https://github.com/kubermatic/kubermatic/pull/12195))
- Update external-snapshotter validation webhook server to v6.0.1 ([#12120](https://github.com/kubermatic/kubermatic/pull/12120))
- Use seed proxy configuration for seed deployed webhook ([#12070](https://github.com/kubermatic/kubermatic/pull/12070))
- Use serializable etcd liveness probes and add a startup probe, as per upstream recommendations ([#12190](https://github.com/kubermatic/kubermatic/pull/12190))
- Usermla Alertmanager now allows blackbox exporter to perform healthcheck API call without AuthFailure ([#12217](https://github.com/kubermatic/kubermatic/pull/12217))

### Chore

- Add support for Kubernetes 1.24.13, 1.25.9 and 1.26.4 ([#12165](https://github.com/kubermatic/kubermatic/pull/12165))
- Disable PodSecurityPolicy in MLA Grafana deployment ([#12101](https://github.com/kubermatic/kubermatic/pull/12101))
- Patch cilium v1.12 and v1.11 to latest patch release (v1.12.9) (v1.11.16) ([#12264](https://github.com/kubermatic/kubermatic/pull/12264))
- Update Alertmanager to 0.25.0 ([#12237](https://github.com/kubermatic/kubermatic/pull/12237))
- Update AWS CCM for Kubernetes 1.25 to 1.25.3Update AWS CSI to 2.17.1Update AWS Node Termination Handler to 1.19.0 ([#11967](https://github.com/kubermatic/kubermatic/pull/11967))
- Update AWS EBS CSI to 1.18.0.Update AWS CCM to 1.26.1 / 1.27.1 ([#12227](https://github.com/kubermatic/kubermatic/pull/12227))
- Update Azure Cloud Node Manager to 1.24.18 / 1.25.12 / 1.26.8Update Azure Disk CSI to 1.27.1Update Azure File CSI to 1.27.0Update Azure CCM to 1.24.18 / 1.25.12 / 1.26.8 / 1.27.1 ([#12222](https://github.com/kubermatic/kubermatic/pull/12222))
- Update Azure CSI Driver components to v1.27.0.Update Azure CCM / Cloud Node Manager to their latest versions as of 2023-03-01 ([#11969](https://github.com/kubermatic/kubermatic/pull/11969))
- Update blackbox-exporter to 0.23.0 ([#12235](https://github.com/kubermatic/kubermatic/pull/12235))
- Update cert-manager to 0.11 ([#11965](https://github.com/kubermatic/kubermatic/pull/11965))
- Update cert-manager to 1.11.1 ([#12243](https://github.com/kubermatic/kubermatic/pull/12243))
- Update cluster-autoscaler to 1.24.1 / 1.25.1 / 1.26.2 ([#12223](https://github.com/kubermatic/kubermatic/pull/12223))
- Update configmap-reload to 0.8.0 ([#12238](https://github.com/kubermatic/kubermatic/pull/12238))
- Update Dex to 2.36.0 ([#12233](https://github.com/kubermatic/kubermatic/pull/12233))
- Update Digitalocean CCM to 0.1.42 ([#11982](https://github.com/kubermatic/kubermatic/pull/11982))
- Update Envoy to 1.26.1 ([#12246](https://github.com/kubermatic/kubermatic/pull/12246))
- Update etcd-backup Minio to RELEASE.2023-05-04T21-44-30Z, change to quay.io/minio/minio ([#12241](https://github.com/kubermatic/kubermatic/pull/12241))
- Update Gatekeeper to 3.12.0 ([#12260](https://github.com/kubermatic/kubermatic/pull/12260))
- Update golang version to 1.20.3 ([#12142](https://github.com/kubermatic/kubermatic/pull/12142))
- Update Grafana to 9.4.3 ([#12013](https://github.com/kubermatic/kubermatic/pull/12013))
- Update Grafana to 9.5.1 ([#12240](https://github.com/kubermatic/kubermatic/pull/12240))
- Update helm-exporter to 1.2.5 ([#12239](https://github.com/kubermatic/kubermatic/pull/12239))
- Update Hetzner CCM to 1.15.0Update Hetzner CSI to 2.3.2 ([#12191](https://github.com/kubermatic/kubermatic/pull/12191))
- Update Hetzner CSI to 2.2.0Update Hetzner CCM to 1.13.1 ([#11968](https://github.com/kubermatic/kubermatic/pull/11968))
- Update IAP (oauth2-proxy) to 7.4.0 ([#12242](https://github.com/kubermatic/kubermatic/pull/12242))
- Update k8s-dns-node-cache to 1.22.20 ([#12245](https://github.com/kubermatic/kubermatic/pull/12245))
- Update Karma to 0.114 ([#12236](https://github.com/kubermatic/kubermatic/pull/12236))
- Update konnectivity proxy-agent/server to 0.0.37 for user clusters using Kubernetes up until 1.26Update konnectivity proxy-agent/server to 0.1.2 for user clusters using Kubernetes 1.27+ ([#12259](https://github.com/kubermatic/kubermatic/pull/12259))
- Update kube-state-metrics to 2.8.1 ([#11987](https://github.com/kubermatic/kubermatic/pull/11987))
- Update kube-state-metrics to 2.8.2 ([#12225](https://github.com/kubermatic/kubermatic/pull/12225))
- Update Metering to v1.0.3 with the following changes: * Add non machine-controller managed machines to `average-cluster-machines`. Note that this is based on a new metric that will be collected together in the same release, therefore information prior this update is not available.* Fixes a bug that leads to low CPU usage values* Remove redundant label quotation ([#12035](https://github.com/kubermatic/kubermatic/pull/12035))
- Update metrics-server to 0.6.3 ([#12244](https://github.com/kubermatic/kubermatic/pull/12244))
- Update nginx-ingress-controller to 1.7.1; this removes support for Kubernetes 1.23 for KKP master clusters ([#12234](https://github.com/kubermatic/kubermatic/pull/12234))
- Update node-exporter Helm chart (seed clusters) and addon (user clusters) to 1.5.0 ([#11984](https://github.com/kubermatic/kubermatic/pull/11984))
- Update Openstack CCM/CSI ([#11983](https://github.com/kubermatic/kubermatic/pull/11983))
- Update OpenStack CCM/CSI to 1.25.5 / 1.26.2. For Kubernetes 1.24+ the OpenStack container images are now using `registry.k8s.io` instead of `docker.io` ([#12228](https://github.com/kubermatic/kubermatic/pull/12228))
- Update Prometheus to 2.43.1 ([#12232](https://github.com/kubermatic/kubermatic/pull/12232))
- Update to Go 1.20.2 ([#11989](https://github.com/kubermatic/kubermatic/pull/11989))
- Update Velero to 1.10.1 ([#11966](https://github.com/kubermatic/kubermatic/pull/11966))
- Update VMware Cloud Director CSI driver to v1.3.2 ([#12096](https://github.com/kubermatic/kubermatic/pull/12096))

### Cleanup

- Anti-affinity rules for control plane components have been simplified to optimise scheduler performance while yielding the same results ([#12215](https://github.com/kubermatic/kubermatic/pull/12215))
- Remove long deprecated heapster addon ([#12055](https://github.com/kubermatic/kubermatic/pull/12055))
- Update Anexia CCM (cloud-controller-manager) to version 1.5.2 ([#11923](https://github.com/kubermatic/kubermatic/pull/11923))
- Update Anexia CCM (cloud-controller-manager) to version 1.5.3 ([#12125](https://github.com/kubermatic/kubermatic/pull/12125))
- Update Anexia CCM (cloud-controller-manager) to version 1.5.4 ([#12212](https://github.com/kubermatic/kubermatic/pull/12212))
- Use Alpine Linux 3.17 for container images ([#12007](https://github.com/kubermatic/kubermatic/pull/12007))

### Deprecation

- Remove auto-upgrade rule for userclusters from 1.23 to 1.24. All userclusters must be migrated to Kubernetes 1.24 before updating to KKP 2.23 ([#12280](https://github.com/kubermatic/kubermatic/pull/12280))

### Miscellaneous

- Add a new controller-runtime metrics dashboard in grafana to the monitoring chart ([#12257](https://github.com/kubermatic/kubermatic/pull/12257))
- Add support for ca-bundle to metering cronjobs ([#11979](https://github.com/kubermatic/kubermatic/pull/11979))
- Add support for canal 3.25 ([#12297](https://github.com/kubermatic/kubermatic/pull/12297))
- Kubermatic-installer: command to spin up a local KKP environment ([#12216](https://github.com/kubermatic/kubermatic/pull/12216))
- The context name for admin Kubeconfig has been changed to the cluster ID from `default` ([#12006](https://github.com/kubermatic/kubermatic/pull/12006))
- The validating webhook for `Cluster` resources now properly checks for provider incompatibilities ([#11996](https://github.com/kubermatic/kubermatic/pull/11996))

### New Feature

- Add --skip-charts flag to `kubermatic-installer deploy` command to make helm chart deployment skippable ([#12059](https://github.com/kubermatic/kubermatic/pull/12059))
- Add `componentOverride.userClusterController` to `Cluster` and `ClusterTemplate` resources to configure the `usercluster-controller` Deployment for each user cluster ([#12211](https://github.com/kubermatic/kubermatic/pull/12211))
- Add `kubermatic_seed_info` metric containing Seed metadata like version, location or phase.Add `kubermatic_seed_clusters` metric containing the number of user clusters per Seed.Add `kubermatic_seed_condition` metric describing the conditions for each Seed.Add `kubermatic_seed_labels` metric containing the Kubernetes labels on Seed resources.Add `KubermaticSeedNotHealthy` alert if a Seed is not healthy ([#12194](https://github.com/kubermatic/kubermatic/pull/12194))
- Add option to disable deployment of default network policies in KubeVirt cluster ([#12082](https://github.com/kubermatic/kubermatic/pull/12082))
- Add option to restrict project deletion to admin ([#12198](https://github.com/kubermatic/kubermatic/pull/12198))
- Add short name for  Application  crds:* `applicationdefinition` -> `appdef`.  e.g:  `kubectl get appdef`* `applicationinstallation` -> `appinstall`.  e.g:  `kubectl get appinstall` ([#12017](https://github.com/kubermatic/kubermatic/pull/12017))
- Add support for `oidc` authentication in kubeconfigs passed to `kubermatic-installer` ([#12252](https://github.com/kubermatic/kubermatic/pull/12252))
- Add support for Cilium 1.13.2 as user cluster CNI ([#12199](https://github.com/kubermatic/kubermatic/pull/12199))
- Add support for disabling Changelog popup in KubermaticSettings ([#12175](https://github.com/kubermatic/kubermatic/pull/12175))
- Add support for enforcing/enabling auto-updates and updates on first boot for Machine Deployments in KubermaticSettings ([#12152](https://github.com/kubermatic/kubermatic/pull/12152))
- Add support for Kubernetes 1.27, raise default version for new user clusters to 1.26.4 ([#12230](https://github.com/kubermatic/kubermatic/pull/12230))
- All Helm charts shipped by KKP now support specifying image pull secrets ([#12098](https://github.com/kubermatic/kubermatic/pull/12098))
- Change `etcd-defragger` CronJob `SuccessfulJobsHistoryLimit` from 0 to 1 to save logs of the most recent successful job ([#12303](https://github.com/kubermatic/kubermatic/pull/12303))
- Enable Loki Compactor rotation and set retention to 1 month by default ([#12029](https://github.com/kubermatic/kubermatic/pull/12029))
- Introduce EnableShareCluster flag in Kubermatic Settings to toggle the share cluster feature for the dashboard.[ACTION REQUIRED] `share_kubeconfig` field in the UI configuration for KubermaticConfiguration has been replaced with `EnableShareCluster` flag in KubermaticSettings. `share_kubeconfig` is no-op and will be ignored by the dashboard ([#11950](https://github.com/kubermatic/kubermatic/pull/11950))
- Limit EtcdDatabaseHighFragmentationRatio rule to avoid triggering excessively for small etcd instances ([#12305](https://github.com/kubermatic/kubermatic/pull/12305))
- New alert NodeTimeDrift ([#12275](https://github.com/kubermatic/kubermatic/pull/12275))
- Support added to specify the suffix `dockerTagSuffix` for the dashboard images. With `dockerTagSuffix` the tag becomes <CURRENT_KKP_VERSION:SUFFIX> i.e. "v2.15.0-SUFFIX" ([#12056](https://github.com/kubermatic/kubermatic/pull/12056))
- Update Cilium to v1.13.3 ([#12320](https://github.com/kubermatic/kubermatic/pull/12320))
- VMware Cloud Director now supports authentication using API Token ([#12124](https://github.com/kubermatic/kubermatic/pull/12124))

### Updates

- Update vSphere CCM/CSI to 1.23.4 / 1.24.5 / 1.25.2 / 1.26.1 ([#12229](https://github.com/kubermatic/kubermatic/pull/12229))
