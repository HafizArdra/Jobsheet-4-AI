# TEKNIK PENCARIAN BLIND SEARCH

# 1. Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7.

Algoritma BFS dimulai dengan node awal, yang dalam kasus ini adalah node 3 (n3), dan ini menjadi titik awal yang diteruskan ke metode BFS(n3). Dalam langkah awal, seluruh node dalam graf diinisialisasi dengan status warna putih (WHITE), kecuali node awal (n3), yang diberi warna abu-abu (GRAY) untuk menandakan bahwa sedang dalam proses.
Node awal (n3) memiliki jarak awal (distance) yang disetel ke 0. Selanjutnya, semua node yang langsung terhubung dengan node awal (n3), yaitu node 2 (n2) dan node 4 (n4), dimasukkan ke dalam antrian (queue) untuk diproses pada tahap berikutnya.

Algoritma BFS akan terus melakukan iterasi selama antrian belum kosong. Ketika sebuah node sedang diproses, warnanya berubah menjadi abu-abu (GRAY) untuk menandakan bahwa sedang dalam proses. Node-node ini kemudian diperiksa untuk menemukan node-node terhubung lainnya.

Node 2 (n2) dan node 4 (n4) adalah node-node putih (WHITE) karena belum diproses. Algoritma BFS akan mengubah warna node 2 (n2) dan node 4 (n4) menjadi abu-abu (GRAY), menghitung jarak dari node awal (n3), dan mengatur node 3 (n3) sebagai pendahulunya.

Contohnya, node 2 (n2) akan memiliki jarak 1 dari node awal (n3), dan node 4 (n4) juga akan memiliki jarak 1 dari node awal (n3). Kemudian, node-node ini ditambahkan ke antrian (queue) untuk diproses pada langkah selanjutnya.

Algoritma akan terus berlanjut dengan mengambil node-node dari antrian yang berikutnya untuk diproses. Setiap kali sebuah node selesai diproses, warnanya akan berubah menjadi hitam (BLACK) untuk menunjukkan bahwa telah selesai diproses.

Hasil dari algoritma BFS adalah pencarian jarak terpendek dari node awal (n3) ke semua node lain dalam graf, serta pengaturan node pendahulu untuk setiap node. Dengan informasi ini, Anda dapat menentukan jarak dari node awal (n3) ke node 8 (n8), node 6 (n6), dan node 7 (n7) dengan mengikuti jalur terpendek. Misalnya, untuk mencari jarak dari n3 ke n8, Anda dapat mengikuti path dari n3 ke n4 (jarak 1), kemudian dari n4 ke n6 (jarak 1), dan akhirnya dari n6 ke n8 (jarak 1), sehingga jarak total dari n3 ke n8 adalah 3. Hal yang sama berlaku untuk mencari jarak dari n3 ke n7.

# 2. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5.

Pertama kita ubah pada bagian static void nya menjadi seperti berikut

        public static void main(String[] args)

    {
        BS graph = new BS();
        Node n0 = new Node(0);
        Node n1 = new Node(1);
        Node n2 = new Node(2);
        Node n3 = new Node(3);
        Node n4 = new Node(4);
        Node n5 = new Node(5);
        Node n6 = new Node(6);
        
        
        
        // Ganti graph dan edge sesuai dengan yang diinginkan
        graph.addEdge(n0, n1);
        graph.addEdge(n0, n2);
       
        graph.addEdge(n1, n0);
        graph.addEdge(n1, n3);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n0);
        graph.addEdge(n2, n5);
        graph.addEdge(n2, n6);
       
        graph.addEdge(n3, n1);
        graph.addEdge(n3, n4);

        graph.addEdge(n4, n3);
        graph.addEdge(n4, n1);

        graph.addEdge(n5, n2);
        graph.addEdge(n5, n6);
        graph.addEdge(n5, n1);

        graph.addEdge(n6, n2);
        graph.addEdge(n6, n5);
        graph.addEdge(n6, n1);
        
        graph.bfs(n0);
    }

outputnya (0,d=0) (1,d=1) (2,d=1) (3,d=2) (4,d=2) (5,d=2) (6,d=2) 

Langkah-langkah BFS menemukan kode node 5 dapat dilakukan dengan cara dalam algoritma BFS, kita memulai dengan sebuah node awal, lalu memasukkannya ke dalam antrian. Selanjutnya, kita melakukan pengecekan apakah node yang kita cari, dalam hal ini node 5, ada di dalam antrian. Pada tahap awal, node 5 belum ditemukan, sehingga kita melanjutkan dengan mengeluarkan node awal dari antrian dan memeriksa node-node tetangganya yang belum dikunjungi. Kita terus mengulang proses ini, yaitu memeriksa node yang ada di dalam antrian, mengeluarkannya, dan memeriksa node-node tetangganya yang belum dikunjungi. Ketika node 5 akhirnya ditemukan dalam antrian, maka pencarian selesai. Hal ini menunjukkan bahwa algoritma BFS telah berhasil menemukan node 5 dalam graf.

# 3. Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.6 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9.

Pertama kita ubah static void nya menjadi seperti berikut

    public static void main(String[] args)

    {
        BS2 graph = new BS2();
        Node n1 = new Node(1);
        Node n2 = new Node(2);
        Node n3 = new Node(3);
        Node n4 = new Node(4);
        Node n5 = new Node(5);
        Node n6 = new Node(6);
        Node n7 = new Node(7);
        Node n8 = new Node(8);
        Node n9 = new Node(9);
        Node n10 = new Node(10);
        Node n11 = new Node(11);
        Node n12 = new Node(12);

        graph.addEdge(n1, n2);
        graph.addEdge(n1, n3);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n1);
        graph.addEdge(n2, n5);
        graph.addEdge(n2, n6);
        
        graph.addEdge(n3, n1);
        
        graph.addEdge(n4, n1);
        graph.addEdge(n4, n7);
        graph.addEdge(n4, n8);
        
        graph.addEdge(n5, n2);
        graph.addEdge(n5, n9);
        graph.addEdge(n5, n10);
        graph.addEdge(n5, n6);
        
        graph.addEdge(n6, n2);
        graph.addEdge(n6, n5);
        
        
        graph.addEdge(n7, n4);
        graph.addEdge(n7, n11);
        graph.addEdge(n7, n12);
        graph.addEdge(n7, n8);
        
        graph.addEdge(n8, n4);
        graph.addEdge(n8, n7);

        graph.addEdge(n9, n5);
        graph.addEdge(n9, n10);

        graph.addEdge(n10, n5);
        graph.addEdge(n10, n9);

        graph.addEdge(n11, n7);
        graph.addEdge(n11, n12);

        graph.addEdge(n12, n7);
        graph.addEdge(n12, n11);
        
        graph.bfs(n1);
    }

outputnya (1,d=0) (2,d=1) (3,d=1) (4,d=1) (5,d=2) (6,d=2) (7,d=2) (8,d=2) (9,d=3) (10,d=3) (11,d=3) (12,d=3)

Langkah-langkah di atas menggambarkan bagaimana algoritma BFS berfungsi dalam menemukan node 9 dalam graf. Proses dimulai dengan memasukkan node awal, yaitu node 1, ke dalam antrian. Kemudian, kita melakukan pengecekan apakah node 9 sudah ada di dalam antrian pada tahap awal, dan pada saat itu, node 9 belum ditemukan.

Setelah itu, node 1 dikeluarkan dari antrian, dan kita melanjutkan dengan memeriksa node-node tetangganya yang belum dikunjungi, yaitu node 2, 3, dan 4. Node-node ini kemudian dimasukkan ke dalam antrian.

Proses berlanjut dengan pengecekan kembali apakah node 9 ada di dalam antrian, yang pada tahap itu masih belum ditemukan. Node 2 kemudian dikeluarkan dari antrian, dan kita menjelajahi node-node tetangganya yang belum dikunjungi, yaitu node 5 dan 6, yang kemudian dimasukkan ke dalam antrian.

Pengecekan terus berlanjut, dan saat kita memeriksa node 5, kita menemukan bahwa node 9 adalah tetangga dari node 5. Inilah saat ketika pencarian berakhir, dan kita dapat menyimpulkan bahwa node 9 telah ditemukan dalam graf.

Algoritma BFS secara sistematis mengeksplorasi graf dan mengelola antrian untuk mencapai tujuan pencarian. Dengan penambahan beberapa kalimat, kita dapat lebih jelas memahami bagaimana algoritma ini bekerja secara berurutan dan akhirnya mencapai hasil yang diinginkan.

# 4. Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 4.7 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C.

Pertama ubah static void nya menjadi seperti berikut

    public static void main(String[] args)

    {
        BS3 graph = new BS3();
        Node n1 = new Node('A');
        Node n2 = new Node('B');
        Node n3 = new Node('C');
        Node n4 = new Node('D');
        Node n5 = new Node('E');
        Node n6 = new Node('F');
        Node n7 = new Node('G');
        Node n8 = new Node('H');
        Node n9 = new Node('I');
        
        graph.addEdge(n1, n2);
        graph.addEdge(n1, n4);

        graph.addEdge(n2, n6);
        graph.addEdge(n2, n1);
        graph.addEdge(n2, n4);
        
        graph.addEdge(n3, n4);
        graph.addEdge(n3, n5);
        
        graph.addEdge(n4, n2);
        graph.addEdge(n4, n3);
        graph.addEdge(n4, n5);
        
        
        graph.addEdge(n5, n4);
        graph.addEdge(n5, n3);
        
        
        graph.addEdge(n6, n2);
        graph.addEdge(n6, n7);
       
        
        
        graph.addEdge(n7, n6);
        graph.addEdge(n7, n9);
        
        graph.addEdge(n8, n9);
        
        graph.addEdge(n9, n8);
        
        graph.bfs(n6);
    }

 Pada bagian yang bertuliskan int data yaitu pada public class dan public Node diganti karena kita menggunakan huruf bukan angka

    public class BS3 {
      public enum NodeColour {
          WHITE, GRAY, BLACK
      }

      public static class Node {
          char data;
          int distance;
          Node predecessor;
          NodeColour colour;

      public Node(char data)

      {
        this.data = data;
      }

        public String toString() {
            return "(" + data + ",d=" + distance + ")";
        }
      }

outputnya (F,d=0) (B,d=1) (G,d=1) (A,d=2) (D,d=2) (I,d=2) (C,d=3) (E,d=3) (H,d=3) 

Dalam urutan yang disebutkan, algoritma BFS berhasil menemukan node C dalam graf. Awalnya, node F dimasukkan ke dalam antrian, dan kemudian dilakukan pengecekan apakah node C sudah ada dalam antrian. Pada tahap awal, node C belum ditemukan.

Node F kemudian dikeluarkan dari antrian, dan langkah selanjutnya adalah memeriksa node-node tetangganya yang belum dikunjungi, yaitu node B dan G. Node B dan G kemudian dimasukkan ke dalam antrian.

Proses ini berlanjut, dan ketika node B dikeluarkan dari antrian, kita mengeksplorasi node-node tetangganya yang belum dikunjungi, yaitu node A dan D. Node A dan D kemudian dimasukkan ke dalam antrian.

Selanjutnya, node A dikeluarkan dari antrian, dan kita mengecek node-node tetangganya yang belum dikunjungi. Pada tahap ini, tidak ada node tetangga yang belum dikunjungi, sehingga proses berlanjut.

Kemudian, node D dikeluarkan dari antrian, dan kita menjelajahi node-node tetangganya yang belum dikunjungi, yaitu node C dan E. Pada saat itu, kita menemukan node C dalam antrian.

Hal ini menunjukkan bahwa algoritma BFS berhasil menemukan node C, dan pencarian berakhir. Algoritma BFS dengan cara yang sistematis menjelajahi graf dan mengelola antrian untuk mencapai tujuan pencarian. Dengan penambahan beberapa kalimat, kita dapat lebih jelas memahami bagaimana algoritma ini beroperasi dan mencapai hasil yang diinginkan.
