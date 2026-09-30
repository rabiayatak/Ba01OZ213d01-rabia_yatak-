[FİZİKSEL_PROGRAMLAMA_1.py](https://github.com/user-attachments/files/32853742/FIZIKSEL_PROGRAMLAMA_1.py)
print("==============================================================")
print("       GÜNE ÖZEL KAMPÜS VERİMLİLİK VE ZAMAN TASARIMCISI       ")
print("==============================================================")

# 1. BÖLÜM: ÖĞRENCİDEN KURTARMAK İSTEDİĞİ GÜNÜ VE SAATLERİ ALMA
ogrenci_adi = input("Öğrencinin Adı: ")
secilen_gun = input("Hangi gününüzü daha verimli hale getirmek istiyorsunuz? (Örn: Çarşamba): ")

print("\n---", secilen_gun, "GÜNÜ DERS VE BOŞLUK BİLGİLERİNİZ ---")
ders_saati = int(input("O gün toplam kaç saat dersiniz var?: "))
bosluk_saati = int(input("O gün dersler arasında kaç saat boşluğunuz var?: "))
yol_saati = int(input("O gün okula geliş-gidiş toplam kaç saat yolda geçiyor?: "))

# 2. BÖLÜM: ÖĞRENCİNİN O GÜNKÜ ÖNCELİKLİ HEDEFİNİ SEÇTİRME
print("\n---", secilen_gun, "GÜNÜ BOŞLUĞUNDA ASIL HEDEFİNİZ NE? ---")
print("1 - Ödev / Proje Eritme (Bilgisayar başında yoğun odaklanma gerekiyor)")
print("2 - Sınav / Konu Tekrarı (Ders notlarını okuma ve özet çıkarma gerekiyor)")
print("3 - Enerji Koruma (O günkü derslerim çok ağır, beynimi yormadan verimli geçirmek istiyorum)")
hedef_secimi = int(input("O gün için hedefiniz hangisi? (1, 2 veya 3 yazınız): "))

# 3. BÖLÜM: O GÜNE ÖZEL MATEMATİKSEL HESAPLAMALAR
# O gün evden çıkıp eve dönene kadar okul için harcanan toplam mesai
gunluk_toplam_mesai = ders_saati + bosluk_saati + yol_saati

# Boşluk saatini dakika bazında planlamak için 60 ile çarpıyoruz
bosluk_dakika = bosluk_saati * 60

# Sadece bu günü verimli kullanarak 14 haftalık dönemde kazanılacak toplam saat
donemlik_kazanc = bosluk_saati * 14

# Öğrencinin seçtiği hedefe göre o günkü boşluğu dakikalara bölüyoruz
if hedef_secimi == 1:
    calisma_dakika = bosluk_dakika - 40
    mola_dakika = 40
    gorev_turu = "Kütüphanede Masabaşı Ödev/Proje Geliştirme"
elif hedef_secimi == 2:
    calismaza_dakika = bosluk_dakika - 30
    mola_dakika = 30
    gorev_turu = "Sessiz Çalışma Alanında Konu Tekrarı ve Özet"
else:
    calisma_dakika = bosluk_dakika / 2
    mola_dakika = bosluk_dakika / 2
    gorev_turu = "Yarı Yarıya Hafif Okuma ve Zihinsel Dinlenme"

# 4. BÖLÜM: SEÇİLEN GÜNE ÖZEL REÇETE VE KARNEYİ YAZDIRMA
print("\n==============================================================")
print(secilen_gun, "GÜNÜ VERİMLİLİK PLANI - Öğrenci:", ogrenci_adi)
print("==============================================================")
print("-> Seçilen Odak Modu:", gorev_turu)
print("1. O Gün Okul ve Yolda Geçen Toplam Süre:", gunluk_toplam_mesai, "saat")
print("2. Değerlendirilecek Ders Arası Boşluğu:", bosluk_saati, "saat (", bosluk_dakika, "dakika )")
print("3. Önerilen Net Odaklanma Süresi:", calisma_dakika, "dakika")
print("4. Önerilen Yemek / Kahve / Dinlenme Süresi:", mola_dakika, "dakika")
print("5. Sadece", secilen_gun, "Gününü Kurtararak Dönemde Kazanacağınız Süre:", donemlik_kazanc, "saat!")
print("--------------------------------------------------------------")

# 5. BÖLÜM: BOŞLUK SÜRESİNE GÖRE O GÜNÜ KURTARMA STRATEJİSİ
print(">>>", secilen_gun, "GÜNÜ BOŞLUĞUNU NASIL DEĞERLENDİRMELİSİNİZ?:")
if bosluk_saati >= 4:
    print("STRATEJİ (Büyük Kampüs Boşluğu): O gün dersleriniz arasında çok uzun bir boşluk var!")
    print("EYLEM PLANI: Bu süre kantinde oturarak geçmez, insanı daha çok yorar. İlk", mola_dakika, "dakikada yemeğinizi yiyin, kalan", calisma_dakika, "dakikada doğrudan kütüphaneye geçip haftanın en zor ödevini okulda bitirin.")

elif bosluk_saati >= 2:
    print("STRATEJİ (Altın Zaman Dilimi): Eve dönmek için kısa ama bir işi bitirmek için mükemmel bir süre!")
    print("EYLEM PLANI: Ders biter bitmez", mola_dakika, "dakika hava alıp kahvenizi için. Ardından", calisma_dakika, "dakika boyunca telefonunuzu sessize alıp sadece seçtiğiniz hedefe odaklanın.")

else:
    print("STRATEJİ (Kısa Geçiş Arası): Boşluğunuz", bosluk_saati, "saat olduğu için ağır bir projeye başlamayın.")
    print("EYLEM PLANI: Bu süreyi bir sonraki dersin notlarına göz atmak ve zihninizi dinlendirmek için kullanın.")

# 6. BÖLÜM: O GÜNÜN AKŞAMI İÇİN ENERJİ VE EV PLANI
print("\n>>>", secilen_gun, "AKŞAMI EVE GİDİNCE NE YAPMALISINIZ?:")
if gunluk_toplam_mesai >= 9:
    print("AKŞAM KARARI (Yüksek Yorgunluk Riski): O gün okul ve yol toplam", gunluk_toplam_mesai, "saatinizi alıyor!")
    print("TAVSİYE: O akşam eve gittiğinizde masa başına geçme planı yapmayın, verim alamazsınız. Tüm çalışmanızı gündüz kampüsteki", calisma_dakika, "dakikalık boşlukta tamamlayın ve akşam evde sadece dinlenin.")

elif gunluk_toplam_mesai >= 6:
    print("AKŞAM KARARI (Dengeli Yoğunluk): Gündüz okulda", gunluk_toplam_mesai, "saatlik orta yoğunlukta bir mesainiz var.")
    print("TAVSİYE: Gündüz boşluktaki planı uygularsanız, akşam evde sadece 45 dakikalık hafif bir tekrar yapmanız yeterli olacaktır.")

else:
    print("AKŞAM KARARI (Yüksek Enerji): O gün okul mesainiz sadece", gunluk_toplam_mesai, "saat sürüyor.")
    print("TAVSİYE: Eve enerjiniz yüksek döneceğiniz için ağır çalışma ve projelerinizi o akşam evde rahatça yapabilirsiniz.")
print("==============================================================")

# EKRANIN KAPANMASINI ENGELLEYEN SATIR
input("\nAnaliz tamamlandı. Çıkmak için Enter tuşuna basınız...")
