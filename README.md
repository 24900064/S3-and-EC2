# Experiment No. 2 — Cloud Storage Creation (S3) and Launching an EC2 Instance in AWS

## Aim
To create an Amazon S3 bucket for cloud storage and launch a virtual machine using Amazon EC2 in the AWS Management Console.

## Objectives
After completing this experiment, students will be able to:
- Understand AWS Cloud Storage (Amazon S3)
- Create and manage S3 buckets
- Upload and organize files in cloud storage
- Launch an EC2 virtual server
- Connect to an EC2 instance
- Understand cloud computing infrastructure services

## Software Requirements
- Laptop/Desktop
- Internet connection
- AWS Academy Learner Account / AWS Free Tier Account
- Modern web browser (Chrome/Edge)

## Theory

### Amazon S3 (Simple Storage Service)
Amazon S3 is an object storage service provided by AWS that stores unlimited amounts of data with high durability and availability.

**Features:**
- Unlimited storage
- 99.999999999% (11 nines) durability
- High availability
- Secure storage
- Versioning
- Lifecycle management
- Encryption

---

## Part A — Creating an Amazon S3 Bucket

1. Open the AWS console: [https://aws.amazon.com/console/](https://aws.amazon.com/console/)  

<img width="1917" height="1042" alt="image" src="https://github.com/user-attachments/assets/125d492a-38c9-4558-ad5c-2ef32b563239" />

2. Log in:
   - Click **Sign in using root user email**
   - Enter the registered email address
   - Enter the AWS password
   - Complete the verification process

<img width="1917" height="1081" alt="Screenshot 2026-10-31 101041" src="https://github.com/user-attachments/assets/35452d9f-7eac-4eba-9d15-4cd0c10f0eef" />

3. Type **S3** in the search box.

<img width="1917" height="1092" alt="Screenshot 2026-10-31 101135" src="https://github.com/user-attachments/assets/484a2d05-a5ab-44ac-8832-0d1402820d71" />

5. Click **Amazon S3**.
6. Click **Create bucket**.
7. Enter the following details:

   | Parameter    | Value                      |
   |--------------|-----------------------------|
   | Bucket type  | General purpose            |
   | Bucket name  | `student-cloud-storage-001` |
   | AWS Region   | Asia Pacific (Mumbai)      |

<img width="1915" height="1075" alt="Screenshot 2026-10-31 101907" src="https://github.com/user-attachments/assets/c1f663f9-1851-4f7f-90ae-fa00b8346cee" />

9. Leave the remaining settings unchanged.
11. Click **Create bucket**.

<img width="1917" height="1023" alt="image" src="https://github.com/user-attachments/assets/43316804-e1d0-4f6b-a934-293cec9c38fa" />

12. Click **Upload**.
13. Upload the following files:
    - PDF file
    - Word document
    - Image file

    
**Example bucket structure:**
```
student-cloud-storage-001
│
├── Cloud.pdf
├── Assignment.docx
├── Image.jpg
└── Notes.pdf
```
<img width="1917" height="1032" alt="Screenshot 2026-10-31 102758" src="https://github.com/user-attachments/assets/890bce95-7b74-4884-8235-cd4bad34fe72" />

---

## Part B — Launching an Amazon EC2 Instance

1. Type **EC2** in the AWS search bar.

<img width="1917" height="1086" alt="Screenshot 2026-10-31 102842" src="https://github.com/user-attachments/assets/fbcc6884-22a3-4107-a582-02a00fc33f1d" />

2. Open the **EC2 Dashboard**.

<img width="1917" height="1081" alt="Screenshot 2026-10-31 102924" src="https://github.com/user-attachments/assets/8fe6e29d-74f9-457d-a3c0-16541713ba1d" />

3. Click **Launch instance**.
4. Enter the instance name: `CloudLabVM`
5. Select the operating system:
   - Amazon Linux 2023
   - Ubuntu Server
6. Select the instance type: `t3.micro`
7. Create a key pair:

   | Parameter      | Value        |
   |----------------|--------------|
   | Key pair name  | `CloudLabKey`|
   | Key pair type  | RSA          |
   | File format    | `.pem`       |

8. Download the `CloudLabKey.pem` file.
9. Configure network settings:
   - ✅ Allow SSH traffic (Port 22)
   - ✅ Allow HTTP traffic (Port 80)
   - ✅ Allow HTTPS traffic (Port 443)
10. Set the storage size: `8 GiB`
11. Click **Launch instance**.
    <img width="1917" height="1085" alt="image" src="https://github.com/user-attachments/assets/ad3ffef0-5c10-4d56-afe5-fca89253ebea" />

13. Wait until the status changes:

<img width="1917" height="1077" alt="Screenshot 2026-10-31 103617" src="https://github.com/user-attachments/assets/09810171-6131-4cb1-b11d-71ce7f3febbe" />


    ```
    Pending → Running
    ```

### Connecting to the EC2 Instance
1. Open **EC2**.
2. Select the instance.

<img width="1535" height="959" alt="Screenshot 2026-09-04 215454" src="https://github.com/user-attachments/assets/fa22ad54-3d9f-4793-96bc-d23041885104" />

3. Click **Connect**.

<img width="1917" height="1023" alt="Screenshot 2026-10-31 104633" src="https://github.com/user-attachments/assets/154a8e76-69d3-469f-bd9a-463e5f6d7258" />

4. Select **EC2 Instance Connect**.
5. Click **Connect**.

6. Execute the following command:

   ```bash
   echo "Hello AWS"
   ```

   **Output:**
   ```
   Hello AWS
   ```

<img width="1917" height="1026" alt="Screenshot 2026-10-31 104054" src="https://github.com/user-attachments/assets/3f4a9ab0-808e-4111-9f46-c4ef662b0c37" />

<img width="1917" height="1098" alt="Screenshot 2026-10-31 104245" src="https://github.com/user-attachments/assets/971f3e58-32cc-4f95-bf05-1a160d77b1d5" />


### Stopping the EC2 Instance
1. Open **EC2**.
2. Select **Instances**.
3. Select the running instance.
4. Click **Instance state**.
5. Click **Stop instance**.

   **Status flow:**
   ```
   Running → Stopping → Stopped
   ```
<img width="1917" height="1032" alt="Screenshot 2026-10-31 104311" src="https://github.com/user-attachments/assets/ee7e32e9-e113-4c7d-b0d0-eaa2f82bca32" />


### Logging Out of AWS
1. Click the profile icon in the upper-right corner.
2. Select **Sign out**.
3. 
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/67c0f1c2-94a9-444a-b996-fabc1910516a" />

---

## Result
The Amazon S3 bucket was created successfully, files were uploaded, an EC2 instance was launched, and the virtual machine was connected successfully.
