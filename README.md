# Tugas Pratikum
Membuat pemrograman fungai tambah, fungsi tampilkan, fungsi hapus, fungsi ubah menggunakan CLASS 

# Codingan 
```
class Item:
    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity
        
    def total_price(self):
        return self.price * self.quantity

class CashRegister:
    def __init__(self):
        self.items = []
        self.payment_amount = 0
        self.change = 0
         
    def add_item(self, name, price, quantity):
        new_item = Item(name, price, quantity)
        self.items.append(new_item)
        print(f"Item '{name}' added with price {price} and quantity {quantity}.")
        
    def display_items(self):
        if not self.items:
            print("No items in the cart.")
            return
        print("\n--- Items in the Cart ---")
        for idx, item in enumerate(self.items, 1):
            print(f"{idx}. {item.name} - {item.price:.2f} x {item.quantity} = {item.total_price():.2f}")
            print("\n")
    def calculate_total(self):
        total = sum(item.total_price() for item in self.items)
        return total
    def process_payment(self):
        total = self.calculate_total()
        print(f"\n Total Amount: {total:.2f}")
        while True:
            try:
                payment = float(input("Masukan total: "))
                if payment < total:
                    print("pembayaran gagal. Silahkan masukkan nominal yang benar. ")
                else: 
                    self.payment_amount = payment 
                    self.change = payment - total
                    change = payment - total
                    print(f"kembalian : {change :.2f}")
                    return
            except ValueError:
                print("input tidak valid")
    def print_receipt(self):
        if not self.items:
            print("No items to print on the receipt.")
            return
        print("\n====== Receipt ======")
        for item in self.items:
            print(f"{item.name} - {item.price:.2f} x {item.quantity} = {item.total_price():.2f}")
        total = self.calculate_total()
        print("---------------------")
        print(f"Total: {total:.2f}")
        print(f"total pembayaran: {self.payment_amount:.2f} ")
        print(f"kembalian: {self.change:.2f}")
        print("=====================\n")
    # Program utama
def main():
    register = CashRegister()
    while True:
        print("1. Add Item")
        print("2. Display Items")
        print("3. Print Receipt")
        print("4. exit")
        choice = input("Choose an option: ")
        if choice == '1':
            name = input("Enter item name: ")
            price = float(input("Enter item price: "))
            quantity = int(input("Enter item quantity: "))
            register.add_item(name, price, quantity)
        elif choice == '2':
            register.display_items()
        elif choice == '3':
            register.process_payment()
            register.print_receipt()
        elif choice == '4':
            print("Exiting the program. Thank you!")
            break
        else:
                print("Invalid choice. Please try again.")
                 
if __name__ == "__main__":
    main()
```
# Penjelasan
Penjelasan Program Utama:
1. Class PersonManager
Digunakan untuk mengelola data mahasiswa, seperti menambah, menampilkan, menghapus, atau mengubah data.

2.Menu Interaktif:
Program menyediakan menu untuk memilih operasi:
1: Tambah data mahasiswa.
2: Tampilkan semua data mahasiswa.
3: Hapus data mahasiswa berdasarkan nama.
4: Ubah nilai mahasiswa berdasarkan nama.
5: Keluar dari program.

3. Validasi Input:
Menggunakan try-except untuk menangani input yang tidak valid, seperti saat memasukkan nilai yang seharusnya berupa angka.

4. Pengulangan Program:
Menggunakan while True agar program terus berjalan sampai pengguna memilih opsi untuk keluar.

# Output
# Fungsi Tambah
```
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 1
Masukkan nama mahasiswa: vito
Masukkan nilai mahasiswa: 9
data vito berhasil di tambahkan
```

# Fungsi Tampilkan
```
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 2
Daftar Nilai Mahasiswa
1. Nama: vito
   Nilai: 9.0
```

# Fungsi Hapus
```
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 3
Masukan Nama Yang Ingin Di Hapus: vito
Data vito Mahaiswa Berhasil Di Hapus
```

# Fungsi Ubah
```
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 4
Masukan Nama Mahasiswa Yang Ingin Di Ubah Nilainya: vito
Masukan Nilai Baru: 8
Data vito Berhasil Di Ubah
```

# Fungsi Keluar
```
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 5
Program telas Selesai, Terima Kasih
```


