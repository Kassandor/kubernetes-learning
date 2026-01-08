# Изучение Kubernetes на примере Minikube
В качестве проекта был взят учебный проект **newildberries**.

---

## Использовались:
### Инфраструктура
- **Bare metal гипервизор:** Hyper-V
- **Root partition:** Windows
- **Child partition 1:** WSL2 (Docker + Docker Desktop)
- **Child partition 2:** VM (Hyper-V VM)

---

## Первая итерация
Кластер был создан на базе Minikube с использованием Docker:
```bash
minikube start --driver=docker
```

* Все поды запускались внутри Docker на WSL2.
* Удобно для локальной разработки и быстрого тестирования образов.

---

## Вторая итерация
Кластер был создан на базе виртуальной машины через Hyper-V:

```bash
minikube start --driver=hyperv --container-runtime=containerd
```

* Позволяет тестировать Kubernetes ближе к продакшн-среде с выделенной VM.