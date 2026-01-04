**Pod** — это минимальная логическая единица Kubernetes, которая запускает один или несколько контейнеров, имеющих общий сетевой адрес (IP), порты и volume.

**Ключевые моменты:**
- Все контейнеры внутри Pod делят **один network namespace** и **одни volume**.
- Pod управляется **kubelet** на Node.
- Pod может содержать **initContainers** (запускаются до основных контейнеров) и **sidecar containers** (дополнительные сервисы, например логирование или прокси).
- Pod **не масштабируется напрямую**; для масштабирования используют **Deployment** или **ReplicaSet**.
- **Существует «pause container»**, создаваемый Kubernetes, который держит namespaces для всех контейнеров Pod.

**Связанные команды kubectl:**
```bash
kubectl get pods                   # список всех Pod в namespace
kubectl describe pod <name>        # подробная информация о Pod
kubectl logs <pod>                 # логи контейнера
kubectl exec -it <pod> -- <cmd>    # выполнить команду в контейнере Pod
kubectl delete pod <name>          # удалить Pod