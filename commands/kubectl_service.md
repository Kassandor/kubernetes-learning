# Kubernetes Service - Основные команды

| Команда | Описание | Пример |
|---------|----------|--------|
| `kubectl get services` | Показать все Service в текущем namespace | `kubectl get services` |
| `kubectl get service <name>` | Показать конкретный Service | `kubectl get service my-service` |
| `kubectl describe service <name>` | Подробная информация о Service | `kubectl describe service my-service` |
| `kubectl apply -f <file.yaml>` | Создать или обновить Service из YAML | `kubectl apply -f service.yaml` |
| `kubectl create service clusterip <name> --tcp=<port>:<targetPort>` | Создать Service типа ClusterIP | `kubectl create service clusterip my-service --tcp=80:80` |
| `kubectl create service nodeport <name> --tcp=<port>:<targetPort>` | Создать Service типа NodePort | `kubectl create service nodeport my-service --tcp=80:80` |
| `kubectl create service loadbalancer <name> --tcp=<port>:<targetPort>` | Создать Service типа LoadBalancer | `kubectl create service loadbalancer my-service --tcp=80:80` |
| `kubectl delete service <name>` | Удалить Service | `kubectl delete service my-service` |
| `kubectl get endpoints` | Показать Endpoints, к которым привязан Service | `kubectl get endpoints my-service` |
| `kubectl get svc -o wide` | Подробный вывод Service | `kubectl get svc -o wide` |
| `kubectl expose deployment <deployment> --type=<type> --name=<name>` | Создать Service для Deployment | `kubectl expose deployment my-app --type=ClusterIP --name=my-service` |
| `kubectl port-forward service/<name> <local_port>:<service_port>` | Проброс порта из Service на локальный | `kubectl port-forward service/my-service 8080:80` |
| `kubectl edit service <name>` | Редактировать Service в интерактивном редакторе | `kubectl edit service my-service` |
| `kubectl patch service <name> --patch '<json>'` | Частичное обновление Service | `kubectl patch service my-service --patch '{"spec":{"type":"NodePort"}}'` |
| `kubectl get services -n <namespace>` | Показать Service в указанном namespace | `kubectl get services -n kube-system` |
| `kubectl get all` | Показать все ресурсы включая Service | `kubectl get all` |

---

### Полезные флаги

- `-n <namespace>` — указать namespace  
- `-o yaml` / `-o json` — вывести ресурс в формате YAML/JSON  
- `--all-namespaces` — показать Service во всех namespace  
- `-l <label>` — фильтр по лейблам  
  - Пример: `kubectl get svc -l app=my-app`  

