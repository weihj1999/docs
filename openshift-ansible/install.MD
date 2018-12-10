# OpenShift Ansible
Huawei provide technical support to install OpenShift on Open Telekom Cloud. You may refer more detail in the bellow repository:<br>
https://github.com/huaweicloud/openshift-ansible
<br>

## Usage
In order to setup openshift cluster by ansible, you'll need to finish the following steps:

## Prerequisite
>* Host Operation System: CentOS 7.3+
>* Host Operation System User: root
>* Available EIP Quatas on Cloud: 4+
>* Available VPC Quatas on Cloud: 1+
>* Available Security Group Quatas on Cloud: 6

## Installation
1. pull openshift-ansible github repository.
```bash
curl https://raw.githubusercontent.com/huaweicloud/openshift-ansible/master/hack/pull-repos.sh | bash
```
2. set cloud credentials.
```bash
cd openshift-ansible
vi keystonerc

  # set your own ENV in the file
  export OS_AUTH_URL=https://iam.cn-north-1.myhwclouds.com
  export OS_USERNAME=user
  export OS_PASSWORD=password
  export OS_IDENTITY_API_VERSION=3
  export OS_DOMAIN_NAME=domain
  export OS_USER_DOMAIN_NAME=domain
  export OS_PROJECT_DOMAIN_NAME=domain
  export OS_TENANT_NAME=tenant
  export OS_REGION_NAME=cn-north-1
  export OS_AVAILABILITY_ZONE=cn-north-1a
 ```
3. Create a new keypair named openshift in cloud web console and put the private key file openshift.pem into openshift-ansible folder.

4. Install openshift cluster by the following command which can be executed repeatly until success.
```bash
. hack/install.sh
```
5. If you need to uninsall openshift cluster, you can run the following command.
```bash
. hack/uninstall.sh
```
