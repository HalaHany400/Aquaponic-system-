# Aqua Control Web Serial

واجهة Flutter Web لقراءة بيانات الـ `ESP` من اللابتوب عبر `USB Serial` بدل البلوتوث.

## التشغيل

1. شغّل:
```bash
flutter pub get
flutter run -d chrome
```
2. افتح التطبيق في `Chrome` أو `Edge`.
3. وصّل لوحة `ESP` بالـ USB.
4. اضغط `Connect Serial` واختر منفذ اللوحة.
5. اضغط `Start Monitoring` لبدء حفظ القراءات وعرضها.

## كود الـ ESP

ملف المتحكم موجود هنا:

- `lib/esp code.c`

الكود يرسل سطر JSON كل `500ms` بالشكل التالي:

```json
{"temp":24.3,"distance":11.5,"tds":320,"pump":true,"fan":false,"heater":false,"dose":false,"steps":0,"status":"PUMPING","profile":"ornamental"}
```

ويرسل التطبيق أوامر تغيير نوع السمك بهذا الشكل:

```text
PROFILE:ornamental
PROFILE:catfish
```
