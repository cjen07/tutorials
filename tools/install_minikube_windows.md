1. 下载并安装 docker desktop 网站：https://www.docker.com/products/docker-desktop （windows 10 需要是专业版或者是企业版才能安装docker）
2. 启动Hyper-V
    1. 使用windows键，搜索（英文系统是 `windows features on and off`, 中文系统是 `启用或关闭windows功能`）
    2. 勾选Hyper-V (启动这个功能需要一些时间，之后系统需要重启，另外如果想关闭这个功能也是可以通过类似的方式操作)
3. 安装windows的软件包管理器chocolatey
    1. 安装官网是：https://chocolatey.org/install
    2. 用administrative权限打开powershell (powershell应该是系统自带的)
    3. 在这个里面执行 `Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`
    4. 使用 `choco /?` 验证是否成功安装
4. 安装kubectl和minikube
    1. 用administrative权限打开powershell
    2. 执行 `choco install kubernetes-cli` 安装kubectl
    3. 当遇到这个提示的时候：`Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint):` 请输入 `A` 然后回车
    4. 执行 `kubectl version` 验证是否成功安装
    5. 执行 `choco install minikube` 安装minikube
    6. 确保docker desktop 已经打开并可以成功运行 `docker ps`
    7. 启动 minikube `minikube start --image-repository=registry.cn-hangzhou.aliyuncs.com/google_containers --extra-config=kubelet.authentication-token-webhook=true --memory='4000mb'`
    8. 验证是否启动成功 `kubectl get all --all-namespaces`
