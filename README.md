# Static HTML Website on Kubernetes with Docker & NodePort

Repositori ini berisi contoh website statis sederhana yang dijalankan menggunakan Docker dan Kubernetes (NodePort).

## Struktur File

- [`index.html`](c:/Users/marli/Desktop/docker-nodepod/index.html): Halaman utama website statis.
- [`styles.css`](c:/Users/marli/Desktop/docker-nodepod/styles.css): File CSS untuk styling halaman.
- [`Dockerfile`](c:/Users/marli/Desktop/docker-nodepod/Dockerfile): Dockerfile untuk membangun image berbasis Nginx yang menyajikan file HTML dan CSS.
- [`deployment.yaml`](c:/Users/marli/Desktop/docker-nodepod/deployment.yaml): Manifest Kubernetes untuk deployment aplikasi.
- [`service-nodeport.yaml`](c:/Users/marli/Desktop/docker-nodepod/service-nodeport.yaml): Manifest Kubernetes untuk service dengan tipe NodePort.
- `minikube-linux-amd64`: Binary Minikube untuk menjalankan Kubernetes secara lokal.

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
