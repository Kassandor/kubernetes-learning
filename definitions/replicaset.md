**ReplicaSet** — объект Kubernetes, который гарантирует, что заданное количество идентичных Pod’ов (**replicas**) работает в любой момент времени.

**Ключевые моменты:**
- Обеспечивает **поддержание заданного числа Pod’ов**.
- Использует **селекторы (labels)** для управления Pod’ами.
- Обычно создаётся **Deployment**, поэтому редко создаётся вручную.
- Следит за **автоматическим созданием и удалением Pod’ов** при изменении количества реплик.

**Связанные команды kubectl:**
```bash
kubectl get rs
kubectl describe rs <name>
kubectl delete rs <name>
kubectl scale rs <name> --replicas=<n>
kubectl get pods -l <label>     # посмотреть Pod’ы, управляемые ReplicaSet