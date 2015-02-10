---
layout: default
title: "HP Helion OpenStack&#174; Troubleshooting DNS as a Service"
permalink: /helion/openstack/services/troubleshooting/dns/
product: commercial.ga

---
<!--UNDER REVISION-->

<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>
<!--

<p style="font-size: small;"> <a href="/helion/openstack/services/object/overview/">&#9664; PREV</a> | <a href="/helion/openstack/services/overview/">&#9650; UP</a> | <a href="/helion/openstack/services/reporting/overview/"> NEXT &#9654</a> </p> --->

# HP Helion OpenStack&#174;  Troubleshooting DNS as a Service

HP Helion OpenStack&#174; is an OpenStack technology coupled with a version of Linux&reg; provided by HP. This topic describes all the known issues that you might encounter. To help you resolve these issues, we have provided possible solutions.

### Configuring the `dnsmasq_dns_servers` list for the undercloud and overcloud {#config_dnas}

To enable name resolution from tenant VMs in the overcloud, it is necessary to configure the DNS servers which will be used by `dnsmasq` as forwarders.  To perform this:

### Configuring the `dnsmasq_dns_servers` list for the undercloud and overcloud {#config_dnas}

To enable name resolution from tenant VMs in the overcloud, it is necessary to configure the DNS servers which will be used by `dnsmasq` as forwarders.  To perform this:

1. Edit the `overcloud_neutron_dhcp_agent.json` file in the
`ce-installer/tripleo/hp_passthrough` directory to add the desired `dnsmasq_dns_servers`
items. 
2. Copy the `overcloud_neutron_dhcp_agent.json` file to a
new file named `undercloud_neutron_dhcp_agent.json` and configure the same
forwarders for the undercloud.

	
		{"dhcp_agent":
		  {"config":
		    [
		      {"section":"DEFAULT",
		        "values":
		          [
		            {"option":"dhcp_delete_namespaces","value":"True"},
		            {"option":"dnsmasq_dns_servers", "value":"0.0.0.0"}  <----set the value to the ip
		                                                                      address of the DNS server
		                                                                      to use.  Multiple DNS
		                                                                      servers can be specified
		                                                                      as a comma separated list.
		          ]
		      }
		    ]
		  }
		}

<hr>



<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593;</a>

