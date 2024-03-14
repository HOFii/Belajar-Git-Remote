GIT REMOTE

1.Poin-Poin Utama:

A. Apa itu Git Remote

    adalah perintah dalam Git yang digunakan untuk menampilkan daftar remote yang terhubung ke repositori 
    lokal Anda. Remote adalah salinan repositori Git yang berada di tempat yang berbeda, seperti server 
    atau platform hosting kode seperti GitHub, GitLab, atau Bitbucket. Remote memungkinkan Anda untuk 
    berkolaborasi dengan anggota tim dan menyimpan perubahan proyek secara terpusat. Server Git menyimpan 
    repositori dan mendukung berbagai mekanisme komunikasi, termasuk HTTP/HTTPS dan SSH.

B. SSH (Secure Shell)

    1.) SSH (Secure Shell) direkomendasikan untuk komunikasi dengan server Git karena manfaat keamanannya. 
    Pengguna perlu membuat kunci SSH untuk autentikasi, yang terdiri dari private key (disimpan secara lokal) 
    dan public key (dibagikan dengan server Git). Menambahkan kunci publik SSH ke pengaturan server Git 
    memungkinkan autentikasi yang mulus tanpa memasukkan kata sandi. 
    2.) Sebelum menggunakan SHH anda perlu membuat SSH Key, yang merupakan kunci autentikasi ke SSH server,
    anda perlu menuliskan perintah "ssh-keygen" di terminal, jika sudah secara default terdapat dua key
    dilokal kita yaitu private key dan public key.
    
C. Remote Repository

    1.) Anda bisa menambahkan remote repository dengan menggunakan perintah "git remote add nama ssh-url".
    2.) Anda juga bisa melihat remote repository dengan menggunakan perintah "git remote", dan untuk melihat 
    lebih detail bisa menggunakan perintah "git remote get-url nama".
    3.) Dan anda juga bisa menghapus remote repository dengan menggunakan perintah "git remote rm nama".
    
D. PUSH

    1.) Untuk mengirim perubahan ke remote repository dengan nama branch yang sama dengan menggunakan perintah
    "git push namaremote localbranch".
    2.) Dan untuk mengirim perubahan branch ke remote repository dengan nama branch yang berbeda bisa menggunakan 
    perintah "git push namaremote localbranchl:remotebranch".
    3.) Anda juga bisa mengirim semuanya sekaligus ke branch remote repository anda, dengan menggunakan perintah
    "git push origin --all".
    4. Bisa juga untuk menghapus branch yang ada didalam remote repository anda, dengan menggunakan perintah 
    "git push --delete namaremote namabranch".
    
E. Clone

    Perintah clone digunakan ketika anda ingin mendownload project Git yang ada di server ke device baru,
    dengan melakukan perintah "git clone urlremotereporitory". Secara default akan membuat folder dengan nama
    yang sama dengan nama project yang ada di repository. Dan jika anda ingin melakukan clone dengan nama folder 
    yang berbeda anda bisa menggunakan perintah "git clone urlremoterepository namafolder".
    
F. Remote Branch

    Secara default, saat melakukan clone, tidak semua remote branch akan dibuat di local storage git project.
    Jika anda ingin melihat semua daftar branch yang ada di remote repository bisa menggunakan perintah
    "git branch -r". Atau jika ingin melihat semua branch dilocal dan remote bisa menggunakan perintah
    "git branch -a".
    
    1.) Anda juga bisa membuat branch dari remote branch yang lain dengan mengambil datanya, menggunakan perintah 
    "git checkout -b localbranch namaremote/remotebranch".
    
G. Fetch 

    Fetch digunakan untuk mendapatkan perubahan terakhir di remote repository. Bisa menggunakan perintah
    "git fetch namaremote" atau jika anda ingin melakukan fetch pada branch tertentu bisa menggunakan perintah
    "git fetch namaremote remotebranch".
    
H. Pull

    Perintah Pull digunakan untuk mengambil perubahan pada remote repository dan dsimpan di local repository,
    dan sifatnya berbeda dengan Fetch yang hanya mendapatkan perubahan tanpa mengubah di local repository.
    Anda bisa menggunakan perintah "git pull namaremote namaremotebranch".
    
I. Tag 

    1.) Saat melakukan push ke remote repository, data Tag tidak akan ikut ke push, jadi anda harus mengirim
    data Tag juga, jika memang dioerlukan dan bisa menggunaka perintah "git push namaremote namatag" atau 
    jika ingin mengirim semua Tag ke remote repository bisa menggunakan perintah "git push namaremote --tags".
    
    2.) Anda juga bisa mengambil Tag dengan menggunakan perintah "git fetch namaremote namatag" atua jika ingin
    mengambil semua tag bisa menggunakan "git fetch namaremote".
    
    3.) Dan bisa juga menghapus Tag di local repository dengan menggunakan perintah "git push --delete
    namaremote namatag" Perlu diingat ini hanya akan menghapus Tag di local repository bukan di
    remote repository.
    
J. Pull Request

    Memungkinkan kolaborasi dan peninjauan perubahan kode sebelum menggabungkannya ke dalam 
    branch utama. Pull request dapat dibuat dan dikelola menggunakan platform seperti GitHub, yang 
    memfasilitasi peninjauan dan kolaborasi kode. Pull request dapat digabungkan setelah ditinjau 
    dan disetujui, mengintegrasikan perubahan ke dalam cabang utama. 
    
K. Merge Conflik

    Merge conflict dapat muncul dalam pull request ketika perubahan bertentangan dengan kode yang ada di 
    target branch. Menyelesaikan konflik membutuhkan intervensi manual untuk merekonsiliasi perbedaan 
    sebelum menggabungkan pull request. Membenarkan merge konfil bisa dilakukan didalam text editor seperti
    VSCODE, SublimeText dll. Merge conflict dapat muncul ketika membuat pull request, biasanya karena
    perubahan pada basis kode yang sama.

    
L. Submodule

    1.) Submodule berguna untuk menyertakan repository eksternal di dalam sebuah project, sehingga memungkinkan
    pengelolaan kode eksternal secara terpisah saat mengaksesnya di dalam project utama. Submodule
    memfasilitasi pembagian kode di antara beberapa project, memastikan konsistensi dan kemudahan 
    pembaruan di seluruh project. Menambahkan submodule melibatkan penentuan URL submodule dan folder
    tempat penyimpanannya di dalam project. Submodule secara otomatis dikloning ke dalam folder yang 
    ditentukan dan ditautkan ke repositori project.
    
    2.) Untuk menambahkan Submodule bisa menggunakan perintah "git submodule add urlgitrepo namafolder". 
    Dan saat menambahkan Submodule secara otomatis semua git repository Submodule tersebut akan di clone kedalam 
    folder yag ditentukan. Anda dapat mendeteksinya dari file ".gitmodules".
    
    3.) Didalam folder Submodule anda bisa melakukan management git repository seperti commit, mengelola branch,
    dll. Namun sangat tidak direkomendasikan untuk melakukan perubahan didalam Submodule.
    
    4.) Jika ada perubahan dalam Submodule anda bisa meng-update perubahan dengan melakukan perintah 
    "git submodule update --remoten namafolder". Atau jika ingin meng-update semua Submodule bisa menggunakan
    "git submodule update --remote".
    
    5.) Saat melakukan Clone pada git repository yang didalamnya terdapat Submodule, secara default Submodule 
    nya juga ikut di Clone tapi anda harus mengaktifkannya secara manual menggunakan perintah "git submodule init"
    
    6.) Dan cara menghapus Submodule bisa menghapus folder Submodulenya lalu ubah file ".gitmodules".
    
M. Fork

    1.Forking Workflow adalah hal yang umum dalam project open source, di mana kontributor menduplikasi 
    repository utama, membuat perubahan dalam fork mereka, dan kemudian meminta perubahan tersebut 
    untuk digabungkan ke dalam proyek utama. Forking Workflow memungkinkan kolaborasi sambil mempertahankan 
    kontrol atas repositori utama dan memastikan perubahan ditinjau sebelum integrasi.
    
2. Pertanyaan dan Catatan Tambahan
   
a. -

4. Kesimpulan
   
Dengan git remote memungkinkan untuk para developer bisa mengembagkan perangkat lunak dengan mudah, dan
efisien dan juga bisa berkontribusi dalam pengembangan project lainnya.
