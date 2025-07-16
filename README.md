# Student Search Widget

ويدجت بحث الطلاب المتقدم لـ Zoho Creator - يوفر بحث مباشر وفلترة متقدمة مع التحكم في الصلاحيات.

## المميزات

- بحث مباشر في أسماء الطلاب بدون إعادة تحميل الصفحة
- فلترة حسب الجنس، حالة الجواز، ونوع الطالب
- صلاحيات حسب نوع المستخدم (الوكلاء يرون طلابهم فقط)
- إحصائيات مباشرة للطلاب
- تصميم متجاوب يعمل على الموبايل

## المتطلبات

- Zoho Creator Premium أو Ultimate
- فورم باسم `Student_Form` يحتوي على:
  - `Full_Name` (مطلوب)
  - `Email` (مطلوب)  
  - `Mobile`, `Gender`, `Nationality`, `Passport_No`, `Photo`, `Student_Owner`, `Transfer_student` (اختياري)

## طريقة التثبيت

### 1. تحضير الملفات

```bash
git clone https://github.com/MohmedDarwish/AllStudntSit.git
cd AllStudntSit
```

### 2. تثبيت Zoho CLI

```bash
npm install -g zet
```

### 3. إنشاء package الويدجت

```bash
zet validate
zet pack
```

### 4. رفع الويدجت في Zoho Creator

1. اذهب لتطبيقك في Zoho Creator
2. Settings → Widgets
3. اضغط "Create Widget"
4. اختر "Internal" hosting
5. ارفع ملف ZIP من مجلد `dist`
6. حط Index File: `/widget.html`

## كيفية الاستخدام

### إضافة الويدجت للصفحة

1. اذهب لـ Design → Pages
2. اختر الصفحة اللي عايز تضيف الويدجت فيها
3. اضغط "Page Builder"
4. اسحب الويدجت من قائمة Widgets
5. احفظ الصفحة

### إعدادات الويدجت

- **Records Per Page**: عدد الطلاب في الصفحة (افتراضي: 20)
- **Enable Filters**: إظهار فلاتر البحث (افتراضي: مفعل)
- **Show Statistics**: إظهار الإحصائيات (افتراضي: مفعل)
- **Role-Based Access**: تقييد البيانات حسب نوع المستخدم (افتراضي: مفعل)

## أنواع المستخدمين

- **Admin**: يشوف جميع الطلاب
- **Active Agent**: يشوف الطلاب المخصصين له فقط

## هيكل البيانات المطلوب

### الحقول المطلوبة
- `Full_Name` - اسم الطالب
- `Email` - الإيميل

### الحقول الاختيارية
- `Mobile` - رقم الموبايل
- `Gender` - الجنس (Male/Female)
- `Nationality` - الجنسية
- `Passport_No` - رقم الجواز
- `Photo` - صورة الطالب
- `Student_Owner` - الوكيل المسؤول
- `Transfer_student` - طالب محول (Yes/No)

### الصفحات المطلوبة
- `Student_Page` - عرض تفاصيل الطالب
- `Edit_Student_Page` - تعديل بيانات الطالب
- `New_Student` - إضافة طالب جديد

## ملفات المشروع

```
AllStudntSit/
├── app/
│   ├── widget.html          # ملف الويدجت الرئيسي
│   └── manifest.json        # إعدادات الويدجت
├── package.json             # إعدادات المشروع
├── README.md               # هذا الملف
└── dist/                   # الملفات المُولدة
```

## التجربة المحلية

```bash
# تشغيل الويدجت محلياً
zet run

# فتح الويدجت في المتصفح
# http://127.0.0.1:5000/app/widget.html
```

## حل المشاكل الشائعة

**الويدجت مش بيحمل**
- تأكد من وجود حقول Full_Name و Email في الـ Student_Form
- تأكد من صلاحيات المستخدم
- شوف console في المتصفح للأخطاء

**البحث مش شغال**
- تأكد من وجود البيانات في Student_Form
- جرب مع بيانات تجريبية الأول

**الصلاحيات مش شغالة**
- تأكد من وجود حقل Student_Owner
- تأكد من تطابق إيميل المستخدم مع الـ owner

## الدعم الفني

- **المشاكل**: [GitHub Issues](https://github.com/MohmedDarwish/AllStudntSit/issues)
- **أسئلة**: [GitHub Discussions](https://github.com/MohmedDarwish/AllStudntSit/discussions)

## الإصدارات

### الإصدار 1.0.0
- الإصدار الأول
- بحث مباشر للطلاب
- فلترة متقدمة
- إحصائيات مباشرة
- تحكم في الصلاحيات
- تصميم متجاوب

## الترخيص

MIT License - يمكن استخدامه مجاناً ونسخه وتعديله.

---

**تم إنشاؤه بواسطة Mohamed Darwish**
