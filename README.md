# is15-project
## 5/25-30(13주) - 구현
5/25(금)-5/30(수) 강의 - 구현 

### 프로젝트 환경 구성(수정)  
#### 프로젝트 환경 설계 - draw.io 활용   
#### VirtualBox 설치
#### pfSense: NAT Network + Internal 
#### securityonion: NAT Network + Internal(promiscuous mode) -> 보류, 컴퓨터 자원 부족 
#### client1/server1(내부망): ubuntu-16.04.3-desktop, Internal, client1.internal
server1:
- centos7
- docker install
- wordpress install
#### client2/server2(외부망): ubuntu-16.04.3-desktop, NAT Network, server2.external

### 테스트
#### 동작 확인 - Test ICMP
#### 테스트 케이스 - 유해 사이트 접속, 사이트 주소를 입력할 것인가? 평판 DB를 사용할 것인가?
#### 테스트 케이스 - 개인정보 (파일) 유출, 개인정보 정규표현식 작성

### Centos - docker 설치
docker centos 설치
https://www.cyberciti.biz/faq/install-use-setup-docker-on-rhel7-centos7-linux/
# sudo yum remove docker docker-common docker-selinux docker-engine-selinux docker-engine docker-ce
# sudo yum install -y yum-utils device-mapper-persistent-data lvm2
# sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# sudo yum install docker-ce
# sudo systemctl enable docker.service
# sudo systemctl start docker.service
# ip a
#  ip a list docker0
# docker info
# docker run hello-world

docker-compose 설치
https://docs.docker.com/compose/install/#install-compose
# sudo curl -L https://github.com/docker/compose/releases/download/1.21.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
# sudo chmod +x /usr/local/bin/docker-compose
# docker-compose --version

root가 아닐때, user에서 sudo 사용하지 않으려면,
https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ docker run hello-world
$ sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
$ sudo chmod g+rwx "/home/$USER/.docker" -R


### 참고자료
- Kali Linux - https://docs.kali.org/installation/kali-linux-hard-disk-install
- Wordpress docker install - https://wpguide.usefulparadigm.com/posts/257
