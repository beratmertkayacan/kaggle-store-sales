# Veri

Bu klasördeki dosyalar depoya dahil edilmiyor. Ham veri yaklaşık 125 MB, ikinci defterin ürettiği `features.csv` ise yaklaşık 700 MB olduğu için `.gitignore` kapsamında tutuluyor.

## İndirme

Kaggle hesabınızla yarışma kurallarını kabul ettikten sonra veriyi komut satırından indirebilirsiniz.

```bash
pip install kaggle
kaggle competitions download -c store-sales-time-series-forecasting -p data/
unzip data/store-sales-time-series-forecasting.zip -d data/
```

Alternatif olarak dosyaları [yarışma sayfasından](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data) indirip bu klasöre çıkarabilirsiniz.

## Beklenen dosyalar

| Dosya | Satır | Açıklama |
|---|---:|---|
| `train.csv` | 3.000.888 | Tarih, mağaza, ürün kategorisi kırılımında satış ve promosyon ürün sayısı |
| `test.csv` | 28.512 | Tahmin edilecek dönem, satış sütunu yok |
| `stores.csv` | 54 | Mağaza numarası, şehir, bölge, tip ve küme |
| `oil.csv` | 1.218 | Günlük ham petrol fiyatı, borsa kapalı günlerde boş |
| `holidays_events.csv` | 350 | Tatil ve etkinlikler, tip ve kapsam bilgisiyle |
| `transactions.csv` | 83.488 | Mağaza başına günlük işlem sayısı, 2017-08-15 tarihinde biter |
| `sample_submission.csv` | 28.512 | Gönderim biçimi örneği |

## Üretilen dosyalar

`02_feature_engineering.ipynb` defteri bu klasöre `features.csv` dosyasını yazar. 39 sütun ve 3.000.888 satır içerir, model eğitimi bu dosyayı okur.
