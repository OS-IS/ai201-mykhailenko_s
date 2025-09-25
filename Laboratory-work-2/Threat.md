# Таблиця виявлених загроз (Microsoft Threat Modeling Tool)

## Таблиця 1 – Результати аналізу виявлених загроз

| № загрози | Назва зв'язку (елемент Interaction з екрану аналізу) | STRIDE-клас загрози | Назва загрози (елемент Title з екрану аналізу) | Опис загрози (елемент Description з екрану аналізу) |
|-----------|-----------------------------------------------------|-------------------|-----------------------------------------------|---------------------------------------------------|
| 1 | Server DB Request | Spoofing | Spoofing of Source Data Store MySQL Database | MySQL Database may be spoofed by an attacker and this may lead to incorrect data delivered to SCADA Server |
| 2 | Server DB Request | Information Disclosure | Weak Access Control for a Resource | Improper data protection of MySQL Database can allow an attacker to read information not intended for disclosure |
| 3 | Server DB Request | Spoofing | Spoofing of Destination Data Store MySQL Database | MySQL Database may be spoofed by an attacker and this may lead to data being written to the attacker's target |
| 4 | Server DB Request | Denial of Service | Potential Excessive Resource Consumption for SCADA Server or MySQL Database | SCADA Server or MySQL Database may not control resource consumption leading to resource exhaustion attacks |
| 5 | Server ModBus Request | Elevation of Privilege | Elevation Using Impersonation | PLC may be able to impersonate the context of Raspberry Server in order to gain additional privilege |
| 6 | Server ModBus Response | Elevation of Privilege | Elevation Using Impersonation | Raspberry Server may be able to impersonate the context of PLC in order to gain additional privilege |
| 7 | Server MQTT Request | Elevation of Privilege | Elevation Using Impersonation | Raspberry Server may be able to impersonate the context of SCADA Server in order to gain additional privilege |
| 8 | Web Browser Request | Spoofing | Spoofing the Web Browser External Entity | Web Browser may be spoofed by an attacker and this may lead to unauthorized access to SCADA Server |
| 9 | Web Browser Request | Tampering | Potential Lack of Input Validation for SCADA Server | Data flowing across Web Browser Request may be tampered with by an attacker leading to various attacks |
| 10 | Web Browser Request | Repudiation | Potential Data Repudiation by SCADA Server | SCADA Server claims that it did not receive data from a source outside the trust boundary |

## Рекомендації щодо усунення загроз

### Для загроз типу Spoofing:
- Впровадження сильної взаємної автентифікації
- Використання цифрових сертифікатів
- Двофакторна автентифікація для операторів

### Для загроз типу Tampering:
- Використання цифрових підписів для критичних команд
- Впровадження контролю цілісності даних
- Шифрування каналів зв'язку

### Для загроз типу Information Disclosure:
- Шифрування даних при зберіганні та передачі
- Контроль доступу до конфіденційної інформації
- Сегментація мережі

### Для загроз типу Denial of Service:
- Впровадження обмеження швидкості запитів
- Моніторинг мережевого трафіку
- Резервування критичних компонентів

### Для загроз типу Elevation of Privilege:
- Принцип найменших привілеїв
- Регулярне оновлення програмного забезпечення
- Аудит доступу та привілеїв

### Для загроз типу Repudiation:
- Детальне журналювання всіх операцій
- Використання незаперечних протоколів
- Цифрові підписи для критичних операцій