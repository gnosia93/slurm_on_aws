```
cat <<_EOF > playbook.yml
- name: get date from workers
  hosts: workers
  tasks:
   - name: ansible_date_time
     debug:
       var: ansible_date_time
_EOF
```

```
$ ansible-playbook playbook.yml -i ansible_hosts --user ubuntu --key-file ~/aws-kp-2.pem
```






## 레퍼런스 ##

* [Ansible을 활용한 NVIDIA-Driver 설치 과정 자동화](https://velog.io/@todd98/Ansible%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-NVIDIA-Driver-%EC%84%A4%EC%B9%98-%EA%B3%BC%EC%A0%95-%EC%9E%90%EB%8F%99%ED%99%94)