# Домашнее задание к занятию «Базовые объекты K8S»
1. Manifest файл: pod.yml

```
 
apiVersion : v1
kind: Pod
metadata:
  name: pod
spec:
  containers:
    - name : pod
      image: gcr.io/kubernetes-e2e-test-images/echoserver:2.2
      ports:
        - containerPort: 8080
```

   Pod запущен:

<img width="1292" height="77" alt="image" src="https://github.com/user-attachments/assets/20632d4f-d578-4167-93e4-aac796687ba3" />

Проброс порта:

<img width="638" height="67" alt="image" src="https://github.com/user-attachments/assets/08338ecf-c041-4daf-845c-070769752cb0" />

Вывод браузера:

<img width="883" height="707" alt="image" src="https://github.com/user-attachments/assets/28468170-629f-4ca3-ae3e-10dd1365f4fa" />

Manifest файл: netology-web.yml

```

apiVersion : v1
kind: Pod
metadata:
  name: netology-web
  labels:
    app: netology
spec:
  containers:
    - name : netology-web
      image: gcr.io/kubernetes-e2e-test-images/echoserver:2.2
      ports:
        - containerPort: 8080

---
apiVersion: v1
kind: Service
metadata:
  name: netology-svc
spec:
  ports:
  - port: 80
    targetPort: 8080
  selector:
    app: netology
        
```

pod и service запущены:

<img width="1352" height="176" alt="image" src="https://github.com/user-attachments/assets/6a00ad0f-0806-4a9f-a158-925b0ffa22ff" />

Проброс порта:

<img width="757" height="68" alt="image" src="https://github.com/user-attachments/assets/7c647ea9-7774-4da6-bf5c-9714d5f8f566" />

Вывод браузера:

<img width="897" height="760" alt="image" src="https://github.com/user-attachments/assets/c0fa2d41-8701-4583-abca-b671d56ebed8" />

