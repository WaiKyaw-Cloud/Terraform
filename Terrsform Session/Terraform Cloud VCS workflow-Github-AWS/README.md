# Architecture
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/0cccb858-e706-48bc-93fe-64cad1ba1093)

## Create Free Terraform Cloud Account ([Page](https://app.terraform.io/app))
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/0d90695b-89d7-4df3-9a16-07d5b9b2077d)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/b2f02308-b0a3-4b23-ad1e-6a37ad5ad94d)

## Generate a Terraform Cloud user token and connect to TFC Cloud
```jsx
vagrant@HelloCloudDevBox:~$ terraform login
Terraform will request an API token for app.terraform.io using your browser.

If login is successful, Terraform will store the token in plain text in
the following file for use by subsequent commands:
    /home/vagrant/.terraform.d/credentials.tfrc.json

Do you want to proceed?
  Only 'yes' will be accepted to confirm.

  Enter a value: yes

---------------------------------------------------------------------------------

Open the following URL to access the tokens page for app.terraform.io:
    https://app.terraform.io/app/settings/tokens?source=terraform-login

---------------------------------------------------------------------------------

Generate a token using your browser, and copy-paste it into this prompt.

Terraform will store the token in plain text in the following file
for use by subsequent commands:
    /home/vagrant/.terraform.d/credentials.tfrc.json

Token for app.terraform.io:
  Enter a value:
```

- Browse  https://app.terraform.io/app/settings/tokens?source=terraform-login

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/ffdc1336-bd39-45f0-baf0-c628afa87d3e)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/d5e13634-9de6-4a44-b11e-d6bf812c1c3d)

- Create the tfc user token and paste it.

```jsx
vagrant@HelloCloudDevBox:~$ terraform login
Terraform will request an API token for app.terraform.io using your browser.

If login is successful, Terraform will store the token in plain text in
the following file for use by subsequent commands:
    /home/vagrant/.terraform.d/credentials.tfrc.json

Do you want to proceed?
  Only 'yes' will be accepted to confirm.

  Enter a value: yes

---------------------------------------------------------------------------------

Open the following URL to access the tokens page for app.terraform.io:
    https://app.terraform.io/app/settings/tokens?source=terraform-login

---------------------------------------------------------------------------------

Generate a token using your browser, and copy-paste it into this prompt.

Terraform will store the token in plain text in the following file
for use by subsequent commands:
    /home/vagrant/.terraform.d/credentials.tfrc.json

Token for app.terraform.io:
  Enter a value: 

Retrieved token for user Terraform_Cop

---------------------------------------------------------------------------------

                                          -                                
                                          -----                           -
                                          ---------                      --
                                          ---------  -                -----
                                           ---------  ------        -------
                                             -------  ---------  ----------
                                                ----  ---------- ----------
                                                  --  ---------- ----------
   Welcome to Terraform Cloud!                     -  ---------- -------
                                                      ---  ----- ---
   Documentation: terraform.io/docs/cloud             --------   -
                                                      ----------
                                                      ----------
                                                       ---------
                                                           -----
                                                               -

   New to TFC? Follow these steps to instantly apply an example configuration:

   $ git clone https://github.com/hashicorp/tfc-getting-started.git
   $ cd tfc-getting-started
   $ scripts/setup.sh

vagrant@HelloCloudDevBox:~$
```
## Generate a Personal Access Token and connect to GitHub
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/34c5fc21-4cd7-4b16-8d13-2a90f9be6dd0)

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/c182ec9b-7177-434c-8ba7-dc5fd537e5a5)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/a51f4ae0-9409-49b7-b3d2-1a39d3f0412a)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/64f3e90c-c0ed-40c5-988b-41a349931635)
- Create the token ( choose the scopes of token )
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/61b846e8-c989-418d-ad0d-4a6c7bd48de5)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/7f8cafe0-9669-4172-854b-835ed79d0f09)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/62bf4166-98f5-4a84-a4b7-a5ea58fde74d)

```jsx
vagrant@HelloCloudDevBox:~$ gh auth login --with-token <<< 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
vagrant@HelloCloudDevBox:~$ gh auth status
github.com
  ✓ Logged in to github.com account cloudgitcollab (/home/vagrant/.config/gh/hosts.yml)
  - Active account: true
  - Git operations protocol: https
  - Token: ghp_************************************
  - Token scopes: 'delete_repo', 'read:org', 'repo', 'user', 'workflow'
```

## [Github Client installation on Linux](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)

```jsx
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

```jsx
vagrant@HelloCloudDevBox:~$  git version
git version 2.34.1
```

## Create the tfc Organization

- Before connecting, it is necessary to create the organization in our Terraform Cloud.
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/9978ef86-f10e-4904-979f-ba0fd07f18f3)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/f2841f94-d31d-4d9f-bad0-fa01a84beadc)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/8a226911-05e2-44f3-bd3f-bb5dbc7ba5d2)
## Connect the organization-level TFC Cloud VCS provider and GitHub OAuth
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/65e65b18-1f9c-407e-8887-579456e13037)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/e1692e3b-a7fe-4f93-a0c3-0f5670843162)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/f84472b7-d073-4d58-9dcc-507eaca12a64)

- Go Github`Settings` >> `Developer Settings` >> `OAuth Apps`
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/bf08f157-d79b-4c75-b258-e0dcce0c42bb)
- And afterward, copy the `Application name`, `Homepage URL`, and `Authorization callback URL` from Terraform Cloud, then paste them into GitHub OAuth.
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/89248025-6cf1-4b24-ae68-57029b715c99)
- In a similar fashion, copy the `Client ID` and `Client Secret` from GitHub and paste them into Terraform Cloud vcs provider
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/b32da806-020a-40ce-9298-42e63f00bdb5)
- Finally, the connection is established
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/e0d10795-9b8d-45b8-9463-27d14c88e163)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/bab2ae47-ee7b-4f7e-b16d-05c99b5e4a6f)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/5a9ee8d8-05b9-4dfc-bde9-5350019b53ad)

## Create Workspaces ( Version Control Workflow )
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/e8283296-c241-4eb8-a66c-ee49d724395c)
- Create `CLI-Driven Workflow` initially; later, it will be changed to a `Version Control Workflow`
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/20169f11-5d35-466f-a8d6-2642a03d4fb9)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/6aac99d3-8621-4527-90e0-68e8f292fd18)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/934e721f-9cdd-4325-a11a-202212774197)

## Create the repository and push the code to GitHub

```jsx
git clone https://github.com/hashicorp/hashicat-aws.git hashicat-aws-bca-github-testing
cd hashicat-aws-bca-github-testing
git remote rm origin    # remove the origin 
gh repo create hashicat-tfc-github-aws-testing --private --source=. --remote=upstream --push
```

- Gitclone , remote rm and git push
    
    ```jsx
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow$ git clone https://github.com/hashicorp/hashicat-aws.git tfc-vcs-github-aws-testing
    Cloning into 'tfc-vcs-github-aws-testing'...
    remote: Enumerating objects: 520, done.
    remote: Counting objects: 100% (38/38), done.
    remote: Compressing objects: 100% (21/21), done.
    remote: Total 520 (delta 20), reused 30 (delta 15), pack-reused 482
    Receiving objects: 100% (520/520), 342.99 KiB | 1.54 MiB/s, done.
    Resolving deltas: 100% (289/289), done.
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow$ ls
    README.md  tfc-vcs-github-aws-testing
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow$ cd tfc-vcs-github-aws-testing/
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ ls
    CODEOWNERS  exercises  files  LICENSE  main.tf  outputs.tf  README.md  terraform.tfvars.example  variables.tf
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ git remote
    origin
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ git remote -v
    origin  https://github.com/hashicorp/hashicat-aws.git (fetch)
    origin  https://github.com/hashicorp/hashicat-aws.git (push)
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ git remote rm origin 
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ git remote -v
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ git remote
    vagrant@HelloCloudDevBox:~/Hashicorp-cp/Terraformcorp/TerraformCloud-vcs_workflow/tfc-vcs-github-aws-testing$ gh repo create hashicat-tfc-github-aws-testing --private --source=. --remote=upstream --push
    ✓ Created repository cloudgitcollab/hashicat-tfc-github-aws-testing on GitHub
    ✓ Added remote https://github.com/cloudgitcollab/hashicat-tfc-github-aws-testing.git
    Enumerating objects: 463, done.
    Counting objects: 100% (463/463), done.
    Delta compression using up to 4 threads
    Compressing objects: 100% (195/195), done.
    Writing objects: 100% (463/463), 328.04 KiB | 109.35 MiB/s, done.
    Total 463 (delta 257), reused 463 (delta 257), pack-reused 0
    remote: Resolving deltas: 100% (257/257), done.
    To https://github.com/cloudgitcollab/hashicat-tfc-github-aws-testing.git
     * [new branch]      HEAD -> master
    Branch 'master' set up to track remote branch 'master' from 'upstream'.
    ✓ Pushed commits to https://github.com/cloudgitcollab/hashicat-tfc-github-aws-testing.git
    ```

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/10d41caf-9f16-4aaf-b33b-6c38c3b3d73a)


## Choose the repository at the TFC workspace

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/96d84b98-fa8e-4e27-a4b4-a52585e77dc2)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/17246f24-b2fc-47f7-949c-0ce332896a61)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/13020e19-9553-4893-a105-6f2905155155)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/c4914399-abaf-47bf-926f-e5d66f3b22e4)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/60313bab-6449-4e70-bbe2-7fc0c2c37c08)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/cb19e6ad-9df9-4c11-8ccb-a8cf822beffd)

## Generate IAM/user `AWS_ACCESS_KEY_ID`nd`AWS_SECRET_ACCESS_KEY`

```
AWS_ACCESS_KEY_ID :: xxxxx
AWS_SECRET_ACCESS_KEY :: xxxxx
```
- Create user , attach permission and access keys.
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/d40848a0-fdd5-47d4-8ea8-9dadbb0a6953)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/ef731244-de2f-414d-8ce9-a445c8be6507)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/f8791aae-a9c9-4e1b-bc74-5f77e759fea5)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/209eff32-143d-44a7-a76d-219531da504c)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/8790dcf9-204e-4790-8cf2-74b2e52eca50)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/b57d3f19-240d-4e6b-8397-2f651274b50c)

## Add the AWS access key ID and secret access key to TFC workspaces as environment variables

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/02b1e273-d97f-4ed8-89ab-737b23d24599)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/4923f8ca-413b-4448-8d88-5c1c9443ac02)

- **`Sensitive variables` ::** variables are never shown in the UI or API, and can’t be edited. They may appear in Terraform logs if your configuration is designed to output them. To change a sensitive variable, delete and replace it.

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/ab20d02a-30f4-4796-9406-9b783cd8e1f8)
## Initiate a new run at TFC workspaces
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/2fec9a82-4c4d-440b-b1cc-8011a9a45ac9)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/ba53d6f7-1e6f-4333-93ff-1f5700f51f59)
- Showing **`Error: No value for required variable`** **`variable "prefix"**`
- add the `terraform variable` and run again

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/7176c737-450f-455e-8e1f-49aadfff4166)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/8f04bdef-ef98-4cce-9691-a1d5b3647419)
- Check the status of resource creation in AWS
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/1fec831e-40a9-4a9d-abd0-085f3e4c8e62)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/11a1f4af-f253-454a-ba39-fbbb108e9119)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/daa8d4f5-a962-4f83-8307-294b311f7ef7)
![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/edd2cf38-4ea0-476d-999a-67b8f446b894)

- It has been created successfully. Let's check the status of the Meow web.

![image](https://github.com/WaiKyaw-Cloud/Terraform/assets/157877132/aa84d9c3-5e51-40f4-abda-78b1e4d8e8d9)










