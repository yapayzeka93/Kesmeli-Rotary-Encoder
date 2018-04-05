# Kesmeli-Rotary-Encoder
Bu çalışmada döner bir cismin hareket yönü, tur sayısı ve hızı gibi bilgileri almak için (rotory encode) döner kodlayıcı kullanılacak. Bunun için bir kütüphane oluşturulacaktır. Tüm açıklamalar TÜRKÇE olacak.

Döner kotlayıcılar genellikle 2 çıkışı bulunan cihazlardır. Bu iki çıkıştan birincisi A fazını ikincisi B fazını temsil etmektedir.Toplamda ile 4 olasılıkla bir döngüsel durumu dörte bölmektedirler.

          A Fazı    B Fazı
1. Adım     0        0             Burada 0 lar düşük gerilim seviyesini yani mantıkta ki olumsuzu temsil etmektedir.
2. Adım     1        0           
3. Adım     1        1
4. Adım     0        1

Bundan sonraki adımda sistem başa dönecek ve [0 0] çıktısını verecektir.

Bir diyagram üzerinde incelemek gerekirse.
A Fazı  001100110011
B Fazı  011001100110

A fazının bit değeri ile B fazının bit değerini yanyana koyacak olursak.

          A Fazı    B Fazı   Değer  İstenen   A'B'        Yöntem
1. Adım     0        0         0       0      0 0     A'=B     B'= A özel veya B
2. Adım     1        0         2       1      0 1     A'=B     B'= A özel veya B
3. Adım     1        1         3       2      1 0     A'=B     B'= A özel veya B
4. Adım     0        1         1       3      1 1     A'=B     B'= A özel veya B

Bu durumda 
byte konum;
konum = ((a^b)|b<<1); Burada konumumuzu 0. 1. 2. 3. olarak tesbit edilecektir.

