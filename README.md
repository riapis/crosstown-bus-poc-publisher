> Fari Hafizh Ramadhan - 2206083691

# Modul 8: Software Architecture pt 1

1. Try to answer the following questions, and write the answer in the and new file readme.md in
   you repository.  
   a. How many data your publisher program will send to the message broker in one run?
   <br>Setiap kali program dijalankan, akan ada pengiriman 5 data ke message broker. Ini terlihat dari jumlah perintah
   `_ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "1".to_owned(), user_name:
   "2206825965-Amir".to_owned() });` yang ada dalam program. <br><br>
   b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
   <br> URL itu adalah pintu masuk kita ke message broker. Jadi, kalau URL di publisher sama dengan URL di subscriber,
   berarti keduanya terhubung ke server yang sama untuk saling mengirim pesan. Tujuannya adalah untuk memastikan bahwa pesan
   yang dikirim oleh publisher bisa diterima dan diolah oleh subscriber.<br><br>

2. Running RabbitMQ as message broker
   ![rabbitmq.png](img/rabbitmq-overview.png)<br><br>

3. Sending and processing event
![cargorun-publisher](img/cargorun-publisher.png)
![cargorun-subscriber](img/cargorun-subscriber.png)
   Kedua gambar tersebut adalah hasil setelah saya melakukan perintah cargo run pada subscriber dan publisher. Publisher 
akan mengirim 5 event kepada message broker yang kemudian event tersebut akan diterima dan diproses oleh subscriber ditandai 
dengan output tersebut.<br><br>

4. Monitoring chart based on publisher
   ![rabbitmq.png](img/rabbitmq-chart.png)
   Pada gambar tersebut, terlihat bahwa terdapat spike pada grafik message rates last minute ketika saya menjalankan 
instruksi cargo run pada publisher directory. Spike pada grafik message rates last minute menunjukkan jumlah message 
yang diterima oleh subscriber pada 1 menit terakhir.