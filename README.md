# monte-carlo.py
import random

def monte_carlo_pi(toplam_nokta):
    cember_icindeki_noktalar = 0
    
    for _ in range(toplam_nokta):
        # 0 ile 1 arasında rastgele x ve y koordinatları üretir
        x = random.random()
        y = random.random()
        
        # Noktanın orijine olan uzaklığının karesi (x^2 + y^2)
        uzaklik_karesi = x**2 + y**2
        
        # Eğer uzaklık 1'den küçük veya eşitse nokta çemberin içindedir
        if uzaklik_karesi <= 1:
            cember_icindeki_noktalar += 1
            
    # Pi sayısı tahmini formülü
    pi_tahmini = 4 * (cember_icindeki_noktalar / toplam_nokta)
    return pi_tahmini

# --- Programın Çalıştırılması ---
# Ödev dökümanında belirtildiği gibi simülasyonu başlatıyoruz [cite: 1, 2]
deneme_sayisi = 100000
sonuc = monte_carlo_pi(deneme_sayisi)

print(f"Atılan Toplam Nokta: {deneme_sayisi}")
print(f"Tahmini Pi Sayısı: {sonuc}")
