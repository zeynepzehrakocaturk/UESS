# Proje 3 — Ders Programı Planlama

Basit bir Flask tabanlı web uygulaması. Ders, öğrenci, öğretim üyesi ve derslik verilerini kullanarak planlama ve raporlama işlevleri sunar.

## Hızlı Başlangıç

- Gereksinimler: Python 3.8+ ve `pip`.
- Sanal ortam oluşturup bağımlılıkları yükleyin:

```bash
python -m venv venv
# PowerShell (Windows)
venv\\Scripts\\Activate.ps1
# veya CMD (Windows)
venv\\Scripts\\activate.bat
# Unix/macOS
source venv/bin/activate

pip install -r requirements.txt
```

Uygulamayı çalıştırmak için:

```bash
python app.py
# veya Windows için hazır betik
run.bat
# Unix için
./run.sh
```

Tarayıcıda açın: http://127.0.0.1:5000

## Yapı ve Önemli Dosyalar

- [app.py](app.py) — Flask uygulama giriş noktası
- [config.py](config.py) — Uygulama yapılandırması
- [requirements.txt](requirements.txt) — Python bağımlılıkları
- [models/](models/) — Veritabanı modelleri ve ORM sınıfları
- [routes/](routes/) — Flask rota tanımları (admin, auth, ders, vb.)
- [templates/](templates/) — HTML şablonları
- [static/](static/) — CSS, JS, örnek CSV dosyası
- [algorithms/planlama_algoritmasi.py](algorithms/planlama_algoritmasi.py) — Planlama mantığı

## Veritabanı
Projede model tanımları `models/` altında bulunmaktadır. Eğer proje SQLite gibi dosya tabanlı bir DB kullanıyorsa, config ayarlarına göre veritabanı dosyası oluşturulur. Mevcut veritabanını görüntülemek için `veritabani_goruntule.py` kullanılabilir.

## Kullanım
- Yönetici paneli, sınav programlama ve raporlar için uygulamanın sağladığı formları kullanın.
- Toplu öğrenci/ders yükleme için ilgili şablonları kullanabilirsiniz (ör. `templates/ders/toplu_yukle.html`).

## Katkıda Bulunma
1. Fork yapın
2. Yeni bir branch oluşturun (`feature/isim`)
3. Değişikliklerinizi commit edin
4. Pull request açın

## Lisans
MIT

---
İsterseniz README'yi projenin gereksinimlerine göre genişleteyim (ör. örnek `config.py` ayarları, ortam değişkenleri, ayrıntılı DB kurulum adımları).

## Konfigürasyon ve Ortam Değişkenleri
Uygulama yapılandırması `config.py` içinde veya ortam değişkenleriyle sağlanabilir. Yaygın kullanılan değişkenler:

- `FLASK_ENV`: `development` veya `production`
- `SECRET_KEY`: Flask oturum/CSRF için gizli anahtar
- `DATABASE_URL`: SQLAlchemy için veritabanı bağlantı URI'si (örn. `sqlite:///data.db`)

Windows PowerShell'de örnek ortam değişkeni ayarlama:

```powershell
$env:DATABASE_URL = "sqlite:///data.db"
$env:FLASK_ENV = "development"
$env:SECRET_KEY = "gizli"
```

Unix/macOS:

```bash
export DATABASE_URL="sqlite:///data.db"
export FLASK_ENV=development
export SECRET_KEY=gizli
```

## Çalıştırma Örnekleri
1. Sanal ortamı aktif hale getirin ve bağımlılıkları yükleyin.
2. Ortam değişkenlerini ayarlayın (yukarıya bakın).
3. Uygulamayı başlatın:

```bash
python app.py
```

Eğer projenizde bir veritabanı başlatma script'i yoksa, bir SQLite dosyası kullanıyorsanız uygulama ilk çalıştırmada dosyayı oluşturabilir; aksi halde proje README veya `models/` içindeki docstring'lere bakınız.

## Örnek Kullanım Senaryosu
- Öğrenci verilerini CSV ile toplu yüklemek için `templates/ogrenci/yukle.html` sayfasını kullanın.
- Sınav programı oluşturmak için `routes/planlama.py` içindeki formları doldurun ve `algorithms/planlama_algoritmasi.py`'yi kullanın.

