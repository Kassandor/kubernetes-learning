# Kubernetes Deployment - Основные команды

| Команда | Описание | Пример |
|---------|----------|--------|
| `kubectl get deployments` | Показать все Deployment в текущем namespace | `kubectl get deployments` |
| `kubectl get deployment <name>` | Показать конкретный Deployment | `kubectl get deployment my-app` |
| `kubectl describe deployment <name>` | Подробная информация о Deployment | `kubectl describe deployment my-app` |
| `kubectl apply -f <file.yaml>` | Создать или обновить Deployment из YAML | `kubectl apply -f deployment.yaml` |
| `kubectl create deployment <name> --image=<image>` | Создать Deployment напрямую | `kubectl create deployment my-app --image=nginx` |
| `kubectl delete deployment <name>` | Удалить Deployment | `kubectl delete deployment my-app` |
| `kubectl scale deployment <name> --replicas=<n>` | Масштабировать количество Pod | `kubectl scale deployment my-app --replicas=3` |
| `kubectl rollout status deployment <name>` | Проверить статус обновления Deployment | `kubectl rollout status deployment my-app` |
| `kubectl rollout history deployment <name>` | Посмотреть историю обновлений Deployment | `kubectl rollout history deployment my-app` |
| `kubectl rollout undo deployment <name>` | Откат Deployment на предыдущую версию | `kubectl rollout undo deployment my-app` |
| `kubectl set image deployment/<name> <container>=<image>` | Обновить образ контейнера в Deployment | `kubectl set image deployment/my-app nginx=nginx:1.25` |
| `kubectl edit deployment <name>` | Редактировать Deployment в интерактивном редакторе | `kubectl edit deployment my-app` |
| `kubectl patch deployment <name> --patch '<json>'` | Частичное обновление Deployment | `kubectl patch deployment my-app --patch '{"spec":{"replicas":5}}'` |
| `kubectl get rs` | Показать ReplicaSet, созданные Deployment | `kubectl get rs` |
| `kubectl describe rs <name>` | Подробная информация о ReplicaSet | `kubectl describe rs my-app-xxxxx` |
| `kubectl get pods -l <label>` | Показать Pod'ы, созданные Deployment | `kubectl get pods -l app=my-app` |

---

### Полезные флаги

- `-n <namespace>` — указать namespace  
- `-o wide` — подробный вывод (IP, node)  
- `-o yaml` / `-o json` — вывести ресурс в формате YAML или JSON  
- `--all-namespaces` — показать Deployment во всех namespace  

