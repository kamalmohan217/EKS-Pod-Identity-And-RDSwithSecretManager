# EKS-Pod-Identity-And-RDSwithSecretManager-Aws
![image](https://github.com/user-attachments/assets/6b9159c5-0ef4-4769-bbf9-4a3621817e6e)

In the first part of this project, I had demonstrated the PostgreSQL RDS and its credentials was stored in AWS Secrets Manager. First, I logged-in with the initial Users Credentials which was stored in the Secrets Manager. Then for demonstration purpose I rotated the Secrets Manager secret (password). However, you should rotate it as per your organisation. After Rotation the Password for RDS had been changed and user was able to logged-in using the new credentials as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/dad79db7-5b56-4aef-a746-9a6fefafe739)

In the second part of this project, I accessed the S3 bucket from the kubernetes Pod present in the EKS Cluster using the Pod Identity. To achieve this using Pod Identity, you should install EKS Pod Identity add on and attach the proper IAM Role with specific namespace and service account in which the pod was existed to the EKS Cluster. For this project I had attached an IAM Role to provide the privilege of Full S3 Bucket and namespace dexter and service account dexter-sa. I had not used the default service account of the namespace (whenever you create a namespace a service account with the same name will also be created).   

![image](https://github.com/user-attachments/assets/07336cb5-100e-4e3f-8118-6bcba351abc4)

In the third and last part of this project I used Secret Store CSI driver to Access Secrets Manager secret from Kubernetes Pod of the EKS Cluster. OIDC (Open ID Connect) and Federated Identity had been used to access the AWS Secrets Manager secret from Kubernetes Pod of EKS Cluster. 
OIDC is a protocol using which a User can logged-in into one Application and can access other applications. Federated Identity is method by which user can access multiple Applications using single set of credentials.

```
Reference:- https://github.com/mihirbhatt4687/lambda-secret-rotate.git
```


