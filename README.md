
# kod-asistanim# 9. Sınıf Proje Ödevi: Dijital Asistan
# Kullanılan Konular: Değişkenler, Koşullar (if-else), Döngüler (while), Listeler, Fonksiyonlar

import datetime

def asistan():
    # 1. Kullanıcıdan isim alma ve zamana göre selamlama
    print("🤖 Merhaba! Ben senin 9. sınıf proje asistanınım.")
    isim = input("Sana nasıl hitap etmemi istersin?: ")
    
    # Günün saatini öğrenme
    simdiki_saat = datetime.datetime.now().hour
    
    if simdiki_saat >= 5 and simdiki_saat < 12:
        print(f"\nGünaydın, {isim}!")
    elif simdiki_saat >= 12 and simdiki_saat < 18:
        print(f"\nTünaydın, {isim}!")
    else:
        print(f"\nİyi akşamlar, {isim}!")

    # Notları saklamak için boş bir liste oluşturuyoruz
    notlar = []

    # 2. Ana Menü Döngüsü
    while True:
        print("\n" + "="*30)
        print("       AKILLI ASİSTAN MENÜSÜ")
        print("="*30)
        print("1. Hesap Makinesi")
        print("2. Not Ekle")
        print("3. Notlarımı Listele")
        print("4. Çıkış")
        
        secim = input("\nLütfen bir işlem seçin (1-4): ")

        # SEÇİM 1: HESAP MAKİNESİ
        if secim == "1":
            print("\n--- HESAP MAKİNESİ ---")
            print("İşlemler: +, -, *, /")
            
            try:
                sayi1 = float(input("1. Sayıyı girin: "))
                islem = input("İşlem seçin (+, -, *, /): ")
                sayi2 = float(input("2. Sayıyı girin: "))
                
                if islem == "+":
                    print("Sonuç:", sayi1 + sayi2)
                elif islem == "-":
                    print("Sonuç:", sayi1 - sayi2)
                elif islem == "*":
                    print("Sonuç:", sayi1 * sayi2)
                elif islem == "/":
                    if sayi2 == 0:
                        print("Hata: Bir sayı sıfıra bölünemez!")
                    else:
                        print("Sonuç:", sayi1 / sayi2)
                else:
                    print("Geçersiz işlem seçtiniz!")
            except ValueError:
                print("Hata: Lütfen geçerli bir sayı girin!")

        # SEÇİM 2: NOT EKLEME
        elif secim == "2":
            yeni_not = input("\nEklemek istediğin notu yaz: ")
            notlar.append(yeni_not)
            print("✔ Not başarıyla eklendi!")

        # SEÇİM 3: NOTLARI LİSTELEME
        elif secim == "3":
            print("\n--- NOTLARIN ---")
            if len(notlar) == 0:
                print("Henüz kayıtlı bir notun yok.")
            else:
                for sira, n in enumerate(notlar, 1):
                    print(f"{sira}. {n}")

        # SEÇİM 4: ÇIKIŞ
        elif secim == "4":
            print(f"\nGörüşürüz {isim}, projende başarılar dilerim! 👋")
            break  # Döngüyü sonlandırır

        else:
            print("Geçersiz seçim! Lütfen 1 ile 4 arasında bir sayı girin.")

# Programı başlat
asistan()

