---
title: Hosts 
layout: default
---

## Getting Started with Hosts
---

### What is a Host?

<span class="highlight">A host is a Linux machine that is used to deploy and run all your applications. The machine can be physical or virtual, which allows you flexibility of how you want to set up your Rancher instance. </span>

Within Rancher, we provide easy instructions to add your host from the Cloud providers that are supported directly from our UI as well as instructions to add your own host if your Cloud provider is not supported yet.

### Adding a Host

From the **Hosts** tab within the Infrastructure tab, you click on **Add Host**.

![Hosts on Rancher 1]({{site.baseurl}}/img/rancher_hosts_1.png)

The first time that you add a host, you will be required to set up the [Host Registration]({{site.baseurl}}/docs/configuration/host-registration/). This setup determines what DNS name or IP address, and port that your hosts will be connected to the Rancher API. By default, we have selected the management server IP and port `8080`.  If you choose to change the address, please make sure to specify the port that should be used to connect to the Rancher API. At any time, you can update the [Host Registration]({{site.baseurl}}/docs/configuration/host-registration/). After setting up your host registration, click on **Save**.

![Host Registration on Rancher 1]({{site.baseurl}}/img/rancher_hosts_registration_1.png)

We support adding hosts directly from cloud providers or adding a host that's already been provisioned. Select which host type you want to add:

* [Adding DigitalOcean Droplet Hosts]({{site.baseurl}}/docs/infrastructure/hosts/digitalocean/)
* [Adding Amazon EC2 Hosts]({{site.baseurl}}/docs/infrastructure/hosts/amazon/)
* [Adding Packet Hosts]({{site.baseurl}}/docs/infrastructure/hosts/packet/)
* [Adding Rackspace Hosts]({{site.baseurl}}/docs/infrastructure/hosts/rackspace/)
* [Adding Custom Hosts]({{site.baseurl}}/docs/infrastructure/hosts/custom/)


## Editing Hosts
---

The options for what can be done to a host are located in the host's dropdown. From the **Infrastructure** -> **Hosts** page, the dropdown icon will appear when you hover over the host. If you click on the host name to view more details of a host, the dropdown icon is located in the upper right corner of the page. It's located next to the State of the host.

### Deactivating/Activating Hosts

Deactivating the host will put the host into an _Inactive_ state. In this state, no new containers can be deployed. Any active containers on the host will continue to be active and you will still have the ability to perform actions on these containers (start/stop/restart). The host will still be connected to the Rancher server. Select **Deactivate** from the host's dropdown menu.

When a host is in the _Inactive_ state, you can bring the host back into an _Active_ state by clicking on **Activate** from the host's dropdown menu.

### Removing Hosts

In order to remove a host from the server, you will need to do a couple of steps from the dropdown menu.

Select **Deactivate**. When the host has completed the deactivation, the host will display an _Inactive_ state. Select **Delete**. The server will start the removal process of the host from the Rancher server instance. The first state that it will display after it’s finished deleting it will be _Removed_. It will continue to finalize the removal process and move to a _Purged_ state before immediately disappearing from the UI. 

If the host was created on a cloud provider using Rancher, the host will be deleted from the cloud provider. If the host was added by using the [custom command]({{site.baseurl}}/docs/infrastructure/hosts/custom/), the host will remain on the cloud provider.
                                                                                                                                                                                                                                                                                                                                                        
> **Notes:** For custom hosts, all containers including the Rancher agent will continue to remain on the host.  

## Notes on Hosts

If your host is deleted outside of Rancher, then Rancher server will continue to show the host until it’s removed. Eventually, these hosts will show up in a _Reconnecting_ state and never be able to reconnect. You will be able to **Delete** these hosts to remove them from the UI. 


