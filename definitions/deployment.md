**Deployment** — это объект Kubernetes, который управляет созданием и обновлением Pod’ов, обеспечивая **жизненный цикл, масштабирование и откат версий**.

**Ключевые моменты:**
- Поддерживает **массштабирование Pod’ов** через параметр replicas.
- Обеспечивает **обновления Pod’ов без простоя** (RollingUpdate).
- Сохраняет **историю изменений** для отката (rollback).
- Автоматически заменяет упавшие Pod’ы.

**Связанные команды kubectl:**
```bash
kubectl get deployments
kubectl describe deployment <name>
kubectl apply -f deployment.yaml
kubectl create deployment <name> --image=<image>
kubectl delete deployment <name>
kubectl scale deployment <name> --replicas=<n>
kubectl rollout status deployment <name>
kubectl rollout history deployment <name>
kubectl rollout undo deployment <name>
kubectl set image deployment/<name> <container>=<image>
kubectl edit deployment <name>
kubectl patch deployment <name> --patch '<json>'