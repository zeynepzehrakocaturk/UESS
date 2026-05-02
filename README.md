<div align="center">

# Üniversite Sınav Sistemi Planlama

Flask tabanli bu uygulama; ogrenci, ders, ogretim uyesi ve derslik verilerini kullanarak sinav planlama surecini otomatiklestirir, cakismalari azaltir ve kaynak kullanimini optimize eder.

</div>

## Hızlı Erişim

| Bölüm | Açıklama |
| --- | --- |
| Amaç ve Kapsam | Sistem hedefleri ve kazanımlar |
| Kurulum | Ortamı hazırlama adımları |
| Çalıştırma | Uygulamayı başlatma komutları |
| Mimarî | Katmanlar ve sorumluluklar |
| Konfigürasyon | Ortam değişkenleri ve DB bağlantısı |
| Kullanım | Panel ve planlama akışı |

## Amaç ve Kapsam

| Hedef | Detay |
| --- | --- |
| Otomasyon | Sınav planlama sürecini manuel bağımlılıktan çıkarma |
| Çakışma Önleme | Öğrenci ve ders çakışmalarını azaltma |
| Kaynak Optimizasyonu | Derslik kapasitesini etkin kullanma |
| Yönetim Kolaylığı | Raporlama ve operasyonel takibi hızlandırma |

## Özellikler

| Modül | Yetkinlik |
| --- | --- |
| Planlama | Sınav planlama algoritması ile otomatik yerleştirme |
| Akademik Yönetim | Öğrenci, ders ve öğretim üyesi yönetimi |
| Derslik Yönetimi | Sınıf ve kapasite bazlı planlama |
| Yetkilendirme | Kimlik doğrulama ve yönetici paneli |
| Veri Aktarımı | CSV ile toplu yükleme |
| Analiz | Raporlama ve değerlendirme ekranları |

## Gereksinimler

| Bileşen | Sürüm |
| --- | --- |
| Python | 3.8+ |
| Paket Yöneticisi | pip |

## Kurulum

| Adım | Komut |
| --- | --- |
| Sanal ortam oluştur | `python -m venv venv` |
| PowerShell aktivasyon | `venv\Scripts\Activate.ps1` |
| CMD aktivasyon | `venv\Scripts\activate.bat` |
| Linux/macOS aktivasyon | `source venv/bin/activate` |
| Bağımlılıklar | `pip install -r requirements.txt` |

## Uygulamayı Çalıştırma

| Senaryo | Komut |
| --- | --- |
| Doğrudan başlatma | `python app.py` |
| Windows kısayol | `run.bat` |
| Linux/macOS kısayol | `./run.sh` |

Uygulama adresi: http://127.0.0.1:5000

## Proje Yapısı

```text
project-root/
|-- app.py
|-- config.py
|-- requirements.txt
|-- models/                  # Veritabani modelleri
|-- routes/                  # Flask route katmani
|-- templates/               # Jinja2 gorunumleri
|-- static/                  # CSS, JS ve statik varliklar
|-- algorithms/
|   |-- planlama_algoritmasi.py
|-- veritabani_goruntule.py
|-- run.sh
|-- run.bat
```

## Sistem Mimarisi

| Katman | Sorumluluk |
| --- | --- |
| Sunum Katmanı | `templates/` ile kullanıcı arayüzü |
| İş Mantığı Katmanı | `routes/` ile akış ve kurallar |
| Veri Katmanı | `models/` ile ORM ve veritabanı ilişkileri |
| Algoritma Katmanı | `algorithms/planlama_algoritmasi.py` ile planlama kararları |

## Planlama Algoritması

| Kriter | Açıklama |
| --- | --- |
| Öğrenci Çakışması | Aynı öğrenciye çakışan sınav atamasını engelleme |
| Derslik Kapasitesi | Sınıf kontenjanına uygun yerleşim |
| Zaman Optimizasyonu | Uygun zaman aralıklarını verimli kullanma |

Algoritma implementasyonu: `algorithms/planlama_algoritmasi.py`

## Veritabanı

| Başlık | Detay |
| --- | --- |
| ORM | SQLAlchemy |
| Varsayılan DB | SQLite |
| Örnek bağlantı | `sqlite:///data.db` |
| Model konumu | `models/` |

Mevcut veritabanını incelemek için:

```bash
python veritabani_goruntule.py
```

## Konfigürasyon

| Değişken | Açıklama | Örnek |
| --- | --- | --- |
| `FLASK_ENV` | Çalışma ortamı | `development` |
| `SECRET_KEY` | Güvenlik anahtarı | `secret` |
| `DATABASE_URL` | Veritabanı bağlantısı | `sqlite:///data.db` |

PowerShell:

```powershell
$env:FLASK_ENV = "development"
$env:SECRET_KEY = "secret"
$env:DATABASE_URL = "sqlite:///data.db"
```

Linux/macOS:

```bash
export FLASK_ENV=development
export SECRET_KEY=secret
export DATABASE_URL=sqlite:///data.db
```

## Kullanım Akışı

| Sıra | İşlem |
| --- | --- |
| 1 | Yönetici panelinden temel verileri ekleyin |
| 2 | CSV ile toplu öğrenci/ders verisi yükleyin |
| 3 | Sınav planlama sürecini başlatın |
| 4 | Oluşan planları rapor ekranından doğrulayın |

## Geliştirme

1. Fork oluşturun.
2. `feature/...` formatında yeni bir branch açın.
3. Değişiklikleri commit edin.
4. Pull request gönderin.

## Lisans

MIT License

