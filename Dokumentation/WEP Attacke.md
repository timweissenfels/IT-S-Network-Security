# WEP Attacke (Challenge-Response Authentifizierung)

Wie eben schon erwähnt ist die Shared-Key-Authentification nicht sicher und gibt Informationen preis. Da wir es mit einer Challenge-Response Authentifizierung zu tun haben, spielt sich das ganze folgendermaßen ab: Der Server schickt als erstes dem Client die Challenge1, beziehungsweise eine Zufallszahl. Danach versucht der Client diese Zahl zu verschlüsseln und schickt das WEP-Paket(IV1+ Cipherntext1) zurück an den Server. Danach kann der Angreifer die Informationen erlangen und zwar die IV1+ Cipherntext1 und Challenge1. Der Angreifer kann dann mittels XOR den Keystream1 errechnen. Hat der Angreifer nun den Keystream1 und IV1 kann er sich selber versuchen zu authentifizieren. Eine Challenge2 wird nun vom Server geschickt. Beantwortet wird sie mit einem WEP-Paket bestehend aus IV1 und Ciphertext2. Ciphertext2 besteht aus Challenge2 und dem Keystream1. Dies wird dann an den Server geschickt und wird nun erfolgreich authentifiziert.