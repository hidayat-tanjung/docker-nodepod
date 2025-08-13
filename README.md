# Static HTML Website on Kubernetes with Docker & NodePort

Repositori ini berisi contoh website statis sederhana yang dijalankan menggunakan Docker dan Kubernetes (NodePort).

## Struktur File
```sh
.
├── deployment.yaml       # Kubernetes Deployment configuration
├── service-nodeport.yaml # Kubernetes Service configuration
├── index.html           # Static HTML content
└── styles.css           # CSS styling
```

## Cara Build dan Deploy

### 1. Build Docker Image

```sh
docker build -t static-html-nginx .
```

### 2. Jalankan di Kubernetes (Minikube)

```sh
kubectl apply -f deployment.yaml
kubectl apply -f service-nodeport.yaml
```

### 3. Akses Website

Cari port NodePort yang digunakan, lalu akses melalui browser:

```
minikube service static-html-service
```

## Deskripsi

Website ini hanya berisi halaman HTML statis yang di-*serve* oleh Nginx. Cocok untuk belajar dasar Docker dan Kubernetes.

---

**Penulis:**  
Website statis sederhana untuk demonstrasi Docker
