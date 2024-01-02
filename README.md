# Bus-Reservation-App


## 1. INTRODUCTION
Bus Reservation App is a final project developed as a requirement to pass the Visual Programming lecture in 2022 at the Department of Informatics, University of Sriwijaya. This app is designed for booking buses for Jakarta-Bandung routes and viewing a list of order histories. I received an 'A' grade from the lecturer and successfully passed the Visual Programming lecture. This app was developed as simple as possible using the Java programming language and the Java Swing toolkit.


## 2. HARDWARE & SOFTWARE REQUIREMENTS
The hardware required to support the operation of this app is as follows:
1. Laptop or PC with a minimum display resolution of 1080 * 720

The software required to support the operation of this app is as follows:
1. Windows OS 10/11 64-bit
2. NetBeans IDE version 14 and above
3. Java Development Kit (JDK) version 15 and above
4. PHP minimum version 8.1.6
5. MariaDB server minimum version 10.4.24
6. XAMPP control panel v3.3.0


## 3. INSTALLING THE PROJECT
Installing the app via Git Bash CLI:
+ Open Git Bash
+ Choose the download folder location. For example: `cd d://downloads`
+ Type `git clone https://github.com/murafba/Bus-Reservation-App.git`
+ Check the download folder and open the project


## 4. SETTING UP THE DATABASE
Before running the app, you need to set up the database. You can import the database or follow the steps below:
1. Create a database named `db_pemesanan_bus`

```
CREATE DATABASE db_pemesanan_bus;
```

2. Create two tables in that database: one named `tb_riwayat` and the other named `tb_akun`.
`tb_riwayat` is a table used to store order history, while `tb_akun` is used to store user-entered data on the *Register* page.

```
CREATE TABLE tb_akun (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nama VARCHAR(50) NOT NULL,
  email VARCHAR(50) NOT NULL,
  nik VARCHAR(50) NOT NULL,
  noHp VARCHAR(50) NOT NULL,
  jk VARCHAR(50) NOT NULL,
  alamat VARCHAR(50) NOT NULL
);
```

```
CREATE TABLE tb_riwayat (
  id INT AUTO_INCREMENT PRIMARY KEY,
  tanggal VARCHAR(50) NOT NULL,
  waktu VARCHAR(50) NOT NULL,
  jmlh_dewasa INT NOT NULL,
  jmlh_anak INT NOT NULL,
  kelas VARCHAR(50) NOT NULL,
  total_bayar INT NOT NULL
);
```

> [!NOTE]
> The attribute `nama` means *name*, `nik` and `jk` refers to the national identification number and gender, while `noHp` and `alamat` represent *phone number* and *address*, respectively. In the `tb_riwayat` table, the attribute `tanggal` means *date*, `waktu` refers to *time*, while `jmlh_dewasa` and `jmlh_anak` stand for the number of adults and children. `kelas` and `total_bayar` represent the chosen bus class and the total amount to be paid by the user.

> [!TIP]
> You can change the database and table names. However, you also need to modify the database connection name and table names in the `MainForm.java` class at lines 984 and 1017, and in the `Register.java` class at lines 360 and 444.


## 5. RUNNING THE APP
Here are the steps to run the app:
1. Launch NetBeans
2. Open the downloaded project

> [!IMPORTANT]
> If the default JDK used is below version 15, it needs to be changed. Here are the steps: (a) Right-click on the project; (b) Select *properties*; (c) Choose the *Libraries* menu; (d) In the *Java Platform* dropdown menu, select JDK version 15 or above.

3. Open the default package and select the `MainForm.java` class


## 6. USING THE APP
There are 3 pages in this app, as follows:

> [!NOTE]
> This app was developed using the Indonesian language. Therefore, I have endeavored to translate the important meanings into English.

### 6.1 [Jadwal | Schedule] Page
On this page, users can view the available bus schedules for today and the next two days. Users can check the date through the dropdown menu, and each date will display schedules for the morning (translate: Pagi), afternoon (translate: Siang), and evening (translate: Malam). However, I didn't create a dynamic page; it's static. You can modify it as needed using Java Swing in NetBeans IDE. Below is the schedule page display.

![Schedule Page](https://github.com/murafba/Bus-Reservation-App/blob/main/images/Screenshot%202023-12-31%20142443.png?raw=true "Schedule Page")
*Fig. 1 The Schedule Page Display*

### 6.2 [Pemesanan | Booking] Page
The booking page (translate: Pemesanan) is where users can reserve a bus. There are three class options: economy, business, and executive. After selecting the desired class, you need to choose the date (translate: Tanggal) and departure time (translate: Waktu) from the available dropdown menu. Then, input the number of adults and children accompanying. Finally, view the cost details by clicking the *Check Price* *(translate: Cek Harga) button and confirming the terms and conditions. The data input will be stored in the `tb_riwayat` table. Click the *Book Bus* (translate: Pesan Bus) button to proceed. Fig. 2 illustrates the booking page for the business class.

![Booking Page](https://github.com/murafba/Bus-Reservation-App/blob/main/images/Screenshot%202023-12-31%20150420.png?raw=true "Booking Page")
*Fig. 2 The Booking Page for Business Class*

### 6.3 Registration Page
The registration page is located in a separate class called `Register.java`. This page will appear when the user clicks the *Book Bus* (translate: Pesan Bus) button. On this page, the user needs to fill in personal information such as name, email, ID number (translate: nik), phone number, gender, and address. The data will be stored in the `tb_akun` table. Press the submit button to proceed or the back (translate: Kembali) button to cancel. The user will return to the schedule page in the `MainForm.java` class. Here's the display of the registration page.

![Registration Page](https://github.com/murafba/Bus-Reservation-App/blob/main/images/Screenshot%202024-01-02%20193527.png?raw=true "Registration Page")
*Fig. 3 The Registration Page*

### 6.4 The Booking History Page
The page is used to view anonymous booking history. It is integrated with the `tb_riwayat` table. Click the button to refresh the table.

![The Booking History Page](https://github.com/murafba/Bus-Reservation-App/blob/main/images/Screenshot%202024-01-02%20202955.png?raw=true "The Booking History Page")
*Fig. 4 The Booking History Page*


## 7. ABOUT THE AUTHOR
> Hi! My name is Muhammad Rafi Akbar. You can call me Rafi. I'm a bachelor of computer science from University of Sriwijaya, majoring in Informatics. You can reach out to me through the following accounts.
+ [LinkedIn](https://linkedin.com/in/murafba)
+ [GitHub](https://github.com/murafba)


## 8. ACKNOWLEDGEMENT
I acknowledge that the program developed is still very basic and lacks clarity of app's functionality. This is because the final project for the Visual Programming lecture primarily emphasizes the GUI development. Therefore, the developer fouces solely on building the interface and didn't extensively consider the application's functionality.


## 9. HOW TO CONTRIBUTE
If any of you have ideas regarding updates to the application, you can fork this project and then create pull requests. I would be happy to appreciate various ideas from all of you. Additionally, you can also ask questions about the project in the Issues section.


## 10. SUPPORT ME
If you found my project pretty useful, you can show your support by attributing to this project and giving it a star on this repository. Alternatively, you can also provide material support through the following links:
+ [PayPal](https://paypal.me/murafba)
+ [Saweria (for Indonesian)](https://saweria.co/murafba)


## 11. LICENSE
Copyright &copy; 2024 Muhammad Rafi Akbar <br>
This project is under the [MIT](https://github.com/murafba/Bus-Reservation-App/blob/main/LICENSE) License.
