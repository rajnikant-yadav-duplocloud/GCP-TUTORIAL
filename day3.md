# Cloud Storage in Google Cloud Platform (GCP)

Google Cloud Storage is a scalable, durable, and highly available object storage service provided by Google Cloud Platform (GCP). It allows you to store and retrieve data from anywhere on the web. Cloud Storage offers several storage classes to suit different data access patterns and cost considerations.

## Storage Classes

### Standard Storage
- Ideal for "hot" data that requires frequent access, such as websites, streaming videos, and mobile apps.
- Offers high performance and availability.
- Suitable for data that is accessed regularly and requires low-latency access.

### Nearline Storage
- Provides a cost-effective solution for data that can be stored for at least 30 days and accessed less frequently, such as data backups and long-tail multimedia content.
- Offers lower storage costs compared to Standard Storage, with slightly higher access costs.
- Designed for data that is not accessed frequently but may need to be retrieved relatively quickly when necessary.

### Coldline Storage
- Offers very low storage costs, suitable for data that can be stored for at least 90 days, including disaster recovery scenarios.
- Designed for data that is rarely accessed but needs to be retained for longer periods.
- Provides higher access costs compared to Nearline Storage but is still more cost-effective for long-term storage needs.

### Archive Storage
- Provides the lowest storage costs among all storage classes, ideal for data that can be stored for at least 365 days, including regulatory archives and compliance-related data.
- Designed for data that is rarely accessed and can tolerate higher access latency.
- Offers the highest access costs among all storage classes but is the most economical option for long-term archival storage.

## Conclusion

Choosing the right storage class in Google Cloud Storage is essential for optimizing costs and meeting the performance requirements of your applications. By understanding the characteristics of each storage class, you can effectively manage your data storage needs and maximize the value of Google Cloud Platform for your business.

For more information and detailed pricing, please refer to the [Google Cloud Storage documentation](https://cloud.google.com/storage).


# Google Cloud VPC Network

Google Cloud VPC Network is like a private space for your resources in Google Cloud. It allows you to securely connect and communicate between your virtual machines (VMs), containers, and other services.

## What is it?

Think of a VPC Network as your own private neighborhood in the Google Cloud. It provides isolation and control over your cloud resources, just like how your home network keeps your devices safe and connected.

## How to Get Started

1. **Create a VPC Network**: You can create a VPC network through the Google Cloud Console or using infrastructure as code tools.
2. **Create Subnets**: Subnets are smaller networks within your VPC network. You can put different types of resources in different subnets for better organization and security.
3. **Configure Firewall Rules**: Firewall rules control what traffic can enter and leave your VPC network.
4. **Launch Resources in Your VPC Network**: Once your VPC network is set up, you can launch your Google Cloud resources, like virtual machines, in your VPC network.

## Key Features

- **Isolation**: Your VPC Network creates a secure boundary around your resources, preventing unauthorized access from the internet.
- **Customization**: You can customize IP address ranges, subnets, and routing to suit your specific needs.
- **Connectivity**: VPC Networks allow your resources to communicate with each other securely, even if they are in different regions or zones.
- **Security**: You can set up firewall rules to control inbound and outbound traffic, keeping your network safe from threats.

## Why Use It?

- **Security**: Keeps your data and services protected from unauthorized access.
- **Scalability**: Easily scale your network as your business grows.
- **Control**: Gives you control over your network configuration and policies.
- **Flexibility**: Supports various deployment scenarios, from simple to complex architectures.

## Conclusion

Google Cloud VPC Network provides a secure and scalable foundation for your cloud infrastructure. By leveraging VPC Networks, you can build robust and reliable applications while maintaining control over your network environment.

For more information and detailed instructions on setting up a VPC Network, refer to the [Google Cloud VPC Network documentation](https://cloud.google.com/vpc).



# Creating Automatic Mode VPC using Console & Cloud Shell

Creating a Virtual Private Cloud (VPC) in automatic mode using Google Cloud Console and Cloud Shell is a straightforward process. This readme will guide you through the steps to set up a VPC quickly and easily.

## What is Automatic Mode VPC?

Automatic mode VPC is a VPC network mode that simplifies the process of creating a VPC by automatically managing IP address ranges for you. It's suitable for scenarios where you want Google Cloud to handle IP address allocation and management.

## Steps to Create Automatic Mode VPC

1. **Access Google Cloud Console**: Open the Google Cloud Console in your web browser.

2. **Navigate to VPC Networks**: Click on the "Navigation menu" (☰) in the top-left corner, then go to "VPC network" under the "Networking" section.

3. **Start VPC Creation**: Click the "+ Create VPC network" button.

4. **Enter VPC Details**: Provide a name for your VPC network and choose "Auto" for the subnet creation mode. Optionally, you can specify the region and the description for your VPC.

5. **Create VPC**: Click the "Create" button to create your VPC network. Google Cloud will automatically generate the IP address ranges for your subnets.

6. **Verify VPC Creation**: Once the VPC is created, you can verify its details in the VPC Networks page.

## Accessing Cloud Shell

1. **Open Cloud Shell**: Click the "Activate Cloud Shell" button in the Google Cloud Console toolbar.

2. **Initialize Cloud Shell**: If it's your first time using Cloud Shell, you might need to initialize it. Follow the on-screen instructions to set up Cloud Shell.

3. **Use gcloud Command**: You can use the `gcloud` command-line tool to interact with Google Cloud services. For example, you can create a VPC using the `gcloud compute networks create` command.

## Conclusion

Creating an Automatic Mode VPC using Google Cloud Console and Cloud Shell is a simple and convenient process. By following the steps outlined in this readme, you can quickly set up a VPC network without worrying about managing IP address ranges manually.

For more information and advanced configuration options, refer to the [Google Cloud VPC documentation](https://cloud.google.com/vpc).


# Creating Custom Mode VPC in Google Cloud

Creating a Custom Mode Virtual Private Cloud (VPC) in Google Cloud allows you to have full control over your network configuration, including IP address ranges and subnets. This readme will walk you through the steps to create a Custom Mode VPC easily.

## What is Custom Mode VPC?

Custom Mode VPC is a VPC network mode that gives you complete flexibility in designing your network architecture. You can specify your own IP address ranges and create subnets according to your specific requirements.

## Steps to Create Custom Mode VPC

1. **Access Google Cloud Console**: Open the Google Cloud Console in your web browser.

2. **Navigate to VPC Networks**: Click on the "Navigation menu" (☰) in the top-left corner, then go to "VPC network" under the "Networking" section.

3. **Start VPC Creation**: Click the "+ Create VPC network" button.

4. **Enter VPC Details**: Provide a name for your VPC network and choose "Custom" for the subnet creation mode. Specify the IP address range for your VPC.

5. **Create Subnets**: After creating the VPC, you can create subnets within it. Specify the subnet name, region, IP address range, and any additional configuration options.

6. **Configure Firewall Rules**: Optionally, you can configure firewall rules to control inbound and outbound traffic to and from your VPC.

7. **Verify VPC Creation**: Once the VPC and subnets are created, you can verify their details in the VPC Networks page.

## Conclusion

Creating a Custom Mode VPC in Google Cloud gives you the flexibility to design your network infrastructure according to your specific needs. By following the steps outlined in this readme, you can create a customized VPC network tailored to your requirements.

For more information and advanced configuration options, refer to the [Google Cloud VPC documentation](https://cloud.google.com/vpc).


# VPC Network Peering in Google Cloud: A Simplified Guide

VPC Network Peering establishes a private connection between two Virtual Private Cloud (VPC) networks, enabling resources in each to communicate directly. This can be beneficial for various use cases, including:

- **Connecting workloads across VPCs**: Establish private communication between VMs, containers, and App Engine instances in separate VPCs.
- **Building secure, private SaaS offerings**: Allow controlled access to your services from other VPC networks within or outside your organization.
- **Simplifying network architecture**: Reduce reliance on public internet connections for inter-VPC communication, enhancing security and control.

## Steps to Configure VPC Network Peering:

### Set Up Your VPC Networks (if not already done):

1. **Create two VPC networks** in the Google Cloud Console. Each VPC requires a name, CIDR block (IP address range), and a region.

### Initiate the Peering Connection (from VPC A):

2. **Go to the "VPC Network Peering"** section in the Google Cloud Console.
3. Click "**Create connection**."
4. Provide a name for this side of the connection (e.g., peer-to-B).
5. Select the VPC network you want to peer from (VPC A in this case).
6. Choose "**In another project**" if VPC B resides in a different project. Specify the project ID and VPC network name of VPC B.
7. Optionally, enable "**Import custom routes**" and "**Export custom routes**" if you need to advertise routes between the VPCs.
8. Click "**Create**."

### Complete the Peering Connection (from VPC B):

9. Repeat steps 2.1-2.5 in VPC B, providing a different name for this side of the connection (e.g., peer-to-A).
10. Ensure all other settings mirror those in VPC A.
11. Click "**Create**."

### Verification:

12. Once the connections are established (both show "**ACTIVE**" status), resources in VPC A can communicate directly with resources in VPC B using their private IP addresses.

## Additional Considerations:

- **Firewall Rules**: Ensure appropriate firewall rules are in place on both VPCs to allow desired traffic between them.
- **Security Groups**: If using security groups, configure them to permit communication between the peered VPCs.
- **Route Advertisement (Optional)**: If route advertisement was enabled, verify that routes are being exchanged correctly to ensure proper connectivity.

## Simplified Code Representation (Not Executable):

```python
# VPC A Configuration (peer-to-B)
vpc_a_name = "my-vpc-a"
vpc_a_cidr = "10.0.0.0/16"
region = "us-central1"

# VPC B Configuration (peer-to-A)
vpc_b_name = "my-vpc-b"
vpc_b_cidr = "10.1.0.0/16"

# Initiate Peering from VPC A
create_vpc_network_peering(
    name="peer-to-B",
    your_vpc_network=vpc_a_name,
    peer_vpc_network=vpc_b_name,
    peer_project_id="...",  # If VPC B is in a different project
    import_custom_routes=True,
    export_custom_routes=True
)

# Complete Peering from VPC B (peer-to-A)
create_vpc_network_peering(
    name="peer-to-A",
    your_vpc_network=vpc_b_name,
    peer_vpc_network=vpc_a_name,
    peer_project_id="...",  # If VPC A is in a different project
    import_custom_routes=True,
    export_custom_routes=True
)

# Configure Firewall Rules and Security Groups (if applicable)
...

# Verify Peering Status
verify_vpc_network_peering_status(vpc_a_name, "peer-to-B")
verify_vpc_network_peering_status(vpc_b_name, "peer-to-A")
