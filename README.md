# BOL Heat Kimya Sorgu

Bu uygulama coil listesi Excel dosyasini veya test sertifikasi PDF'ini yukleyip girilen BOL numarasina ait heat numaralarini, kimyasal sonuclari ve mekanik degerleri listeler.

## Calistirma

1. Bu klasorde `run_app.bat` dosyasina cift tiklayin.
2. Tarayicida acilan ekranda Excel veya PDF dosyasini yukleyin.
3. Sayfayi, BOL kolonunu, coil kolonunu, heat kolonunu ve kimyasal kolonlari kontrol edin.
   - Coil kolonu sizin dosyanizda `FULL_TAG_NUM` olarak secilmelidir.
4. BOL numarasini girin.
5. Sonucu ekranda inceleyin veya `Excel raporu indir` butonu ile raporu alin.

Komut satirindan calistirmak isterseniz:

```powershell
python -m streamlit run app.py
```

## Notlar

- Uygulama BOL, coil, heat ve kimyasal kolonlari otomatik tahmin eder, ama Excel formatiniz farkliysa sol panelden elle degistirebilirsiniz.
- `FULL_TAG_NUM` coil numarasi olarak raporda heat numarasinin yaninda gosterilir.
- PDF desteği metin tabanli PDF'ler icindir. Taranmis/resim PDF'lerde OCR gerekebilir.
- Ayni heat icinde ayni kimyasal kolon icin farkli degerler varsa `Kontrol` uyarisi verir.
- Indirilen raporda `Ozet`, `Heat Kimya`, `Detay` ve gerekiyorsa `Kontrol` sayfalari bulunur.
- Standart kontrolu icin `standards_rules.csv` dosyasindaki `Min` ve `Max` kolonlarini kendi resmi/internal limitlerinize gore doldurun.
- `Min` bos birakilirsa sadece maksimum, `Max` bos birakilirsa sadece minimum kontrol edilir. Ikisi de doluysa aralik kontrolu yapilir.
- `PDF uygunluk raporu indir` butonu, standart kontrol sonucunu PDF olarak verir. Minimum alti, maksimum ustu, eksik deger ve kontrol bulunamayan satirlar raporda ayrica belirtilir.
