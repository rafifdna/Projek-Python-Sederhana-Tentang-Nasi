# Projek-Python-Sederhana-Tentang-Nasi
from abc import ABC, abstractmethod

class Makanan():
    # class variable
    __jumlah = 0

    def __init__(self, nama, asal):
        self.nama = nama
        self.asal = asal
        Makanan.__jumlah += 1

    # penggunaan decorator classmethod
    # pada decorator classmethod bisa menambahkan parameter
    @classmethod
    def getJumlah(cls):
        return Makanan.__jumlah


Nasgor = Makanan("Nasi Goreng", "Asia")
Uduk = Makanan("Nasi Uduk", "Asia Tenggara")
Kebuli = Makanan("Nasi Kebuli", "Timur Tengah")
print(Makanan.getJumlah()) 
print(Nasgor.getJumlah())
print(Uduk.getJumlah())
print(Kebuli.getJumlah())
print("")
print("==========================================")
print("")

class Nasi(ABC): #class abstrak

    def tampilan(self):
        print("Nasi putih")
        print("Nasi putih memiliki tampilan seperti nasi pada umumnya.")
        pass
  
    def rasa(self):
        print("Memiliki sedikit rasa manis.")
        print("")
        pass

class Nasgor(Nasi):

    def tampilan(self):
        print("Nasi goreng")
        print("Nasi goreng biasanya memiliki tampilan berwarna merah kecoklatan apabila menggunakan kecap.")
  
    def rasa(self):
        print("Nasi goreng memiliki rasa pedas yang enak.")
        print("")
  
class Uduk(Nasi):

    def tampilan(self):
        print("Nasi uduk")
        print("Nasi uduk memiliki tampilan seperti putih biasa.")
  
    def rasa(self):
        print("Rasanya memiliki aroma seperti santan.")
        print("")

class Kebuli(Nasi):

    def tampilan(self):
        print("Nasi kebuli")
        print("Nasi kebuli memiliki bentuk nasi yang lebih besar dibandingkan nasi biasa.")
  
    def rasa(self):
        print("Rasanya sangat enak jika dimakan dengan daging kambing.")
        print("")
  
obj_nasigoreng = Nasgor()
obj_nasiuduk = Uduk()
obj_nasikebuli = Kebuli()
for makanan in (obj_nasigoreng, obj_nasiuduk, obj_nasikebuli):
    makanan.tampilan()
    makanan.rasa()

# Driver code untuk kelas abstrak
R = Nasgor()
R.tampilan()
R.rasa()
 
K = Uduk()
K.tampilan()
K.rasa()
 
R = Kebuli()
R.tampilan()
R.rasa()
