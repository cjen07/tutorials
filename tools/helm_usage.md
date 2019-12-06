1. 这里总结helm的常用命令
2. 官网的教程：https://v3.helm.sh/docs/
3. 添加官网charts仓库 `helm repo add stable https://kubernetes-charts.storage.googleapis.com/`
4. 搜索官方常用charts `helm search repo stable`
5. 更新charts仓库中列表 `helm repo update`
6. 例子：安装mysql charts `helm install stable/mysql --generate-name`
7. 查询当前released的charts `helm ls`
8. 查询当前部署的release `helm list`
9. 卸载一个release `helm uninstall <release-name>`
10. 查看一个release状态 `helm status <release-name>`
11. 获取帮助 `helm help` 或者 `helm <command> -h`
12. 安装本地chart `helm install my-chart chart/`
13. charts官网的教程是：https://v3.helm.sh/docs/topics/charts/ 
14. 请需要编写或想深入理解charts的开发人员详细阅读官方教程