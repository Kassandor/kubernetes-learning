**Service** — это абстракция в Kubernetes, которая обеспечивает **постоянный сетевой доступ к группе Pod’ов**, скрывая их динамическую смену IP.  

**Ключевые моменты:**
- Service связывает Pod’ы через **селекторы (labels)**.
- Service обеспечивает стабильный **IP-адрес** и **DNS-имя** для Pod’ов.
- Типы Service:
  - **ClusterIP** — доступ внутри кластера (по умолчанию)
  - **NodePort** — открывает порт на Node для внешнего доступа
  - **LoadBalancer** — создаёт балансировщик нагрузки (для облачных провайдеров)
  - **ExternalName** — прокси для внешнего DNS-имени
- Service автоматически обновляет Endpoints при добавлении или удалении Pod’ов.

**Связанные команды kubectl:**
```bash
kubectl get services                   # список всех Service
kubectl describe service <name>        # подробная информация о Service
kubectl create service clusterip <name> --tcp=<port>:<targetPort>   # создать ClusterIP Service
kubectl delete service <name>          # удалить Service
kubectl expose deployment <name> --type=<type> --name=<service>    # создать Service для Deployment
kubectl port-forward service/<name> <local_port>:<service_port>    # проброс порта на локальный