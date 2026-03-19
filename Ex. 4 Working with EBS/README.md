# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**: Vedhavalli S________________________________
* **Register Number**: 212223090029 _____________________
* **Date of Submission**: 19/03/26__________________

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

(Write the steps you followed in your own words)

1. -First, I logged in to the AWS Management Console.

I navigated to the EC2 Dashboard.

I explored the Elastic Block Store (EBS) section under EC2.

I observed different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

I clicked on “Volumes” and selected “Create Volume.”

I chose the required volume type (General Purpose SSD – gp3).
I entered the desired storage size (for example, 8 GB).

I selected the same Availability Zone as my running EC2 instance.

I clicked on “Create Volume” to create the EBS volume.

After the volume was created, I selected the volume and clicked on “Attach Volume.”

I selected my running EC2 instance and attached the volume as a new device (for example, /dev/xvdf).

I connected to my EC2 instance using SSH from the terminal.

I checked the attached disk using the command lsblk to verify the new volume.

I formatted the attached volume using the command:
sudo mkfs -t ext4 /dev/xvdf

I created a directory to mount the volume using:
sudo mkdir /mnt/ebs

I mounted the volume to the directory using:
sudo mount /dev/xvdf /mnt/ebs

I verified that the volume was mounted successfully using the df -h command.

I created sample files inside the mounted directory using:
sudo touch /mnt/ebs/sample.txt--


---

## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="591" height="608" alt="image" src="https://github.com/user-attachments/assets/6483e2d6-ada5-4311-8385-aa4724ec933f" />


---

### Screenshot 2: EBS Volume Attached to EC2
<img width="592" height="614" alt="image" src="https://github.com/user-attachments/assets/5d0aeeb6-1fac-4fda-830c-740bf4c39536" />
<img width="960" height="1044" alt="Screenshot 2026-02-27 163520" src="https://github.com/user-attachments/assets/20ef1511-245f-427a-abd6-db6196d7b5fb" />



---

### Screenshot 3: Mounted Volume with Data

<img width="791" height="880" alt="image" src="https://github.com/user-attachments/assets/f213112f-0fec-4793-99a6-838bc3a965a9" />
<img width="799" height="820" alt="image" src="https://github.com/user-attachments/assets/b48a4ad6-3e06-4b87-85b8-61a01cde812b" />


---

## Result / Conclusion

This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.
