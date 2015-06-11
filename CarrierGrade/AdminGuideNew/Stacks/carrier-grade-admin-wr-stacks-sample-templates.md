---
layout: default
title: "HP Helion OpenStack&#174; Carrier Grade (Beta): Sample Templates for HP Helion OpenStack Carrier Grade"
permalink: /helion/openstack/carrier/admin/stacks/guest/
product: carrier-grade
product-version1: HP Helion OpenStack
product-version2: HP Helion OpenStack 1.1
role1: All

authors: Paul F

---
<!--UNDER REVISION-->

<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>

<!-- <p style="font-size: small;"> <a href="/helion/openstack/1.1/3rd-party-license-agreements/">&#9664; PREV</a> | <a href="/helion/openstack/1.1/">&#9650; UP</a> | NEXT &#9654; </p> -->

# HP Helion OpenStack&#174; Carrier Grade (Beta): Reporting a Guest Metric

You can evaluate selected features of Heat using sample templates included with HP Helion OpenStack Carrier Grade. The samples also demonstrate some HP Helion OpenStack Carrier Grade extensions.

<hr>
**Note:** This feature applies to the Wind River Linux servers only.
<hr>
The templates are distributed on DVD and are available online as part of the HP Helion OpenStack Carrier Grade release.

## HOT Templates: Simple

The templates in the hot/simple directory use the OpenStack HOT Template File Format. Each template in this directory provides a simple example for an OpenStack Resource type, indicated by the filename.

* **AWS_CloudFormation_Stack.yaml** - Specifies the URL of another Heat template that describes additional resources. This allows Heat
templates to be nested.

* **OS_Ceilometer_Alarm.yaml** - Creates a Ceilometer threshold alarm. This example illustrates how to specify the name of an alarm meter, and how to set parameters such as the threshold for triggering an alarm, the comparison operator to use, the evaluation period for the comparison, and so on.

* **OS_Cinder_Volume.yaml** - Creates a Cinder volume of a particular size (in gigabytes).

* **OS_Cinder_VolumeAttachment.yaml** Creates an attachment, or mount point, for a Cinder volume within a VM instance. 

* **OS_Glance_Image.yaml** - Creates a Glance image, specifying the image file, container format, disk format, and so on.

* **OS_Heat_AccessPolicy.yaml** - Specifies which types of resource to include in the results for heat stack-show stackname and heat resource-show stackname resourcename.

* **OS_Heat_CWLiteAlarm.yaml** - Creates a threshold alarm using OS::Heat::CWLiteAlarm. This is an older and less capable alarm resource than OS::Ceilometer::Alarm. If possible, use OS::Ceilometer::Alarm instead.

* **OS_Heat_InstanceGroup.yaml** - Creates a specified number of instances using a specified launch configuration. The number of instances is controlled by the size property. This invokes AWS::AutoScaling::LaunchConfiguration, which effectively restricts the launched instances to AWS::EC2::Instance resources.

* **OS_Neutron_FloatingIP.yaml** - Creates a floating IP address for an external tenant network, in order to represent an internal port IP address using NAT.

* **OS_Neutron_Net.yaml** - Creates a tenant network, to which other resources such as OS::Neutron::Port, OS::Neutron::Subnet, and
OS::Nova::Server can refer.

* **OS_Neutron_Port.yaml** - Creates a port for a VM instance on a tenant network. The VM instance can use this to attach to the tenant network.

* **OS_Neutron_ProviderNet.yaml** - Creates a provider network, specifying the name and type (flat or vlan).

* **OS_Neutron_ProviderNetRange.yaml** - Creates a segmentation range for a provider network, specifying the provider network, and the minimum and maximum values of the range.

* **OS_Neutron_QoSPolicy.yaml** - Creates a Neutron QoS policy, which specifies a packet scheduling weight. The policy can be referenced by a tenant network to modify the scheduling weight of AVS ingress traffic from VMs for the tenant network.

* **OS_Neutron_Router.yaml** - Creates an IP router for tenant networks. The router's IP interfaces to tenant network subnets are established as shown in OS_Neutron_RouterInterface.yaml.

* **OS_Neutron_RouterGateway.yaml** - Creates a router gateway interface for the specified router on the specified external network. The IP address for the interface is allocated from the external network subnet, and a default IP route is created using the gateway_ip of the subnet.

* **OS_Neutron_RouterInterface.yaml**  - Creates an IP interface on an existing router for an existing IP subnet.

* **OS_Neutron_SecurityGroup.yaml** - Creates a Security Group that defines a stateless IP Filter. This Security Group can be referenced by a Server (VM) resource that requires a stateless IP Filter for ingress and egress traffic to or from the VM.

* **OS_Neutron_Subnet.yaml** - Creates an IP subnet on a specified tenant network. The IP subnet and mask are required, and the DHCP support status (enabled or disabled) must be specified . DNS nameservers can optionally be specified.

* **OS_Nova_Flavor.yaml** - Creates a Nova flavor that describes the resource requirements for a VM, such as the required RAM, number of vCPUs, disk size, and so on.

* **OS_Nova_KeyPair.yaml** - Creates a secure shell (SSH) key pair to enable secure login to a launched VM. The created key pair is
referenced in OS::Nova::Server.

* **OS_Nova_Server.yaml** - Creates a VM Instance, specifying flavor, image and network attachments.

* **OS_Nova_ServerGroup.yaml** - Creates a server group, which is a set of VM instances (OS::Nova::Server) that can be assigned group attributes such as compute-node-affinity or antiaffinity. To assign a VM instance to a server group, use NovaSchedulerHints within the OS::Nova::Server resource; for example, NovaSchedulerHints: [{Key: 'group', Value: {Ref: server_group_name}}].

* **OS_SysInv_HostInterface.yaml** - Creates a Layer 2 interface on a compute node, specifying the compute node, the interface type (eth or lag), the port or ports, the network type (mgmt, oam, infra, or data), and for a data network, the provider networks.

## HOT Templates: Scenarios

The templates in the hot/scenarios directory use the OpenStack HOT Template File Format. Each template in this directory provides an example scenario involving several Resource types.

* **BootFromCinder.yaml** - Creates a bootable Cinder volume, and uses it to launch a VM instance. The Cinder volume is used as the VM's virtual boot disk.

* **DPDK_Flavors.yaml** - Creates four different flavors for DPDK-type guest applications.

* **Launch2NamedVMs.yaml** - Creates a static service containing two virtual machines attached to the same network. This template illustrates the HP Helion OpenStack Carrier Grade extension for
simplified VM instance naming, as described in [Extensions to Heat](/helion/openstack/carrier/admin/stacks/wr/). The template is used as an example in Creating a Static Resource.

* **LabSetup.yaml** - Similar to Provisioning.yaml, but also creates IP subnets on the tenant networks, routers on the tenant networks, and router gateways.

* **NetworkSetup.yaml** - Creates three tenant networks, five subnets, and two routers, each with an external gateway interface and an internal interface.

* **Provisioning.yaml** - Provisions a variety of resources, including provider networks, segmentation ranges, tenant networks, key pairs, Glance images, and flavors, some of which are implemented as a nested stack (by referencing another Heat template).

* **SimpleServer.yaml** - Creates a single VM instance. This template illustrates several custom extensions, incuding support for multiple network attachments, the use of `name` or `subnet_name` to refer to the network, and the ability to specify the vifmodel per network attachment (or NIC).

* **DemoAutoScaling.yaml** - Creates a single Load Balancer VM, and an AutoScalingGroup of server VMs that scales based on link utilization. This demonstrates a typical in/out autoscaling use case. The template also illustrates the use of the RAW UserDataType to pass user data that does not require cf_init for parsing.

* **VMAutoScaling.yaml** - Creates an up/down autoscaling service that responds to CPU load by adding or removing vCPUs for a VM instance. NestedStack.yaml Creates an OS::Cinder::Volume, and an OS::Nova::Server resource that uses the volume. This stack is used as a nested stack within the NestedAutoScale.yaml template. NestedAutoScale.yaml Creates an autoscaling stack, using a nested stack. The stack NestedStack.yaml, which contains a VM and its Cinder Volume, is scaled in and out.

## CFN Template

The templates in the cfn directory use the AWS Cloud Formation 

* **AutoScaleWithNamePattern.yaml** - Creates an in/out autoscaling service with simplified names for VM instances, using a HP Helion OpenStack Carrier Grade extension. The service responds to CPU load as reported by a platform-generated metric.

*  **ComputeScale.yaml** - Creates an in/out autoscaling service that responds to CPU load as reported by the compute node hosting the VM.

* **CPUScale.yaml** - Creates an in/out autoscaling service that responds to CPU load as reported by the guest VM, using a custom metric generated within the guest. For more about this template, see [Resource Scaling (Autoscaling)](/helion/openstack/carrier/admin/stacks/autoscale/)

* **MemScale.yaml** - Creates an in/out autoscaling service that responds to memory usage as reported by the guest VM, using a custom metric generated within the guest. To push the metric to the HP Helion OpenStack Carrier Grade platform, the guest must contain cloud-init and heatcfntools.

* **TenantScale.yaml** - Demonstrates the use of a parameter to supply user credentials. This template can be run by a tenant user. It creates an in/out autoscaling service that responds to CPU load as reported by the guest VM. To push the metric to the HP Helion OpenStack Carrier Grade platform, the guest must contain cloud-init and heatcfntools.


<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>
 
----