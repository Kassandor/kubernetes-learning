**StatefulSet** — это объект Kubernetes для управления **stateful-приложениями**, которые требуют **стабильных идентификаторов Pod’ов, постоянного хранилища и упорядоченного старта/остановки**.

## Ключевые моменты
- Поддерживает **стабильные идентификаторы Pod’ов** (`pod-0`, `pod-1`…), даже при пересоздании.  
- Обеспечивает **постоянное хранилище** через `volumeClaimTemplates` для каждого Pod’а.  
- Поддерживает **упорядоченный запуск и остановку** Pod’ов (`orderedReady`, `orderedTermination`).  
- Используется для **баз данных, кэш-серверов и любых stateful-приложений**.  

## Связанные команды kubectl
```bash
kubectl get statefulsets
kubectl describe statefulset <name>
kubectl apply -f statefulset.yaml
kubectl delete statefulset <name>
kubectl scale statefulset <name> --replicas=<n>
kubectl rollout status statefulset <name>
kubectl rollout history statefulset <name>
kubectl rollout undo statefulset <name>
kubectl set image statefulset/<name> <container>=<image>
kubectl edit statefulset <name>
kubectl patch statefulset <name> --patch '<json>'