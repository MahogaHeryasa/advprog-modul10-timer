# advprog-modul10-timer

# Mahoga Aribowo Heryasa

# 2206025230

### Experiment 1.2: Understanding how it works

![Experiment 1.2: Understanding how it works](assets/images/Experimet%201.2.png)

Berdasarkan hasil dari `cargo run`, *print statement* "hey hey" muncul terlebih dahulu sebelum "howdy!" dan "done!". Hal ini terjadi karena *print statement* "hey hey" tidak diletakkan pada *asynchronous task spawner* , melainkan diletakkan pada fungsi `main` sebelum fungsi `executor.run()`. Hal ini menunjukan bahwa `spawner.spawn(async {...});` tidak akan *execute* *task*-nya sebelum *executor*-nya di *run*.  