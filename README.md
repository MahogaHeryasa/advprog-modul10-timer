# advprog-modul10-timer

# Mahoga Aribowo Heryasa

# 2206025230

### Experiment 1.2: Understanding how it works

![Experiment 1.2: Understanding how it works](assets/images/Experimet%201.2.png)

Berdasarkan hasil dari `cargo run`, *print statement* "hey hey" muncul terlebih dahulu sebelum "howdy!" dan "done!". Hal ini terjadi karena *print statement* "hey hey" tidak diletakkan pada *asynchronous task spawner* , melainkan diletakkan pada fungsi `main` sebelum fungsi `executor.run()`. Hal ini menunjukan bahwa `spawner.spawn(async {...});` tidak akan *execute* *task*-nya sebelum *executor*-nya di *run*.  


### Experiment 1.3: Multiple Spawn and removing drop

![Experiment 1.3: Multiple Spawn and removing drop](assets/images/Experiment%201.3.png)

![Experiment 1.3 (2): Multiple Spawn and removing drop](assets/images/Experiment%201.3.2.png)

Berdasarkan kedua percobaan yang saya lakukan, terlihat bahwa *order* dari ekseskui *task*-nya tidak teratur dan bergantung pada *scheduling algorithm executor*, sehingga pada kedua percobaan urutannya random dan tidak konsisten. Hal yang mungkin saja terjadi adalah eksekusi dilakukan dengan *order* yang semestinya namun pesan tidak selalu di *print* secara teratur. Karena spawner menggunakan resource untuk setiap kali membuat *task*, ketika proses pembuatan dibuat sangat banyak tentunnya program akan berjalan lebih lama serta executor akan kesulitan untuk me-*manage* *task*-nya. Selain itu, terlihat bahwa program tidak stop, hal ini terjadi karena pengapusan fungsi `drop` yang menyebabkan tidak ada perintah yang memberitahu *executor* bahwa tidak ada *task* yang ditambahkan pada *queue*.      