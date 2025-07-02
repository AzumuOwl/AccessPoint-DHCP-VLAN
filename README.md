# 📡 Access Point Configuration with Multi-SSID, VLAN, and DHCP

#📶 Cisco AP VLAN + SSID Setup (แจก IP แยกตาม SSID)
โปรเจคนี้คือการตั้งค่า Access Point ของ Cisco ให้สามารถสร้าง Wi-Fi หลายชื่อ (SSID) และแจก IP แยกตาม VLAN อย่างถูกต้อง โดยใช้ Bridge Group Interface (BVI) เพื่อรับ IP จาก DHCP Server (เช่น Router)

#📌 เป้าหมาย
SSID_A → อยู่ใน VLAN 10 → ได้ IP ในวงของ VLAN 10
SSID_B → อยู่ใน VLAN 20 → ได้ IP ในวงของ VLAN 20

ใช้ trunk port เพื่อเชื่อมกับ switch/router ที่รองรับ VLAN
