# Static HTML Website on Kubernetes with Docker & NodePort

Repositori ini berisi contoh website statis sederhana yang dijalankan menggunakan Docker dan Kubernetes (NodePort).

## Struktur File
```sh
custom-html/
├── index.html             # Halaman utama website
├── styles.css             # Style CSS
├── Dockerfile             # Script build Docker image
├── deployment.yaml        # YAML untuk deploy di Kubernetes (server berbeda)
└── service-nodeport.yaml  
```

## Cara Build dan Deploy

### 1.  Build dan Push Docker Image dari Server Docker

```sh
# Build image (ganti "hidayat30" dengan username Docker Hub kamu)
docker build -t hidayat30/custom-html:latest .
 
# Login ke Docker Hub (jika belum)
docker login -u userKamu
 
# Push image ke Docker Hub
docker push hidayat30/custom-html:latest
```

### 2. Deploy ke Kubernetes

```sh
kubectl apply -f deployment.yaml
kubectl apply -f service-nodeport.yaml
```

### 3. Akses Website

Cari port NodePort yang digunakan, lalu akses melalui browser:

```
kubectl get svc custom-html-svc
atau
minikube service custom-html-svc --url
```

## Deskripsi

Website ini hanya berisi halaman HTML statis yang di-*serve* oleh Nginx. Cocok untuk belajar dasar Docker dan Kubernetes.

---

**Penulis:**  
Website statis sederhana untuk demonstrasi Docker
