1. 这里主要总结一些比较常用的kubectl命令
2. 查看所有命名空间的信息 `kubectl get all --all-namespaces`
3. 查看一个pod的日志 `kubectl logs pod/<pod-name>`
4. 查看一个pod的配置信息和事件 `kubectl describe pod <pod-name>`
5. 启动一个测试pod `kubectl run -i --tty --rm debug --image=busybox --restart=Never -- sh`
6. 安装一个yml资源 `kubectl apply -f <path-to-yml-file>`
7. 查看storageclass资源 `kubectl get storageclass`
8. 查看pv（persistent volume）资源 `kubectl get pv`
9. 查看pvc（persistent volume claim）资源 `kubectl get pvc`
10. 删除一个pod `kubectl delete pod <pod-name>`