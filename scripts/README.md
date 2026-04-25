# DEU Tınaztepe Kampüsü Analizi

Bu depo, Dokuz Eylül Üniversitesi Tınaztepe Kampüsü için üretilen piksel tabanlı çevresel verilerin betimleyici istatistiklerini, parametrik olmayan testlerini, mekânsal bağımlılık analizlerini ve figürlerini üretmek için düzenlenmiştir.

## Beklenen ham veri dosyaları
`data_raw/` klasörü içine şu iki dosya yerleştirilmelidir:

- `deu_kampus_piksel_2024_tumdegiskenler.csv`
- `deu_fakulte_piksel_2024_tumdegiskenler.csv`
- `deu_fakulte_ndbi_duyarlilik_2024.csv`

## Klasör yapısı

- `data_raw/` : ham CSV dosyaları
- `data_processed/` : temizlenmiş RDS çıktıları
- `scripts/` : çalıştırılabilir R scriptleri
- `tables/` : CSV tablo çıktıları
- `figures/` : makale ve ek figürler
- `output/` : gerektiğinde geçici çıktılar
- `archive/` : eski sürümler ve kullanılmayan dosyalar

## Çalıştırma sırası

1. `scripts/00_config.R`
2. `scripts/01_prepare_data.R`
3. `scripts/02_descriptive_stats.R`
4. `scripts/03_nonparametric_tests.R`
5. `scripts/04_spatial_analysis.R`
6. `scripts/05_main_figures.R`
7. `scripts/06_appendix_figures.R`
8. `scripts/07_ndbi_sensitivity_analysis.R`

Tek komutla çalıştırmak için:

```r
source("run_all.R")
```

## Notlar

- Scriptler göreli klasör yapısıyla çalışır. Bilgisayara özel mutlak dosya yolu kullanılmaz.
- Paket kurulumları otomatik zorlanmaz. Gerekli paketler `00_config.R` içinde denetlenir ve eksik paketler açık biçimde bildirilir.
- Aynı analitik akış tek dosyada yığılmamış, üretim mantığına göre bölünmüştür.
