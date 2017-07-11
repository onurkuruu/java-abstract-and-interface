### Abstract Anahtar Kelimesi ve Interface

**Java**’da kullanıcıları arka plan işlerinden **soyutlamak, geliştirilebilir, düzenli yapılar** kurmak için bu yazılım birimlerini oldukça fazla kullanırız. Kodlarımızı bunlar olmadan da yazabiliriz fakat, özellikle büyük projelerde kodlarımız zamanla karmaşık bir hal alır.

### Abstract Anahtar Kelimesi

Abstract anahtar kelimesi:

* **Sınıflar**
* **Metotlar** için kullanılır.

#### Abstract Sınıflar

**Abstract** kelimesini sınıflarımıza eklediğimiz zaman sınıflar artık **soyutlanmış** olur. Bu sınıfların nesnelerini oluşturamayız. Diğer sınıflar tarafından **extends** ile kalıtım alınması gerekmektedir. Kurucu fonksiyonları vardır. **Normal, final, static** değişkenler, main metodu içerebilir. **Final** metot içeremezler.

```java
abstract class A {

    private String var1;
    private final String var2;
    private static String var3;

    A() {
        var2 = "";
    }

    public void func1() {
        System.out.println("");
    }
}
```

#### Abstract Metotlar

**Abstract** kelimesi ile tanımlanmış fonksiyonlar soyutlanmış olur. Metotun gövdesi olmaz. Kalıtım alan sınıfın **override** etmesi gerektiği belirtilir. Sadece **abstract sınıflar ve interfaceler** içerisinde kullanılır.

```java
abstract class A {
    abstract void func1();

    abstract void func2();
}

class B extends A {

    @Override
    void func1() {
        System.out.println("Function 1");
    }

    @Override
    void func2() {
        System.out.println("Function 2");
    }
}
```

### Interface(JAVA 8’den önce)

**Interfaceler** taslak oluşturmamıza yarayan yapılardır. Abstract sınıfların maksimum soyutluk sağlanmış halidir diyebilir. Nesneleri oluşturulamaz. **Final static** değişkenler içerebilir. İçerisindeki metotlar **private** yada **final** olamaz. 

Interfaceler kullanılarak **soyutluk, loose coupling, çoklu kalıtım** işlemleri sağlanabilir. Java sınıfları tarafından **implements** anahtar kelimesi ile kullanılır. Diğer interfaceleri **extends** anahtar kelimesi ile kalıtım alabilir. Interfaceler arasında **çoktu kalıtım** olabilir.

```java
 interface A {
    void func1();
}

interface B {
    void func2();
}

interface C extends A, B {
    void func3();
}
```

İçerisinde sabit ya da metot bulundurmayan interfaceler **işaretlenmiş interface** olarak bilinir ve **JVM**’ye bazı istatistikleri sağlamada yardımcı olur(Örneğin; Serializable, Remote vb.).

Derleme zamanında interface içerisinde ki sabitlere **final static** anahtar kelimeleri, aynı şekilde metotlara da **abstract** anahtar kelimesi eklenir.

### Abstcract Sınıflar ve Interface(Java 8’den önce)
* Abstract sınıfta abstract ya da abstract  olmayan metotlar bulunabilir. Interfacede tüm metotlar abstracttır.
* Abstract çoklu kalıtımı desteklemez, interface destekler.
* Abstract sınıfta final, static ya da normal değişken olabilir interface sadece final static değişken içerir.
* Abstract sınıfların soyutluk derecesi 0-100 arasında iken interfacenin 100 dür. 
