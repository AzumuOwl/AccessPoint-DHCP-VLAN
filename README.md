# 📡 Access Point Configuration with Multi-SSID, VLAN, and DHCP

## 📶 Cisco AP VLAN + SSID Setup (แจก IP แยกตาม SSID)
โปรเจคนี้คือการตั้งค่า Access Point ของ Cisco ให้สามารถสร้าง Wi-Fi หลายชื่อ (SSID) และแจก IP แยกตาม VLAN อย่างถูกต้อง โดยใช้ Bridge Group Interface (BVI) เพื่อรับ IP จาก DHCP Server (เช่น Router)

## 📌 เป้าหมาย
- Mansh1 → อยู่ใน VLAN 10 → ได้ IP ในวงของ VLAN 10
- Mansh2 → อยู่ใน VLAN 20 → ได้ IP ในวงของ VLAN 20

**ใช้ trunk port เพื่อเชื่อมกับ switch/router ที่รองรับ VLAN**

##🧪 การทดสอบ
###หลังตั้งค่าทั้งหมด:
- อุปกรณ์ที่เชื่อมต่อกับ SSID: Manosh1 จะได้รับ IP จาก VLAN 10
- อุปกรณ์ที่เชื่อมต่อกับ SSID: Manosh2 จะได้รับ IP จาก VLAN 20
- ตรวจสอบการเชื่อมต่อด้วยคำสั่ง show bridge, show dot11 associations, show interfaces

## 📌 หมายเหตุ
- อย่าลืมให้พอร์ตที่เชื่อมกับ AP บน Switch เป็น Trunk และอนุญาต VLAN ที่เกี่ยวข้อง
- ต้องมี DHCP Server ที่แจก IP แยกตาม VLAN หรือใช้ Router ที่ทำ DHCP Relay
- ใช้ BVI1 เพื่อรับ IP address ของ AP เอง ไม่ได้ส่งผลต่อ client
