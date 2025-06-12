# Detekcija QRS kompleksa u EKG signalu pomoću STFT

## EKG signal
Elektrokardiogram (EKG) je grafički prikaz električne aktivnosti srca detektovane korišćenjem elektroda koje se postavljaju na kožu pacijenta. Za električni signal koji ove elektrode detektuju koristićemo termin EKG signal.
Na Slici 1 je prikazan jedan primjer EKG signala na kojem vidimo da se on sastoji iz nekoliko karakterističnih talasnih oblika koji se kvaziperiodično ponavljaju.

Najkarakterističniji talasni oblik u EKG-u je QRS kompleks. On odražava električnu aktivnost srca tokom kontrakcije komora, pa trenuci u kojima se pojavljuje i njegov oblik daju značajne informacije o stanju u kojem se srce nalazi. Na Slici 2 je prikazan primjer QRS kompleksa na kojem su označeni njegovi karakteristični dijelovi (Q-, R- i S-talasi), kao i talasni oblici koji mu prethode i slijede ga, P- i T-talasi.
P talas, QRS kompleks i T talas čine jedan srčani ciklus. Detekcija QRS kompleksa je osnova svih algoritama za automatsku analizu EKG-a.

## Detekcija QRS kompleksa
Intuitivno, QRS-kompleks je moguće detektovati detekcijom vršnih vrijednosti koje odgovaraju vrhu R-talasa. Međutim, zbog prisustva šuma i postojanja varijacija u obliku EKG-a u kojima vrh R-talasa nije dominantan, kao što je, na primjer, invertovani QRS-kompleks, bolje je detekciju bazirati na činjenici da R-talas predstavlja naglu promjenu vrijednosti EKG signala.

Nagle promjene impulsnog oblika se lako uočavaju kao širokopojasni porast energije u vremensko-frekvencijskoj reprezentaciji signala. Zbog toga za detekciju QRS-kompleksa možemo koristiti sistem prikazan blok-dijagramom.

<img src="https://github.com/donsale/ecg/blob/main/blok-dijagram.PNG" width="400" height="auto">
