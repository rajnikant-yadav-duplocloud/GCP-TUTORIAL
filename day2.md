# GCP Resource Hierarchy

## Organization: 
This is the top boss, like the main folder on your computer. It groups everything together.
## Folders (optional): 
These are sub-folders within the organization, helping you categorize projects by department, team, or however you like.

## Projects

Projects are the top-level organizing units in GCP. Think of them as containers that hold all the resources related to a particular application or service. You can have multiple projects in your GCP account, each with its own set of resources and permissions.

## Resources

Within a project, resources represent the various services and components you use, such as virtual machines, databases, storage buckets, and more. These resources are organized hierarchically within the project.

## Permissions

Permissions in GCP are granted at different levels of the resource hierarchy. You can assign permissions at the project level, folder level, or individual resource level, depending on your requirements. This allows you to control who can access and manage specific resources within your GCP environment.


# Google Cloud Compute Engine

Compute Engine is Google's on-demand virtual machine service. Think of virtual machines (VMs) as computers in the cloud that you can set up and use just like your own computer.

## 1. Predefined vs. Custom VMs:

### Predefined VMs:
These are like pre-built computers with set amounts of processing power, memory, and storage. They're quick and easy to use, ideal for common tasks like running websites or small applications.

### Custom VMs:
Imagine building your own computer. You choose the exact CPU, memory, and storage you need for your specific workload. This gives you more control but takes more time to set up.

## 2. Types of Predefined VMs:

Google offers a variety of pre-built VM options to suit different needs. They have categories like:

- General purpose: Good for all-around tasks like web servers and development environments.
- Compute optimized: Perfect for processing-intensive workloads like scientific computing.
- Memory optimized: Ideal for applications that need a lot of memory, like databases.

## 3. Advantages of GCE over Other Cloud Providers:

- Performance: Built on Google's top-notch global infrastructure, offering high performance and reliability.
- Scalability: Easily scale your VMs up or down as your needs change.
- Cost-effective: Pay only for the resources you use, with per-second billing.
- Integration: Integrates seamlessly with other Google Cloud services.

## 4. Benefits of Custom VMs:

- Full Control: Tailor your VM to your exact needs, maximizing performance and efficiency.
- Flexibility: Perfect for unique workloads that require specific configurations.
- Cost Optimization: You only pay for the resources you choose, potentially saving money.


# Google Compute Engine Pricing and VM Disk Types

## Pricing Options

Google Compute Engine offers various pricing options:

- **Sustained Use Discounts/On-Demand:** Automatically applied for consistent usage over time, providing discounts for each vCPU and GB of memory used.
- **Commitments:** Suitable for predictable workloads, where you commit to using a specific amount of vCPUs and memory for future usage.

## VM Disk Types

GCE offers different types of VM disks:

- **Standard Persistent Disks:** Reliable and cost-effective storage for VM instances.
- **SSD Persistent Disks:** High-performance solid-state drives suitable for high-I/O workloads.
- **Local SSDs:** Temporary storage directly attached to the VM instance, providing high-speed, low-latency access.

## Cost Estimation
You can estimate the cost of running a Compute Engine VM instance by considering the machine type, disk type, and other related pricing factors. Sustained use discounts and commitments can help optimize costs for your specific workload and usage patterns.


# How to Create a VM in Google Cloud

## Steps:

1. **Access the Google Cloud Console:** 
   - Go to [Google Cloud Console](https://console.cloud.google.com/) and sign in with your Google Cloud account.

2. **Navigate to Compute Engine:** 
   - In the left-hand navigation menu, select "Compute Engine" and then "VM instances."

3. **Create a VM Instance:** 
   - Click the "Create instance" button.

4. **Specify Basic Settings:**
   - **Name:** Enter a descriptive name for your VM (e.g., "my-first-vm").
   - **Region:** Choose a geographic location where your VM will reside, considering factors like latency and regulatory requirements.
   - **Zone (Optional):** Select a specific zone within the region for increased fault tolerance.

5. **Machine Configuration:**
   - **Machine type:** Choose the VM's processing power (CPU), memory (RAM), and storage capacity based on your workload requirements.
   - **Boot disk:** Select an operating system image for your VM, such as Ubuntu, Debian, CentOS, or Windows Server. You can also create a custom image if needed.

6. **Configure Disks (Optional):**
   - Add additional storage disks if your VM requires more space beyond the boot disk.

7. **Networking:**
   - **Network interface:** Specify a network for your VM to communicate with other resources in your GCP project.
   - **External IP (Optional):** Enable an external IP address if you need to access your VM from the internet, considering security implications.
   - **Firewall:** Define firewall rules to control incoming and outgoing traffic to your VM, such as allowing SSH access or other necessary connections.

8. **Management, Security, and Disk Encryption (Optional):**
   - Review and adjust settings for features like metadata, startup scripts, security keys, and disk encryption based on your specific needs.

9. **Create:**
   - Once you're satisfied with your configuration, click the "Create" button to provision and launch your VM instance.

## Additional Tips:

- Google Cloud offers a free tier with limited VM usage for new users. Check their documentation for details.
- Consider using the Google Cloud SDK (command-line tool) for scripting VM creation and management tasks if you need to create multiple VMs frequently.
- Explore preconfigured VM images provided by Google Cloud or third-party vendors to save setup time.

By following these steps, you'll have a VM up and running in Google Cloud, ready to host your applications or workloads.









# Create and Manage VM Instances using Cloud Shell

## Introduction:

Cloud Shell is a web-based command-line interface (CLI) provided by Google Cloud Platform (GCP) that allows you to manage your resources directly from the browser. This README will guide you through the process of creating and managing VM instances using Cloud Shell.

## Steps:

1. **Access Cloud Shell:**
   - Open your web browser and navigate to the [Google Cloud Console](https://console.cloud.google.com/).
   - Click on the Cloud Shell icon located at the top right corner of the console.

2. **Creating a VM Instance:**
   - Use the `gcloud compute instances create` command to create a VM instance.
     ```
     gcloud compute instances create INSTANCE_NAME --machine-type MACHINE_TYPE --zone ZONE
     ```
     - Replace `INSTANCE_NAME` with your desired name for the VM instance.
     - Replace `MACHINE_TYPE` with the desired machine type (e.g., `n1-standard-1`).
     - Replace `ZONE` with the preferred zone for the VM instance (e.g., `us-central1-a`).

3. **Managing VM Instances:**
   - You can manage your VM instances using various `gcloud compute` commands, such as:
     - Start: `gcloud compute instances start INSTANCE_NAME --zone ZONE`
     - Stop: `gcloud compute instances stop INSTANCE_NAME --zone ZONE`
     - Delete: `gcloud compute instances delete INSTANCE_NAME --zone ZONE`

4. **Accessing VM Instances:**
   - You can SSH into your VM instance directly from Cloud Shell using the following command:
     ```
     gcloud compute ssh INSTANCE_NAME --zone ZONE
     ```
     - Replace `INSTANCE_NAME` and `ZONE` with the values you used during VM creation.

## Additional Tips:

- Cloud Shell provides a persistent home directory (mounted to your Google Cloud account) and 5GB of persistent storage.
- You can customize your Cloud Shell environment by installing additional tools or configuring settings.
- Remember to manage your resources efficiently to avoid unnecessary costs, especially for running VM instances.

By following these steps, you can easily create and manage VM instances using Cloud Shell directly from your web browser.



# Changing Machine Type for a VM in Google Cloud Platform 

## Introduction:

In Google Cloud Platform (GCP), you might need to adjust the machine type (CPU and memory configuration) of a virtual machine (VM) to better suit your application's requirements or optimize costs. This guide will walk you through the simple steps to change the machine type for a VM in GCP.

## Steps:

1. **Access Google Cloud Console:**
   - Open your web browser and go to the [Google Cloud Console](https://console.cloud.google.com/).
   - Sign in with your Google Cloud account.

2. **Navigate to Compute Engine:**
   - In the left-hand navigation menu, select "Compute Engine" and then "VM instances."

3. **Select the VM Instance:**
   - Locate the VM instance for which you want to change the machine type.
   - Click on the checkbox next to the instance to select it.

4. **Stop the VM Instance (if running):**
   - If the VM instance is running, you'll need to stop it before changing the machine type.
   - Click the "Stop" button at the top of the page to stop the VM.

5. **Edit the VM Instance:**
   - With the VM instance selected, click the "Edit" button at the top of the page.

6. **Change Machine Type:**
   - In the "Machine type" section, click on the dropdown menu to select a new machine type.
   - Choose the desired machine type that fits your requirements.

7. **Save Changes:**
   - After selecting the new machine type, click the "Save" button to apply the changes.

8. **Start the VM Instance (if necessary):**
   - Once the changes are saved, you can start the VM instance again if it was previously stopped.

## Alternative Using Cloud Shell:

**Open Cloud Shell:**
  - Click the "Activate Cloud Shell" button in the console.

**Stop VM:**
  ```bash
  gcloud compute instances stop <INSTANCE_NAME> --zone <ZONE>
```

Use code with caution.

**Change Machine Type:**

```bash
gcloud compute instances set-machine-type <INSTANCE_NAME> \
  --machine-type <NEW_MACHINE_TYPE> \
  --zone <ZONE>
```

**Restart VM:**
```bash
gcloud compute instances start <INSTANCE_NAME> --zone <ZONE>
```



## Resize Your Persistent Disk in GCP (Console & Cloud Shell)

This guide explains how to increase the storage capacity of a persistent disk attached to a VM in Google Cloud Platform (GCP), using both the Google Cloud Console and Cloud Shell.

**Important Note:** You can only **increase** the size of a persistent disk, not decrease it.

**Prerequisites:**

- A Google Cloud account ([https://cloud.google.com/](https://cloud.google.com/))
- A running VM instance with a persistent disk attached

**Using the Google Cloud Console:**

1. **Navigate to Disks:** In the left navigation menu, select "Compute Engine" and then "Disks."

2. **Find Your Disk:** Locate the disk you want to resize by name or size.

3. **Edit Disk:** Click the name of the disk to open its details page.

4. **Increase Size:** Click the "Edit" button. Under "Capacity," enter the new desired size in gigabytes (GB).

5. **Save Changes:** Click "Save" to apply the resize operation.

**Using Cloud Shell:**

1. **Activate Cloud Shell:** In the Google Cloud Console, click the "Activate Cloud Shell" button.

2. **Identify Disk and Zone:** Use the `gcloud compute disks list` command to view your disks and their zones.

3. **Resize Disk:** Execute the following command, replacing placeholders with your values:

```bash
gcloud compute disks resize <DISK_NAME> --size <NEW_SIZE_GB> --zone <ZONE>
```

- `<DISK_NAME>`: The name of your persistent disk.
- `<NEW_SIZE_GB>`: The desired new size in GB.
- `<ZONE>`: The zone where the disk resides (found in the `gcloud compute disks list` output).

**Next Steps (on the VM):**

1. **Connect to VM:** SSH into your VM using your preferred method (e.g., SSH client).

2. **Identify Filesystem:** Use the `df -h` command to list disk usage and identify the filesystem associated with your resized disk.

3. **Resize Filesystem (Linux):** If needed, use tools like `parted` or `resize2fs` to resize the filesystem to utilize the additional space. Here's an example using `parted`:
- Run `sudo parted /dev/sdX` (replace `/dev/sdX` with the device identifier of your disk).
- Use the `resizepart` command to resize the partition.
- Exit `parted` and run `sudo resize2fs /dev/sdXN` to resize the filesystem (replace `/dev/sdXN` with the appropriate partition).

4. **Verify Filesystem:** Run `df -h` again to confirm that the filesystem has been resized successfully.

**Remember:** Resizing the filesystem might require additional steps depending on your specific setup.

**Additional Tips:**

- Consider stopping your VM instance before resizing the disk for a cleaner operation.
- Double-check the new disk size before saving or running the resize command.
- Review the official documentation for more details and advanced options: [https://cloud.google.com/compute/docs/disks/resize-persistent-disk](https://cloud.google.com/compute/docs/disks/resize-persistent-disk)



# Understanding Public Images, Custom Images, and Machine Images in GCP

## Introduction:

Google Cloud Platform (GCP) offers various types of images that you can use to create virtual machine (VM) instances. These images serve as templates for the operating system and software configuration of your VMs. Understanding the differences between public images, custom images, and machine images is essential for efficient resource management and deployment in GCP.

## Public Images:

- **Definition:** Public images are pre-configured disk images provided by Google Cloud, containing various operating systems and software configurations.
- **Usage:** You can use public images to quickly deploy VM instances without the need to create or manage your own images.
- **Examples:** Google provides a range of public images, including images for popular Linux distributions (e.g., Ubuntu, Debian) and Windows Server.
- **Benefits:** Public images are convenient for getting started with VMs and are regularly updated and maintained by Google.

## Custom Images:

- **Definition:** Custom images are disk images created from existing VM instances or imported from your on-premises environment.
- **Usage:** You can create custom images to capture a specific state of your VM, including installed software, configurations, and data.
- **Examples:** You might create custom images after installing and configuring your application software or for compliance purposes.
- **Benefits:** Custom images allow you to replicate consistent environments and configurations across multiple VM instances.

## Machine Images:

- **Definition:** Machine images are higher-level abstractions in GCP that include not only disk images but also instance configurations and metadata.
- **Usage:** Machine images provide a more comprehensive solution for capturing and managing VM configurations and settings.
- **Examples:** Google Cloud's Compute Engine provides managed instance groups that can be based on machine images, enabling automated scaling and management.
- **Benefits:** Machine images streamline the deployment and management of VM instances, especially in automated or orchestrated environments.

## Conclusion:

Understanding the differences between public images, custom images, and machine images in Google Cloud Platform is crucial for effectively managing your VM deployments. Public images offer convenience and ease of use, while custom images and machine images provide flexibility and control over your VM configurations and deployments.

By leveraging the appropriate image types based on your requirements, you can optimize your infrastructure deployment and management workflows in GCP.

For more detailed information and guidance on using images in Google Cloud Platform, refer to the official documentation: [Google Cloud Documentation](https://cloud.google.com/docs).
