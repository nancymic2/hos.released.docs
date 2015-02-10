---
layout: default-devplatform
title: "Application Lifecycle Service Client Command Reference"
permalink: /als/v1/user/reference/client-ref/services/
title: "Application Lifecycle Service Command Line Client Reference: Services"
product: devplatform

---
<!--UNDER REVISION-->

# HP Helion Development Platform: ALS Command Reference: Services

- [helion marketplace](#command-marketplace): List the supported service plans of the target for the current or specified space. This command is new in HP Helion OpenStack&reg; 1.1. 
- [helion purge-service-offerings](#command-purge-service-offerings): Purge all offerings of the service type from the system. **Warning** use with caution.  This command is new in HP Helion OpenStack&reg; 1.1. 
- [helion service](#command-service): Show information about the named service.
- [helion services](#command-services): List the supported and provisioned services of the target.
	
## Syntax

	helion [options] command [arguments] [command-options]
For more information, use the **helion help**, **helion help [*command*]**, or **helion options** commands.

<hr>

## helion marketplace {#command-marketplace}
List the supported service plans of the target, for the current or specified space. This command is new in Helion OpenStack&reg; 1.1.

<table style="text-align: left; vertical-align: top; width:650px;">
<tr style="background-color: #C8C8C8;">
<td style="width: 200px;"><b>Option</b></td><td><b>Description</b></td>
</tr><tr><td>--json</td>
<td>Print raw json as output, not human-formatted data.</td>
</tr><tr>
<td>--organization, -o</td>
<td>The once-off organization to use for the current operation.</td>
</tr>    <tr><td>--space</td>
<td>The once-off space to use for the current operation, specified by
name. Cannot be used together with <i>--space-guid</i>.</td>
</tr>    <tr><td>--space-guid</td>
<td>The once-off space to use for the current operation, specified by
guid. Cannot be used together with <i>--space</i>.</td>
</tr>    <tr><td>--target</td>
<td>The once-off target to use for the current operation.</td>
</tr>    <tr><td>--token</td>
<td>The once-off authentication token to use for the current
operation.</td>
</tr>    <tr><td>--token-file</td>
<td>Path to an existing and readable file containing the targets and
authorization tokens.</td>
</tr>
</table>

    
## helion purge-service-offerings <*service*>  {#command-purge-service-offerings}
Purge all offerings of the service type from the system. **Warning**: Do this **only** for services that have already had their brokers killed, leaving behind orphans. This command is new in Helion OpenStack&reg; 1.1.


<table style="text-align: left; vertical-align: top; width:650px;">
<tr style="background-color: #C8C8C8;">
<td style="width: 200px;"><b>Option</b></td><td><b>Description</b></td>
</tr><<tr><td>--provider</td>
<td>The service provider. Use this to disambiguate between multiple
providers of the same vendor/type.</td>
</tr> <tr><td>--target</td>
<td>The once-off target to use for the current operation.</td>
</tr>  <tr><td>--token</td>
<td>The once-off authentication token to use for the current
operation.</td>
</tr>    <tr><td>--token-file</td>
<td>Path to an existing and readable file containing the targets and
authorization tokens.</td>
</tr>
   <tr><td>--version</td>
<td>The service version. Use this to disambiguate between multiple versions of the same vendor/type.</td>
</tr>
</table>

	    
## helion service <*name*> {#command-service} 
Show the information about the named service.

<table style="text-align: left; vertical-align: top; width:650px;">
<tr style="background-color: #C8C8C8;">
<td style="width: 200px;"><b>Option</b></td><td><b>Description</b></td>
</tr><tr><td>--json</td>
<td>Print raw json as output, not human-formatted data.</td>
</tr><tr>
<td>--organization, -o</td>
<td>The once-off organization to use for the current operation.</td>
</tr>    <tr><td>--space</td>
<td>The once-off space to use for the current operation, specified by
name. Cannot be used together with <i>--space-guid</i>.</td>
</tr>    <tr><td>--space-guid</td>
<td>The once-off space to use for the current operation, specified by
guid. Cannot be used together with <i>--space</i>.</td>
</tr>    <tr><td>--target</td>
<td>The once-off target to use for the current operation.</td>
</tr>    <tr><td>--token</td>
<td>The once-off authentication token to use for the current
operation.</td>
</tr>    <tr><td>--token-file</td>
<td>Path to an existing and readable file containing the targets and
authorization tokens.</td>
</tr>
</table>
    
## helion services {#command-services}
List the supported and provisioned services of the target.

<table style="text-align: left; vertical-align: top; width:650px;">
<tr style="background-color: #C8C8C8;">
<td style="width: 200px;"><b>Option</b></td><td><b>Description</b></td>
</tr><tr><td>--json</td>
<td>Print raw json as output, not human-formatted data.</td>
</tr><tr>
<td>--organization, -o</td>
<td>The once-off organization to use for the current operation.</td>
</tr>    <tr><td>--space</td>
<td>The once-off space to use for the current operation, specified by
name. Cannot be used together with <i>--space-guid</i>.</td>
</tr>    <tr><td>--space-guid</td>
<td>The once-off space to use for the current operation, specified by
guid. Cannot be used together with <i>--space</i>.</td>
</tr>    <tr><td>--target</td>
<td>The once-off target to use for the current operation.</td>
</tr>    <tr><td>--token</td>
<td>The once-off authentication token to use for the current
operation.</td>
</tr>    <tr><td>--token-file</td>
<td>Path to an existing and readable file containing the targets and
authorization tokens.</td>
</tr>
</table>