# Attendance App — Flutter Android Starter

This is a starter source project for an Android employee attendance app with:
- Employee name/ID entry (prototype login only)
- Check-in and check-out using GPS coordinates
- Office-only geofence: 200 metres around City Plaza / Space Cinema, Bani Park, Jaipur
- Blocks check-in/out when reported GPS accuracy is worse than 100 metres or Android reports a mock location
- Selfie capture using the front camera
- Local attendance history
- Excel (.xlsx) export and Android share sheet

## Office geofence configuration
- Office address: Sanchit Financial and Management Services Ltd., 414, 4th Floor, City Plaza (Space Cinema), Bani Park, Jaipur 302016.
- Configured map centre: latitude `26.935581`, longitude `75.791931` (City Plaza / Space Cinema area; approximate map pin, not verified inside office suite 414).
- Allowed radius: `200 metres`.
- If the office entrance or GPS behaviour differs, update `_officeLat` and `_officeLon` in `lib/main.dart` after confirming the exact pin on-site.

## Important limitations
This starter stores records locally on one device. It is **not** a production multi-employee system:
- Employees do not yet share a central database.
- The name/ID screen is not secure authentication.
- Admin dashboard, server-side validation, anti-spoofing, and cloud photo storage are not implemented.
- GPS and a selfie alone do not guarantee identity or prevent location spoofing. Mock-location detection is only a basic check and can be bypassed on modified devices.
- The 200 m fence is checked when an employee taps check-in/check-out; it does not continuously track the employee.

## Run
1. Install Flutter SDK and Android Studio.
2. From this folder run:
   ```bash
   flutter create .
   flutter pub get
   flutter run
   ```
3. On Android, allow camera and location permissions when prompted.
4. To build an APK:
   ```bash
   flutter build apk --release
   ```
   APK output: `build/app/outputs/flutter-apk/app-release.apk`

Use HTTPS/server authentication and a proper backend before using this for real employee records.
