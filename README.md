# 🌡️ Termoizračun HR — Kalkulator snage klima uređaja

**Besplatni open source kalkulator za izračun potrebne snage klima uređaja prema EN 12831 normi.**  
Koristi javno dostupne klimatske podatke [DHMZ-a](https://meteo.hr/klima.php?section=klima_podaci&param=k1) za 20+ gradova u Hrvatskoj.

🔗 **Live verzija:** [profesionalna-klimatizacija.github.io/termoizracun-hr](https://profesionalna-klimatizacija.github.io/termoizracun-hr/)  
🏢 **Razvijač:** [Profesionalna klimatizacija, VRV sustavi d.o.o.](https://klimatizacija.pro) — Zagreb, Hrvatska

---

## ✨ Funkcionalnosti

- **Izbor lokacije** — 20 meteoroloških postaja (Zagreb, Split, Dubrovnik, Osijek, Rijeka i dr.)
- **Tip prostora** — stambeni, poslovni, restoran, server soba
- **Orijentacija i sunce** — sjever/jug/istok/zapad + razina izloženosti
- **Izolacija i prozori** — nova gradnja / stara gradnja / staklene površine
- **Broj osoba i kat** — prizemlje, srednji kat, potkrovlje
- **Dodatni izvori topline** — računala, kuhinja, rasvjeta, strojevi
- **Ventilacija** — recirkulacija / djelomična / puna izmjena zraka
- **Rezultat u kW i BTU/h** s preporukom modela (od 9.000 BTU do VRV sustava)
- **Detaljna razrada faktora** — transparentan prikaz svakog uvećanja

---

## 🌡️ Klimatski podaci (DHMZ)

| Grad | Zona | T srpnja (°C) |
|------|------|--------------|
| Zagreb | Kontinentalna | 21,4 |
| Osijek | Kontinentalna | 22,1 |
| Slavonski Brod | Kontinentalna | 22,0 |
| Rijeka | Primorska | 23,5 |
| Pula | Primorska | 24,0 |
| Zadar | Primorska | 25,3 |
| Split | Primorska | 26,2 |
| Hvar | Primorska | 26,8 |
| Dubrovnik | Primorska | 26,5 |
| Gospić | Gorska | 17,8 |
| ... | ... | ... |

Izvor: [DHMZ – Državni hidrometeorološki zavod](https://meteo.hr/klima.php?section=klima_podaci&param=k1), prosjek 1981.–2010.  
Licenca podataka: [Otvorena dozvola RH](https://data.gov.hr/otvorena-dozvola)

---

## 📐 Metodologija

Izračun se temelji na **EN 12831** europskoj normi za proračun projektnog toplinskog opterećenja:

```
Ukupna snaga = (Osnovna snaga + Korekcijski faktori) × 1.10
```

**Osnovna snaga:**
```
P_osnova = Površina (m²) × bazaWm2 (W/m²)
bazaWm2 = 30 + max(0, T_srpnja - 21.0)
```

**Korekcijski faktori:**
| Faktor | Korekcija |
|--------|-----------|
| Visina stropa > 2,6 m | proporcionalno |
| Poslovni prostor | +5 W/m² |
| Restoran | +15 W/m² |
| Server soba | +30 W/m² |
| Jug (orijentacija) | +3 W/m² |
| Zapad | +2 W/m² |
| Puno sunce | +9 W/m² |
| Zadnji kat / potkrovlje | +8 W/m² |
| Loša izolacija | +8 W/m² |
| Velike staklene površine | +5 W/m² |
| Računala/serveri | +300 W |
| Kuhinja | +800 W |
| Sigurnosni faktor | × 1,10 |

---

## 🚀 Korištenje

### Direktno u pregledniku
Jednostavno otvorite `index.html` u pregledniku — bez servera, bez instalacije.

### Ugradnja na vlastitu stranicu (iframe)
```html
<iframe 
  src="https://profesionalna-klimatizacija.github.io/termoizracun-hr/" 
  width="100%" 
  height="900" 
  frameborder="0"
  title="Kalkulator snage klima uređaja"
></iframe>
```

### Lokalno pokretanje
```bash
git clone https://github.com/profesionalna-klimatizacija/termoizracun-hr.git
cd termoizracun-hr
# Otvorite index.html u pregledniku
```

---

## 📄 Licenca

MIT License — slobodno koristite, modificirajte i distribuirajte uz navođenje autora.

```
Copyright (c) 2026 Profesionalna klimatizacija, VRV sustavi d.o.o.
(https://klimatizacija.pro)
```

Klimatski podaci DHMZ-a korišteni su pod [Otvorenom dozvolom RH](https://data.gov.hr/otvorena-dozvola).

---

## 🏢 O razvijačima

**Profesionalna klimatizacija, VRV sustavi d.o.o.**  
Zagreb, Hrvatska  
OIB: 42769573020

🌐 Website: [www.klimatizacija.pro](https://klimatizacija.pro)  
📞 Tel: [099 208 33 88](tel:0992083388)  
💬 WhatsApp: [wa.me/385992083388](https://wa.me/385992083388)

Specijalist za ugradnju i servis klima uređaja, VRV i DRV sustava u stanovima, uredima, restoranima i industrijskim objektima u Zagrebu i cijeloj Hrvatskoj.

---

*Ovaj projekt je nastao kao open source doprinos zajednici. Ako vam je alat koristan, ostavite ⭐ na GitHubu!*
