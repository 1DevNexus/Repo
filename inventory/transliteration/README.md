# Quran Transliteration Data

## 📖 الوصف

هذا المجلد يحتوي على نطق القرآن الكريم بالحروف اللاتينية (Transliteration) لجميع السور الـ 114.

## 📁 محتويات المجلد

- **114 ملف JSON** - كل ملف يمثل سورة واحدة
- تنسيق الملفات: `surah_1.json` إلى `surah_114.json`

## 📊 هيكل البيانات

كل ملف JSON يحتوي على:

```json
{
  "id": 1,
  "name": "الفاتحة",
  "transliteration": "Al-Fatihah",
  "type": "meccan",
  "total_verses": 7,
  "verses": [
    {
      "id": 1,
      "text": "بِسۡمِ ٱللَّهِ ٱلرَّحۡمَٰنِ ٱلرَّحِيمِ",
      "transliteration": "Bismi Allahi alrrahmani alrraheemi"
    }
  ]
}
```

## 🔑 الحقول

| الحقل | الوصف |
|------|-------|
| `id` | رقم السورة (1-114) |
| `name` | اسم السورة بالعربية |
| `transliteration` | اسم السورة بالحروف اللاتينية |
| `type` | نوع السورة (meccan/medinan) |
| `total_verses` | عدد الآيات في السورة |
| `verses` | مصفوفة تحتوي على جميع آيات السورة |

### حقول الآية:

| الحقل | الوصف |
|------|-------|
| `id` | رقم الآية في السورة |
| `text` | نص الآية بالعربية |
| `transliteration` | نطق الآية بالحروف اللاتينية |

## 📥 المصدر

البيانات مأخوذة من:
- **المصدر:** [quran-json](https://github.com/risan/quran-json)
- **CDN:** jsdelivr.net
- **النسخة:** 3.1.2
- **الترخيص:** MIT License

## 🎯 الاستخدام المستقبلي

هذه البيانات معدة للرفع على السيرفر لتوفير ميزة النطق اللاتيني للقرآن الكريم في التطبيق.

## 📊 الإحصائيات

- **عدد السور:** 114 سورة
- **إجمالي الآيات:** 6236 آية
- **حجم البيانات:** ~2.5 MB
- **التنسيق:** JSON
- **الترميز:** UTF-8

## 🔄 تحديث البيانات

تاريخ التحميل: 13 نوفمبر 2025

لتحديث البيانات، استخدم الأمر التالي:

```powershell
$baseUrl = "https://cdn.jsdelivr.net/npm/quran-json@3.1.2/dist/chapters/"
$outputDir = "d:\Work\Main\Quran\prime\inventory\transliteration"

for ($i = 1; $i -le 114; $i++) {
    $url = "$baseUrl$i.json"
    $outputFile = Join-Path $outputDir "surah_$i.json"
    Write-Host "Downloading Surah $i..."
    Invoke-WebRequest -Uri $url -OutFile $outputFile -UseBasicParsing
    Start-Sleep -Milliseconds 200
}

Write-Host "Download complete! 114 surahs downloaded."
```

## 📝 ملاحظات

- البيانات متوافقة مع معيار Uthmani للنص القرآني
- النطق اللاتيني من tanzil.net
- جميع الملفات بصيغة JSON صالحة ومنسقة
- يمكن استخدامها مباشرة في التطبيق أو رفعها على API

## 🚀 الخطوات التالية

1. ✅ تحميل جميع السور (114 سورة)
2. ⏳ رفع البيانات على السيرفر
3. ⏳ إنشاء API endpoint للوصول للبيانات
4. ⏳ دمج النطق اللاتيني في واجهة التطبيق

---

**تم بحمد الله** 🕌
