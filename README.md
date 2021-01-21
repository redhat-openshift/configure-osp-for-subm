# Configure Submariner Security Group Prerequisites for OpenStack Platform 

Submariner Gateway nodes need to be able to accept traffic over UDP ports (4500 and 500 by default) when using IPsec.
Submariner also uses UDP port 4800 to encapsulate traffic from the worker and master nodes to the Gateway nodes, and TCP port 8080 to
retrieve metrics from the Gateway nodes.

`configure_osp.sh` is a script designed to update your OpenShift installation on OpenStack infrastructure for Submariner deployments,
handling the requirements specified above.

You can use the `configure_osp.sh` script on your OpenShift install directory with your openrc credentials correctly sourced.

```bash
cd my-cluster-openshift-install-dir
curl https://raw.githubusercontent.com/sridhargaddam/configure-osp-for-subm/main/configure_osp.sh -L -O
chmod a+x ./configure_osp.sh
./configure_osp.sh
```

Certain parameters, such as the IPsec UDP ports can be customized before running the script. For example:

```bash
export IPSEC_NATT_PORT=4501
export IPSEC_IKE_PORT=501
```

## Prerequisites

You will need:

* [Terraform](https://releases.hashicorp.com/terraform/) version 0.12. Maximum compatible version is 0.12.12
