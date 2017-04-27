Nguồn: http://ionichelper.forlearning.net/ionic-2-building-a-release-android-apk

1. Di chuyển tới thư mục dự án
cd ionic3Blank

2. Thêm platform Android
ionic platform add android

3. Tạo khóa keystore
keytool -genkey -v -keystore android.keystore -alias android -keyalg RSA -keysize 2048 -validity 10000

4. Di chuyển android.keystore tới thư mục platform/android

5. Tạo tập tin release-signing.properties với nội dung sau:
key.store=<YOUR_KEYSTORE>.keystore
key.store.password=<YOUR_KEYSTORE password>
key.alias=<YOUR_ALIAS>
key.alias.password=<YOUR_ALIAS password>

6. Phát hành ứng dụng apk
ionic build android --release

7. Tối ưu và livereload ứng dụng apk
ionic run android --prod --release -l -s -c
