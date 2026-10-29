# 55VPN — Android VPN build

Repository สำหรับเตรียมซอร์ส Android VPN และสร้าง Debug APK ผ่าน GitHub Actions

## สถานะ
- Repository ถูกสร้างแล้ว
- มีไฟล์ workflow สำหรับเริ่ม Build แบบ manual
- ต้องอัปโหลดซอร์สโปรเจกต์ Android จาก `ics-openvpn-master.zip` ให้ครบก่อน จึงจะ Build APK ได้
- ต้องรักษา `.gitmodules` และ Git submodule references ของ OpenVPN3/OpenVPN/OpenSSL ฯลฯ ให้ครบ ไม่ใช่เพียงคัดลอกโฟลเดอร์ว่างจาก ZIP

## วิธี Build
1. อัปโหลดซอร์ส Android ทั้งหมดลง root ของ repository โดยให้ `gradlew`, `settings.gradle` และโฟลเดอร์ `main/` อยู่ในตำแหน่งที่ถูกต้อง
2. ตรวจสอบว่า submodules ถูก checkout ครบ โดยเฉพาะ `main/src/main/cpp/openvpn3/client/ovpncli.i`
3. เปิดแท็บ **Actions**
4. เลือก **Build Android APKs** แล้วกด **Run workflow**
5. หากสำเร็จ ดาวน์โหลด APK จากส่วน **Artifacts** ของ workflow run

## ข้อควรทราบ
ZIP ที่ตรวจสอบก่อนหน้านี้ไม่มี Git history ที่ใช้งานได้ และมีไฟล์ submodule ที่ขาดหาย จึงต้องแก้ source/submodule ก่อน Build จริง
