#### [English](#topic) / [Turkish](#konu)
# Topic

The purpose of the Design Pattern.

### UML Diagram of Design Pattern
Shows Design Pattern UML Diagram
Simple:

![|Solid](https://raw.githubusercontent.com/incubationhub/jee.oop/master/com.ihub.jee.oop/dp/creational/singleton/images/singleton.PNG)

## Prerequisites

*   Basic Java programming knowledge
*   Basic OOP knowledge

## Scenario

There are different enterprise scenarios related to design patterns. 

## Explanation

Every Design Pattern is clearly explained this part. 

##### Why Design Pattern is used ? 

Explained why design pattern is used.

##### Connector.java
Some sample from code.
```
public class Connector {

    // it is created null when first class is called.
	private static Connector uniqueInstance = null;
	
	private final String hostURL ;
	private final String pathURL ;
	private final String serviceURL;
		
	//the constructor is  defined private because it must not called from outside.
	private Connector () {
		 hostURL = "http://services.odata.org";
		 pathURL = "/V2/Northwind/Northwind.svc/";
		 serviceURL = hostURL + pathURL;
	}

	// Our method to call our class from the outside.
	// Thanks to synchronized keyword is prevented from runnig the method at the same time 
	public synchronized static Connector getInstance () {
		if(uniqueInstance == null) {
			uniqueInstance = new Connector();
		}
		
		return uniqueInstance;		
	}
	...
}
```

##### Main.java
Some sample from code.
```
public class Main {

	public static void main(String[] args) throws IOException {
		//We can reach Singleton Connector Class thanks to getInstance()
		Connector connector = Connector.getInstance();

		//get orders from Northwind.svc
		String orders = connector.getOrders();
		System.out.println(orders);
		
		...
	}

}
```

## Summary

Summary part is consist of all processes related to Design Pattern.

## Links
Benefit from some resources related to Design Pattern.


# Konu

Desing Pattern'lerin çalışma mantığı, neden kullanıldığı ve nerelerde kullandığını bir Java projesi üzerinden açıklanacaktır.

## Gereksinimler

*   Temel Java programlama bilgisi.
*   Başlangıç seviyesinde OOP bilgisi.

## Senaryo

Desing Pattern'leri kurumsal senaryolar oluşturarak anlatılacaktır.

## Açıklama

Her Design Pattern amacı, kullanımı net ve sade bir şekilde anlatılacaktır.

##### Ne zaman bu Design Pattern'i Kullanmalıyız ? 

İlgili Design Pattern'i ne zaman ve hangi durumlarda kullanmamamız gerektiği anlatılacaktır.

##### Connector.java
Projeden bazı kodlar örnek olarak verilecektir.
```
public class Connector {

    //ilk class çağrıldığında null olarak uniqueInstance yaratılacaktır. 
	private static Connector uniqueInstance = null;
	
	private final String hostURL ;
	private final String pathURL ;
	private final String serviceURL;
		
	//Constructor private olmalıdır, dışarıdan çağrılamaması için.
	private Connector () {
		 hostURL = "http://services.odata.org";
		 pathURL = "/V2/Northwind/Northwind.svc/";
		 serviceURL = hostURL + pathURL;
	}

	// Birden fazla instance'i almayı engellemek için kontrol ediliyor.
	//synchronized keyword'u ile de run-time da 2 kere aynı anda yaratılmayı engellemiş oluyoruz. 
	public synchronized static Connector getInstance () {
		if(uniqueInstance == null) {
			uniqueInstance = new Connector();
		}
		
		return uniqueInstance;		
	}
	...
}
```

##### Main.java
Projeden bazı kodlar örnek olarak verilecektir.
```
public class Main {

	public static void main(String[] args) throws IOException {
		//'Main' Classın da singleton olan 'Connector' classının instance'ni alıyoruz.  
		Connector connector = Connector.getInstance();

		//instance'i alınan Connector classının getOrders methodu ile Northwinden Orderları çekiyoruz.
		String orders = connector.getOrders();
		System.out.println(orders);
		
		...
	}

}
```

## Özet

İlgili Pattern'i kullanırken tüm süreçlerini özet şeklinde anlatılan bir kısım olacaktır. 

## Linkler
Design Pattern'i kodlarken yararlanan kaynaklar.

* [Singleton Oracle Java](http://www.oracle.com/technetwork/articles/java/singleton-1577166.html) - Oracle Java Singleton
* [Northwind V2 OData SVC ](http://services.odata.org/V2/Northwind/Northwind.svc/) - Northwind Odata 
