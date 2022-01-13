### 1. NodeJS ile server ayağa kaldırmak
```
let  http = require('http');     // http modulü import edildi
const  server = http.createServer(function (req, res) {     // server oluşturuldu
res.write('Hello World!');
res.end();
})

server.listen(3000, () => {        // server localhost:3000'de ayağa kaldırıldı 
console.log("Server Ayağa kaldırıldı!")
})

```

### 2. NodeJS ve Express kullanarak server ayağa kaldırmak
Terminalde `npm i express` komutu kullanılarak express modülü indirilir ve kurulur.
```
const express = require("express");  // express modülü import edildi
const app = express();               // express modülü app'e atandı

const port = 3000;   // server'in ayağa kaldırılacağı port atandı

app.get("/), (req, res) => {   // localhost:3000'e gelen GET isteği
res.send("Merhaba!")
})

app.listen(port, () => {     // server localhost:3000'de ayağa kaldırıldı
console.log(`Server ${port} portunda ayağa kaldırıldı`)
})
```

## JavaScript ve TypeScript farkları

JavaScript dinamik yapısı sebebiyle kod çalıştırılana kadar hata ayıklama (debugging) yapılamıyor. Küçük projelerde herhangi bir sorun yaratmasa da büyük projelerde kod bloklarını büyümesi sonucunda hata ayıklama daha zor bir duruma geliyor. Büyük projeler için gerekli olan tipler, sınıflar, arayüzler gibi yapılar JavaScript'te yer almıyordu.
TypeScript ise Microsoft tarafından geliştirilen açık kaynak ve nesne yönelimli bir programlama dilidir. Büyük projelerde hata ayıklamayı kod derlemesinden önce yapmaya yarayan dildir. Örnek vermek gerekirse; 

### JavaScript kod örneği
```
const getFullName = (isim, soyIsim) => isim + soyIsim;

getFullName(1,2); // 3
getFullName("Mehmet", "Yüksel"); // MehmetYüksel 
getFullName(); NaN

```
Yukarıdaki kodda JavaScript herhangi bir uyarı vermeyecek ve çıktıyı ancak kod çalıştırıldıktan sonra göreceğiz. Küçük çaplı projelerde sorun yaratmasa bile büyük çaplı projelerde bu hata ayıklamasını yapmak kolay olmayacaktır.

### TypeScript kod örneği
```
const  getFullName = (isim :string, soyIsim: string) =>  isim + soyIsim;

console.log(getFullName(1,2)); // Type hata uyarısı verir
console.log(getFullName("Mehmet", "Yüksel")); // MehmetYüksel
console.log(getFullName()); // Beklenen argüman olduğu uyarısını verir

```
Yukarıdaki TypeScript kod bloğunda ise daha fonksiyonu yazarken gerekli uyarılar alınacağı için herhangi bir beklenmedik çıktı oluşmayacaktır. JavaScript dosyalarının uzantıları .js, TypeScript dosyalarının uzantısı ise .ts'dir.
