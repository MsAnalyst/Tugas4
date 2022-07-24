# Tugas4
Tujuan Pengerjaan Project: 
Mengelola dan merapikan data yang ada.

Detail/deskripsi task:
Langkah pengerjaan adalah sebagai berikut:
1. Mengimport package pandas --> import pandas as pd
2. Membuat variable dan mengimport file yang akan dikelola --> 
          okt = pd.read_csv("2019-Oct-sample.csv")
          nop = pd.read_csv("2019-Nov-sample.csv")
3. Menampilkan isi variable --> 
          okt.head()
          nop.head()
4. Membuat variable untuk frame atau untuk menampung variable data yang sebelumnya telah dibuat serta menggabungkan variable data tersebut --> 
          frames=[okt,nop]
          result=pd.concat(frames).drop_duplicates().reset_index(drop=True)  
5. Menampilkan frame --> result.head()
6. Membuat variable baru untuk menganalisa --> 
          z=result[['product_id','category_id','category_code','brand','price']]
z
7. Membuat variable baru untuk memfilter dan menampilkan aktivitas pembelian--> 
        filter=result.loc[result["event_type"]=='purchase']
        filter
8. Melakukan splitting namun tidak berhasil karena kendala size limit --> 
     filter[['category','productnm','product_name']]=filter.category_code.str.split(".",expand=True)filter[['category','productnm','product_name']]=filter.category_code.str.split(".",expand=True)

Cara Running/Penggunaan Program:
Untuk menjalankan script ini, maka perlu membuka aplikasi Jupyter lalu membuat file baru dengan extensi file ".ipynb", lalu bisa di-copas script yang ada di Repository ini ataupun didownload. Selain itu bisa juga menggunakan VSCode (extension Python dan Jupyter harus telah dipasang).

Saran Perbaikan: 
Menggunakan file yang lebih sedikit datanya. 

Tambahan: 
Saya menggunakan Python karena saya tidak menggunakan Linux dan saat menggunakan emulator Linux, saya tidak dapat menemukan letak main folder/folder utama dari emulator tersebut. Selain itu, data yang dikelola terlalu besar dan masih kurang paham tentang penggunaan bash/shell. Maka, ada kendala saat splitting kolom.

