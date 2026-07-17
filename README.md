# 👨‍💻 Employee Burnout Prediction (End-to-End ML)

Bu layihə, işçilərin iş yükü və mental yorğunluq göstəriciləri əsasında onların tükənmə (burnout) dərəcəsini proqnozlaşdırmaq üçün hazırlanmışdır.
## 🎯 Nə Analiz Edirik və Niyə?

Bu layihədə işçilərin iş yükü, mental yorğunluq və resurs bölgüsü göstəriciləri əsasında 
onların tükənmə (burnout) dərəcəsini proqnozlaşdırmaq üçün Linear Regression modeli 
qurulub.

**Niyə vacibdir?** İşçi tükənməsi məhsuldarlıq itkisinə və işdən çıxma nisbətinin artmasına 
səbəb olur. Model vasitəsilə hansı faktorların tükənməyə ən çox təsir etdiyini müəyyən 
edərək, HR-in erkən müdaxilə etməsinə imkan yaradılır.

**Tədqiq olunan sual:** İş yükü, mental yorğunluq, resurs bölgüsü və vəzifə səviyyəsi 
əsasında işçinin tükənmə dərəcəsini nə qədər dəqiqliklə proqnozlaşdırmaq mümkündür?

## 🚀 Layihənin Mərhələləri
1. **Data Cleaning:** Boşluqların doldurulması və lazımsız məlumatların təmizlənməsi.
2. **Outlier Detection:** IQR metodu ilə kənarlaşmaların təyin edilməsi və modelin dəqiqliyi üçün təmizlənməsi.
3. **Feature Engineering:** `Stress_Index` adlı yeni effektiv sütun yaradılaraq model performansı artırıldı.
4. **EDA:** Seaborn və Matplotlib kitabxanaları ilə datanın vizual analizi aparıldı.
5. **Modeling:** Linear Regression modeli istifadə olundu və **87% R2 score** əldə edildi.

## 📊 Dərin Analiz və Vizuallaşdırma

Layihənin bu hissəsində həm datanın daxili strukturunu, həm də modelin performansını əks etdirən əsas vizualları təqdim edirəm:

### 1. Model Performansı: Actual vs Predicted
Modelin proqnozlarının real dəyərlərlə müqayisəsi. Nöqtələrin mərkəzi xətt boyunca sıxlığı modelin **87% dəqiqliyini** və yüksək proqnoz gücünü göstərir.
<img width="691" height="547" alt="image" src="https://github.com/user-attachments/assets/11c86887-fec0-4413-bfa0-0827ca7a258f" />


### 2. Faktorların Təsiri (Feature Importance)
Model tərəfindən müəyyən edilən, "Tükənmə dərəcəsinə" (Burn Rate) ən çox təsir edən faktorlar. Bu analiz göstərir ki, işçinin mental yorğunluğu və iş yükü ən kritik göstəricilərdir.
<img width="1105" height="470" alt="image" src="https://github.com/user-attachments/assets/d87936d7-19cb-4d01-bb94-ae54965f8363" />


### 3. Stress İndeksi Paylanması (Stress Index Distribution)
Yeni yaratdığım `Stress_Index` xüsusiyyətinin datada necə paylandığını göstərir. Bu qrafik işçilərin stress səviyyəsinin ümumi mənzərəsini vizuallaşdırır.
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/6119b5ed-93b0-44b5-9299-48e6253713a3" />


### 4. Tükənmə Paylanması (Burn Rate Distribution)
İşçilərin ümumi tükənmə dərəcəsinin (target variable) sıxlığı. Bu, datadakı balansın və orta tükənmə səviyyəsinin başqa göstəricilərlə əlaqəsini anlamağa kömək edir.
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/7b78e455-64c6-4dae-ba3e-c0f1521abffa" />


### 5. Resurs Bölgüsü və Stress Əlaqəsi (Resource Allocation vs Stress Index)
İşçiyə ayrılan resursların (iş yükü/komandada mövqeyi) stress səviyyəsinə təsiri. Bu Barplot vasitəsilə resurs artdıqca stressin necə dəyişdiyini müşahidə edirik.
<img width="687" height="470" alt="image" src="https://github.com/user-attachments/assets/238ebec2-6bd3-4b78-b7e9-3e8cc70bee48" />


### 6. Vəzifə və Tükənmə (Designation vs Burn Rate)
İşçinin vəzifə dərəcəsi (Designation) ilə tükənmə dərəcəsi arasındakı əlaqə. Boxplot vasitəsilə hər vəzifə qrupu üçün median dəyərləri və potensial kənarlaşmaları (outliers) görə bilirik.
<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/59484eff-0430-4e3e-8ef4-0436cef91a1a" />


### 7. Korrelyasiya Heatmap
Bütün dəyişənlər arasındakı riyazi əlaqəni göstərən təkmilləşdirilmiş matris. Bu, multikolinearlıq riskini idarə etməyə kömək edir.
<img width="768" height="659" alt="image" src="https://github.com/user-attachments/assets/e9a6bead-e71c-4ba4-9a8d-56eab9466936" />

## ✅ Nəticə

Linear Regression modeli **87% R² score** ilə işçi tükənməsini uğurla proqnozlaşdırdı — 
yəni modelin proqnozları real dəyərlərin 87%-lik dəyişkənliyini izah edir.

Analiz nəticəsində müəyyən edildi ki:

- **Mental yorğunluq** və **iş yükü** tükənməyə ən çox təsir edən iki faktordur (Feature 
  Importance analizinə əsasən)
- Yaradılan `Stress_Index` göstəricisi model performansını artırdı
- Resurs bölgüsü ilə stress səviyyəsi arasında aydın əlaqə var — resurs artdıqca stress 
  dəyişir
- Fərqli vəzifə qrupları fərqli median tükənmə səviyyəsi göstərir, yəni risk bərabər 
  paylanmır

**Praktik tətbiq:** Bu model HR komandalarına yüksək risk daşıyan işçi qruplarını 
əvvəlcədən müəyyən etmək və resurs bölgüsünü buna uyğun tənzimləmək imkanı verir.

## 📁 İstifadə Olunan Kitabxanalar
- Pandas, Numpy
- Scikit-learn
- Matplotlib, Seaborn
