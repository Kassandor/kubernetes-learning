# Kubernetes Pod - Основные команды

| Команда | Описание | Пример |
|---------|----------|--------|
| `kubectl get pods` | Показать все Pod в текущем namespace | `kubectl get pods` |
| `kubectl get pod <name>` | Показать конкретный Pod | `kubectl get pod my-nginx-pod` |
| `kubectl describe pod <name>` | Подробная информация о Pod | `kubectl describe pod my-nginx-pod` |
| `kubectl apply -f <file.yaml>` | Создать или обновить Pod из YAML | `kubectl apply -f pod.yaml` |
| `kubectl create pod <name> --image=<image>` | Создать Pod напрямую (редко используют) | `kubectl run my-nginx-pod --image=nginx` |
| `kubectl delete pod <name>` | Удалить Pod | `kubectl delete pod my-nginx-pod` |
| `kubectl logs <pod>` | Показать логи контейнера Pod | `kubectl logs my-nginx-pod` |
| `kubectl logs -f <pod>` | Подписка на логи (stream) | `kubectl logs -f my-nginx-pod` |
| `kubectl logs <pod> -c <container>` | Логи конкретного контейнера внутри Pod | `kubectl logs my-pod -c nginx` |
| `kubectl exec -it <pod> -- <command>` | Выполнить команду внутри контейнера | `kubectl exec -it my-nginx-pod -- sh` |
| `kubectl port-forward <pod> <local_port>:<pod_port>` | Проброс порта из Pod на локальный | `kubectl port-forward my-nginx-pod 8080:80` |
| `kubectl cp <pod>:<path> <local_path>` | Скопировать файл из Pod на локальный | `kubectl cp my-pod:/app/log.txt ./log.txt` |
| `kubectl get pods -o wide` | Подробный вывод Pod (IP, Node, Status) | `kubectl get pods -o wide` |
| `kubectl get pods -n <namespace>` | Показать Pod в указанном namespace | `kubectl get pods -n kube-system` |
| `kubectl top pod` | Показать использование ресурсов Pod | `kubectl top pod my-nginx-pod` |
| `kubectl get events` | Показать события, связанные с Pod | `kubectl get events` |
| `kubectl wait --for=condition=Ready pod/<name>` | Дождаться, пока Pod будет Ready | `kubectl wait --for=condition=Ready pod/my-nginx-pod` |
| `kubectl edit pod <name>` | Редактировать Pod в интерактивном редакторе | `kubectl edit pod my-nginx-pod` |
| `kubectl patch pod <name> --patch '<json>'` | Частичное обновление Pod | `kubectl patch pod my-pod --patch '{"metadata":{"labels":{"env":"prod"}}}'` |

---

### Полезные флаги

- `-n <namespace>` — указать namespace  
- `-o yaml` / `-o json` — вывести Pod в формате YAML/JSON  
- `--all-namespaces` — показать Pod во всех namespace  
- `-l <label>` — фильтр по лейблам  
  - Пример: `kubectl get pods -l app=my-app`  

