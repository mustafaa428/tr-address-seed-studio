# 🇹🇷 Türkiye Adres Verisi — SQL Seed Studio

Türkiye genelindeki **81 İl, 973 İlçe ve ~53.000+ Mahalle / Posta Kodu** hiyerarşisini; farklı veritabanı motorları, Primary Key standartları ve isimlendirme kurallarına göre özelleştirerek tek tıkla ilişkisel `SQL SEED` dosyasına dönüştüren açık kaynaklı, tamamen tarayıcı tabanlı (client-side) geliştirici aracı.

🔗 **Canlı Demo (GitHub Pages):** [https://mustafaa428.github.io/tr-address-seed-studio/](https://mustafaa428.github.io/tr-address-seed-studio/)

---

## ✨ Öne Çıkan Özellikler

* **Çoklu Veritabanı Motoru Desteği:**
  * **PostgreSQL** (`"Cities"`, `UUID`, `TIMESTAMPTZ`, `ON CONFLICT DO NOTHING`)
  * **MSSQL / SQL Server** (`[Cities]`, `UNIQUEIDENTIFIER`, `NVARCHAR`, `DATETIME2`)
  * **MySQL / MariaDB** (`` `Cities` ``, `CHAR(36)`, `INSERT IGNORE`)
* **Esnek Primary Key (ID) Seçenekleri:**
  * **UUIDv7 (RFC 9562):** B-Tree indeks fragmantasyonunu önleyen, zaman sıralı (time-ordered) modern GUID üretimi.
  * **UUIDv4:** Standart rastgele GUID üretimi.
  * **INT:** 1'den başlayan deterministik sıralı tam sayı ID'ler.
* **Tam İsimlendirme Kontrolü:**
  * Tek tıkla **PascalCase** (`.NET / EF Core` standartları) veya **snake_case** (`PostgreSQL / Laravel / Django` standartları) geçişi.
  * Mevcut projenizdeki şemaya birebir uyum için tüm tablo ve kolon adlarını (`Cities`, `Districts`, `Neighborhoods`, `CityId`, `DistrictId`, `PostalCode` vb.) manuel özelleştirme imkânı.
* **DDL ve Audit Kolonları:**
  * İsteğe bağlı `CREATE TABLE` (Foreign Key ve `ON DELETE CASCADE` tanımlı) şema çıktısı.
  * İsteğe bağlı `CreatedAt` ve `UpdatedAt` audit kolonları.
* **%100 Client-Side ve Hızlı:**
  * Herhangi bir sunucu kurulumu veya bağımlılık gerektirmez. Tüm SQL üretimi tarayıcı belleğinde milisaniyeler içinde gerçekleşir.

---

## 📂 Proje Yapısı

```text
tr-address-seed-studio/
├── index.html                  # Özelleştirilebilir Web UI ve SQL Seed motoru
├── turkey_addresses.json       # Türkiye İl / İlçe / Mahalle / Posta Kodu veri seti
└── README.md