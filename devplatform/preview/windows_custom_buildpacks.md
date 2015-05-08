---
layout: default-devplatform
title: "HP Helion 1.2 Development Platform:  Deploying Windows Applications with the IIS Buildpack"
permalink: /helion/devplatform/preview/buildpack/
product: devplatform
product-version1: HP Helion Development Platform
product-version2: HP Helion Development Platform 1.2
role1: Systems Administrator 
role2: System Engineer
role3: Cloud Administrator
role4: Network Administrator
role5: Application Developer
Role6: Security Engineer
role7: Application Developer 
role8: ISV Developer
role9: Service Developer
authors: Patrick F

---
<!--UNDER REVISION-->

# HP Helion 1.2 Development Platform: Deploying Windows Applications with the IIS Buildpack

*Windows and IIS are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries.*

A **Buildpack** is a collection of scripts that specify what frameworks and runtimes are to be deployed with an application. 

When you build and deploy a Windows application, the following steps take place:

1. You will be prompted for connection data (Endpoint, login, and password), and whether to ignore SSL errors. You should check "Ignore SSL errors" in the dialog if your deployment environment uses self-signed SSL certificates.

	<img src="media/windows_publish_credentials.png" />
2. Application settings are collected from <code>manifest.yml</code>.
3. If a local build is requested, projects in the solution directory are deployed to a temporary folder and compiled with **MSBuild**.
4. Projects are deployed using the **CloudFoundry MS Build Tasks**.

After the project is deployed, the IIS Buildpack performs the following tasks:

5. If there is no solution or project file present, the application is simply copied to the "Output Path" directory specified in the project configuration.
6. If a project file is present, but no solution file, the application is built with **MSBuild** with no parameters, and the built application is copied to the "Output Path" directory specified in the project configuration.
7. If a solution file is present, NuGet packages listed in the solution file will be restored, and the application will be built with **MSBuild**, and the application is copied to the "Output Path" directory specified in the project configuration.


This process can fail if any of the following are true:

1. There is more than one solution file present
2. The number of folders in the deployed site is not correct
3. There is no <code>Web.Config</code> file in the root of the "Output Path" directory after deployment

The following diagram shows all of the steps in the pre-publish and post-publish process:

<img src="media/windows_publish_flowchart.png" />