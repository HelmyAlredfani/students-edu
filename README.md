# ALREDFANI SCHOOLS - Backend Application

هذا هو الكود المصدري للواجهة الخلفية لتطبيق إدارة نتائج مدارس الردفاني.

## المتطلبات الأساسية

*   Python 3.11 أو أحدث
*   pip (مدير حزم Python)
*   خادم قاعدة بيانات MySQL أو MariaDB

## خطوات الإعداد والتشغيل

1.  **استنساخ أو تحميل الكود:**
    قم بالحصول على ملفات المشروع.

2.  **إنشاء بيئة افتراضية (Virtual Environment):**
    افتح الطرفية (Terminal) في مجلد المشروع الرئيسي (`ALREDFANI_SCHOOLS`) ونفذ:
    ```bash
    python3 -m venv venv
    ```

3.  **تفعيل البيئة الافتراضية:**
    *   على Linux/macOS:
        ```bash
        source venv/bin/activate
        ```
    *   على Windows:
        ```bash
        .\venv\Scripts\activate
        ```

4.  **تثبيت الاعتماديات:**
    تأكد من أنك داخل البيئة الافتراضية ونفذ:
    ```bash
    pip install -r requirements.txt
    ```

5.  **إعداد قاعدة البيانات:**
    *   قم بإنشاء قاعدة بيانات جديدة على خادم MySQL الخاص بك (مثلاً باسم `alredfani_db`).
    *   قم بتعديل إعدادات الاتصال بقاعدة البيانات في ملف `src/main.py`.
        ابحث عن السطر:
        ```python
        app.config["SQLALCHEMY_DATABASE_URI"] = f"mysql+pymysql://{os.getenv("DB_USERNAME", "root")}:{os.getenv("DB_PASSWORD", "password")}@{os.getenv("DB_HOST", "localhost")}:{os.getenv("DB_PORT", "3306")}/{os.getenv("DB_NAME", "mydb")}"
        ```
        واستبدل `root`, `password`, `localhost`, `3306`, `mydb` بمعلومات الاتصال الصحيحة لقاعدة بياناتك، أو قم بتعيين متغيرات البيئة `DB_USERNAME`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT`, `DB_NAME`.

6.  **تشغيل التطبيق:**
    تأكد من أنك داخل البيئة الافتراضية ونفذ:
    ```bash
    python src/main.py
    ```
    سيقوم التطبيق بإنشاء الجداول اللازمة في قاعدة البيانات تلقائياً عند أول تشغيل، وإنشاء حساب المدير الافتراضي.

7.  **الوصول للتطبيق:**
    سيعمل التطبيق افتراضياً على العنوان `http://127.0.0.1:5000`.

## بيانات الدخول الافتراضية

*   **اسم مستخدم المدير:** alredfani
*   **كلمة مرور المدير:** 73345

## ملاحظات

*   هذا الكود يمثل الواجهة الخلفية (API) فقط. ستحتاج إلى تطوير واجهة أمامية منفصلة (باستخدام HTML/CSS/JavaScript أو أي إطار عمل مثل React/Vue/Angular) للتفاعل مع هذه الواجهة الخلفية.
*   تمت إزالة خاصية توليد ملفات PDF بسبب قيود بيئة النشر السابقة.

