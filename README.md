# Soal test magang Quality Assurance engineer

Berikut adalah soal/pertanyaan yang perlu dijawab oleh peserta

## Knowledge base

1. Apa yang anda ketahui tentang Rest API?
Jawaban:
REST API atau Representational State Transfer API (Application Programming Interface) adalah salah satu arsitektur dalam pengembangan layanan web. Sebuah API dikategorikan sebuah REST API jika menerapkan prinsip-prinsip utama REST, yaitu:
a. Stateless: Setiap permintaan dari client ke server harus mengandung semua informasi yang diperlukan untuk memahami dan memproses permintaan tersebut.
b. Client-Server: Memisahkan tanggung jawab antara client dan server, di mana client menangani antarmuka pengguna dan server menangani penyimpanan data.
c. Cacheable: Respon dari server harus menunjukkan apakah mereka dapat di-cache atau tidak, untuk meningkatkan performa.
d. Uniform Interface: Menyediakan antarmuka yang konsisten sehingga setiap interaksi antara client dan server dapat dipahami dan digunakan dengan cara yang sama.

2. Apa yang anda ketahui tentang Server side and Client side processing?
Jawaban:
a. Server-side Processing adalah proses eksekusi kode di server sebelum hasilnya dikirim ke client. Server-side processing digunakan untuk tugas-tugas seperti validasi data, manipulasi basis data, dan pemrosesan logika bisnis yang kompleks. Bahasa yang umum digunakan termasuk PHP, Python, Ruby, dan Node.js.
b. Client-side Processing adalah proses eksekusi kode di browser pengguna (client). Biasanya digunakan untuk interaksi pengguna yang dinamis, seperti validasi form secara real-time, animasi, dan manipulasi DOM. Bahasa yang digunakan adalah JavaScript, dan framework seperti React, Angular, atau Vue.js.

3. Apa yang anda ketahui tentang Monolith dan Microservices, berikan contohnya?
Jawaban:
Monolith adalah aplikasi besar yang semua komponennya  terintegrasi dan dikelola sebagai satu unit. Contohnya aplikasi e-commerce yang memiliki modul pengguna, produk, pesanan, dan payment dalam satu kode basis. Sedangkan microservices adalah sebuah arsitektur yang memecah aplikasi menjadi layanan-layanan lebih kecil  yang dapat dikembangkan secara independen. Contohnya adalah website e-commerce yang modul pengguna, produk, pesanan, dan payment dikelola sebagai layanan yang terpisah tapi dikomunikasiskan melalui API.

4. Apa yang anda ketahui tentang Automation testing serta sebutkan contohnya?
Jawaban:
Automation testing adalah proses pengujian perangkat lunak yang menggunakan bantuan tools dan framework yang mengharuskan tester menulis test script untuk mengeksekusi test case yang dibuat.
Contoh tools dalam automation testing adalah Selenium untuk pengujian aplikasi web.

5. Dengan menggunakan tools automation testing tersebut, biasanya menggunakan bahasa/tools apa?
Jawaban:
Selenium biasa digunakan dengan bahasa Java, Python, C#, dan Javascript.

## Use cases

Suppose there was a transaction that had been done in tokopedia.com , the transaction
id should be available on the screen alongside with the address of shipment, date of
order, seller’s name, and delivery service (JNE/POS/REX/others). 
The transaction id (TRX_ID) should also be available on the database which again supposedly there was a simple table containing all the transaction data.

![success notif](imgs/trx-notif.png)

![tabel transaksi](imgs/table-trx.png)

Apparently, the order `01023A9AC` seems to have different Delivery Service on the UI and the
database record. How do you, as automation test developers develop such test scenario so that this kind of error does not occur?

To ensure that the transaction information displayed in the user interface (UI) is consistent with the data in the database, we need to create automated test scenarios that verify data compliance between the UI and the database.

Test Scenario: Verify Consistency of Transaction Data between UI and Database
Test Case ID: TC001
Test Case Description:
Ensure that the transaction data displayed in the UI is consistent with the data stored in the database for a specific transaction.

Preconditions:
1. The user has access to the transaction page on Tokopedia.
2. The user has access to the database containing transaction data.
3. Transaction data with ID 01023A9AC is available in the database.

Test Steps:
1. Access the transaction page in the UI:
- Open the browser.
- Navigate to the transaction URL: https://www.tokopedia.com/transaction/01023A9AC.

2. Retrieve transaction data from the UI:
- Retrieve and store the Transaction ID (TRX_ID) from the relevant UI element.
- Retrieve and store the Address of shipment from the relevant UI element.
- Retrieve and store the Date of order from the relevant UI element.
- Retrieve and store the Seller’s name from the relevant UI element.
- Retrieve and store the Delivery service (JNE/POS/REX/others) from the relevant UI element.

3. Access the database to retrieve transaction data:
- Connect to the database that stores transaction data.
- Execute a query to retrieve the transaction data with Transaction ID 01023A9AC.
- Store the query results in the relevant variables.
- Compare the data from the UI with the data from the database:

4. Compare the Transaction ID from the UI with the database.
- Compare the Address of shipment from the UI with the database.
- Compare the Date of order from the UI with the database.
- Compare the Seller’s name from the UI with the database.
- Compare the Delivery service from the UI with the database.

5. Verify and report the test results:
- If all the data matches, report that the test passed.
- If there are any discrepancies, report that the test failed and identify the differences found.
