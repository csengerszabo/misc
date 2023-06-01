### Bugfixes

- * UI/UX improvements for vSphere credentials in provider settings step* By default, username/password will be configured and dedicated credentials will be used to configure infra management user for vSphere ([#5959](https://github.com/kubermatic/dashboard/pull/5959))
- Add cache busting mechanism for theme styles ([#5943](https://github.com/kubermatic/dashboard/pull/5943))
- Allow removing cluster label when PodNodeSelector admission plugin and clusterDefaultNodeSelector namespace are set ([#5981](https://github.com/kubermatic/dashboard/pull/5981))
- Allow updating of the `clusterNetwork.proxyMode` via the KKP API (PATCH endpoint) ([#5803](https://github.com/kubermatic/dashboard/pull/5803))
- AWS subnets are fetched correctly if credentials are provided directly instead of using a preset ([#5883](https://github.com/kubermatic/dashboard/pull/5883))
- Fix cluster wizard not selecting a default version if custom versions are configured in `KubermaticConfiguration` ([#5879](https://github.com/kubermatic/dashboard/pull/5879))
- Fix Datacenter MachineFlavorFilter not used ([#5787](https://github.com/kubermatic/dashboard/pull/5787))
- Machine Deployments are initialized without waiting for all cluster details to finish loading ([#5922](https://github.com/kubermatic/dashboard/pull/5922))
- Show correct health information for Machine Deployments with no replicas ([#5837](https://github.com/kubermatic/dashboard/pull/5837))

### Chore

- Update golang version to 1.20.4 ([#5886](https://github.com/kubermatic/dashboard/pull/5886))

### Cleanup

- Use Alpine Linux 3.17 for container images ([#5814](https://github.com/kubermatic/dashboard/pull/5814))

### Design

- Add an option to clear VSphere tags category so it doesn't get stuck when there are no tags ([#5940](https://github.com/kubermatic/dashboard/pull/5940))
- Add color to required indicator of untouched and empty required form fields ([#5937](https://github.com/kubermatic/dashboard/pull/5937))
- Add indicator of what was changed on editing dialogs ([#5843](https://github.com/kubermatic/dashboard/pull/5843))
- Add warning message in the cluster list page in case some seeds are not reachable ([#5982](https://github.com/kubermatic/dashboard/pull/5982))
- Allow selection of items per page under every table along with user settings page ([#5954](https://github.com/kubermatic/dashboard/pull/5954))
- Improve page responsiveness  for smaller screen sizes ([#5801](https://github.com/kubermatic/dashboard/pull/5801))
- Update Dialogs to follow latest material design specifications ([#5927](https://github.com/kubermatic/dashboard/pull/5927))
- Update the notification design and improve user experience ([#5970](https://github.com/kubermatic/dashboard/pull/5970))

### Miscellaneous

- Add new option to restrict project deletion in the admin settings ([#5925](https://github.com/kubermatic/dashboard/pull/5925))
- Introduce Enable Share Cluster settings to toggle the share cluster feature from Admin panel ([#5764](https://github.com/kubermatic/dashboard/pull/5764))

### New Feature

- Add an option in admin settings to enable/enforce auto upgrades for machine deployments ([#5893](https://github.com/kubermatic/dashboard/pull/5893))
- Add support to disable changelog popup ([#5905](https://github.com/kubermatic/dashboard/pull/5905))
- Add support to import digitalocean KubeOne cluster ([#5827](https://github.com/kubermatic/dashboard/pull/5827))
- Add support to import hetzner KubeOne cluster ([#5830](https://github.com/kubermatic/dashboard/pull/5830))
- Add support to import openstack kubeone cluster ([#5951](https://github.com/kubermatic/dashboard/pull/5951))
- Configure Ingress Hostname cluster settings of OpenStack provider ([#5861](https://github.com/kubermatic/dashboard/pull/5861))
- Configure report types in schedule configuration ([#5894](https://github.com/kubermatic/dashboard/pull/5894))
- Do not set Assign Public IP by default for AWS and Azure providers ([#5938](https://github.com/kubermatic/dashboard/pull/5938))
- Support to enable accelerated networking for machines on Azure ([#5906](https://github.com/kubermatic/dashboard/pull/5906))
- The context name for OIDC Kubeconfig has been changed to the cluster ID from `default` ([#5810](https://github.com/kubermatic/dashboard/pull/5810))
- VMware Cloud Director now supports authentication using API Token ([#5885](https://github.com/kubermatic/dashboard/pull/5885))
