# Flight Price Regression (Business & Economy)

Bu projede uçuş verileri kullanılarak `price` tahmini için regresyon modelleri kurulmuştur.
Veri seti; uçuşa ait çeşitli özellikler (şehirler, saatler, durak sayısı, uçuş süresi vb.) ve hedef değişken olarak `price` sütununu içerir.

## Amaç

* `price` tahmini için regresyon pipeline'ı kurmak
* `class` (Economy/Business) değişkeninin modele etkisini incelemek
* Business ve Economy veri setlerini ayrı ele alıp segment bazlı performansı test etmek

## Özet Bulgular

* Clean dataset üzerinde yüksek R² skorlarının ana kaynağı `class` sütunudur.
* Ablasyon testi ve permutation importance sonuçları `class` değişkeninin baskın etkisini göstermiştir.
* Segment bazında modelleme yapıldığında:

  * Business setinde performans anlamlı seviyede kalmıştır.
  * Economy setinde R² belirgin şekilde düşmüştür; mevcut feature seti ile fiyatın açıklanabilirliği sınırlıdır.

## Proje Yapısı

```
.
├── Flight_Price_Regressor.ipynb
├── data/                      # (gitignore ile hariç tutulur)
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

## Kurulum

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
```

## Çalıştırma

Notebook dosyasını çalıştır:

* `Flight_Price_Regressor.ipynb`

## Notlar

* Veri dosyaları lisans/kolaylık sebebiyle repoya eklenmemiştir.
* `data/` klasörüne yerleştirerek notebook’ta path’leri buna göre güncelleyebilirsin.

## Kullanılan Teknolojiler

* Python
* pandas, numpy
* scikit-learn
* xgboost
* matplotlib / seaborn
