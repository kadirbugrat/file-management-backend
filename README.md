# File Management App

**Full-stack web uygulaması** – Spring Boot (Java) + React (TypeScript) + Firebase

## Özellikler

- **Kimlik Doğrulama**
    - Firebase Authentication (email/şifre)
    - JWT ile korunan backend endpoint’leri

- **Dosya Yönetimi**
    - PDF, PNG, JPG dosya yükleme
    - Yüklü dosyaları listeleme
    - Dosya silme
    - Dosyaların Firebase Storage’da saklanması

## Teknolojiler

- **Backend**
    - Java 17, Spring Boot 3
    - Spring Security (OAuth2 Resource Server & JWT)
    - Firebase Admin SDK (Storage)
    - Maven

- **Frontend**
    - React + TypeScript
    - Axios
    - Material-UI (v5)

## Kurulum

1. **Backend**
   ```bash
   -cd file-management-backend
   -./mvnw clean package

   -src/main/resources/application.properties içindeki firebase.cred.path ve firebase.bucket ayarlarını kendi servis hesabı JSON ve bucket adınızla güncelleyin.
   -VITE_FIREBASE_API_KEY benzeri değerler .env dosyanıza girilecek (frontend kısmı için)
   -Uygulamayı 8081 portunda çalıştırmak için: 
   ```bash
   ./mvnw spring-boot:run

2. **Frontend**
   -cd file-management-frontend
   -npm install
   -npm run dev

   .env içinde:
   VITE_FIREBASE_API_KEY=your_web_api_key
   VITE_API_BASE_URL=http://localhost:8081


**KULLANIM**
1. Tarayıcıyı açın: http://localhost:5173

2. E-posta & parola ile giriş yapın.

3. “Dosya Yükle” bölümünden bir dosya seçip “Yükle” butonuna tıklayın.

4. Başarıyla yüklendiğinde üstte indirme linki, altta liste görünür.

5. Listeden “Sil” ile dosyayı kaldırabilirsiniz.

6. Çıkış yapmak için sağ üstteki “Çıkış Yap” butonunu kullanın.


**DİZİN YAPISI**
file-management-backend/
├─ src/
│  ├─ main/
│  │  ├─ java/...  (Spring kodları)
│  │  └─ resources/ (application.properties, firebase serv.acc)
└─ pom.xml

file-management-frontend/
├─ src/
│  ├─ api/         (axios client)
│  ├─ components/  (Login, FileUploader, FileList)
│  ├─ App.tsx
│  └─ index.tsx
└─ package.json
