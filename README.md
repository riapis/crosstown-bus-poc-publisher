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
