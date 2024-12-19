* [EFS 설정](https://my-studyroom.tistory.com/entry/AWS-%EC%8B%A4%EC%8A%B5-EFSElastic-File-System-%EC%82%AC%EC%9A%A9%ED%95%B4%EB%B3%B4%EA%B8%B0)
* https://registry.terraform.io/modules/terraform-aws-modules/efs/aws/latest


## EFS ##

* [Add EFS to an Amazon Linux 2 AWS EC2 Instance with Terraform](https://medium.com/@wblakecannon/add-efs-to-an-amazon-linux-2-aws-ec2-instance-with-terraform-bb073b6de7)


```
Ubuntu에서 sudo mount -t efs -o tls fs-d7ac42b7:/ /mnt/efs/fs1 명령어를 넣어주기 전에 다음과 같은 과정을 해야 한다.

(3단계에서 파일 시스템 추가 안 했을 경우임)

 

1.) sudo apt install git

2.) git clone https://github.com/aws/efs-utils

3.) sudo apt install -y make

4.) sudo apt install -y binutils

5.) cd efs-utils

6.) ./build-deb.sh

7.) sudo apt install ./build/amazon-efs-utils*deb
```
