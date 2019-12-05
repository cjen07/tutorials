0. 预备：安装好 docker 教程： https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04
1. 官网教程是：https://kubernetes.io/docs/tasks/tools/install-minikube/
2. 在命令行执行 `grep -E --color 'vmx|svm' /proc/cpuinfo` 确认这个结果不是空的（也就是输出非空）
3. 安装 kubectl 官网教程是: https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux
    1. `curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl` 执行这个命令下载kubectl
    2. `chmod +x ./kubectl` 执行这个命令让kubectl可执行
    3. `sudo mv ./kubectl /usr/local/bin/kubectl` 将kubectl程序放到系统程序的目录下
    4. `kubectl version` 验证是否安装成功
4. 安装 kvm
    1. 教程链接是：https://linuxconfig.org/install-and-set-up-kvm-on-ubuntu-18-04-bionic-beaver-linux
    2. `sudo apt install qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils virt-manager` 执行这个命令安装kvm相关的package
    3. 按照教程里的方式设置网络，注意请把 `ens3` 替换成你的网络接口名称，可以使用 `ip a` 这个命令查看你们网络接口名称 （可能不是必要的）
    4. 按照教程里的方式设置用户权限，注意请把 `username`替换成你当前登录的用户名 （可能不是必要的）
    5. 重启系统
    6. 可以使用教程中的方式通过安装一个debian系统验证kvm是否成功安装
5. 安装 minikube
    1. 下载minikube `curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube`
    2. 安装 `sudo mkdir -p /usr/local/bin/` `sudo install minikube /usr/local/bin/`
6. 启动 minikube `minikube start --image-repository=registry.cn-hangzhou.aliyuncs.com/google_containers --extra-config=kubelet.authentication-token-webhook=true --memory='4000mb'`
7. 验证是否启动成功 `kubectl get all --all-namespaces`