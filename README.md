# ROS2-Humble

## locale을 확인한다.
moses@moses-turtlebot:~$ localectl<br/>
&nbsp;System Locale: LANG=C.UTF-8<br/>
&nbsp;VC Keymap: (unset)<br/>
&nbsp;X11 Layout: kr<br/>
&nbsp;X11 Model: pc105<br/>
UTF-8을 지원하지 않으면 설치한다.

## 시스템에 ROS2 apt repository 추가
### Ubuntu Universe 무료 및 오픈소스 소프트웨어 저장소 추가 sudo add-apt-repository universe<br/>
확인 방법은 moses@moses-turtlebot:/etc/apt$ vi sources.list<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports mantic main restricted universe multiverse<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports/ mantic-updates main restricted universe multiverse<br/>
&nbsp;deb http://ports.ubuntu.com/ubuntu-ports/ mantic-security main restricted universe multiverse<br/>
vi 끝낼 때는 :q<br/>
### curl(Client Url)설치 sudo apt update && sudo apt install curl -y<br/>
### curl을 사용해서 ROS2 GPG Key 가져오기 sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg<br/>
### ROS2 GPG키 추가된 것을 확인한다.<br/>
moses@moses-turtlebot:~$ cd /<br/>
moses@moses-turtlebot:/$ cd usr/share/keyrings<br/>
moses@moses-turtlebot:/usr/share/keyrings$ ls<br/>
&nbsp;ros-archive-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-master-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-esm-infra.gpg<br/>
&nbsp;ubuntu-archive-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-anbox-cloud.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-fips.gpg<br/>
&nbsp;ubuntu-archive-removed-keys.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-cc-eal.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-realtime-kernel.gpg<br/>
&nbsp;ubuntu-cloudimage-keyring.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-cis.gpg &nbsp;&nbsp;&nbsp; ubuntu-pro-ros.gpg<br/>
&nbsp;ubuntu-cloudimage-removed-keys.gpg  ubuntu-pro-esm-apps.gpg<br/>
### 소스 목록에 repository 추가<br/>
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

### ROS2 패키지 설치<br/>
sudo apt update<br/>
sudo apt upgrade<br/>









