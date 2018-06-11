# java_KHTN
```java
package thucHanh;

import java.util.Scanner;

public class BtapBietLe3 {

	//Ham doc 1 so
	private static String doc1So(int so) {
		switch(so) {
		case 0:
			return "khong";
		case 1:
			return "mot";
		case 2:
			return "hai";
		case 3:
			return "ba";
		case 4:
			return "bon";
		case 5:
			return "nam";
		case 6:
			return "sau";
		case 7:
			return "bay";
		case 8:
			return "tam";
		case 9:
			return "chin";
		default:
			return "khong biet";
		}
	}
	//ham doc 3 so
	private static String doc3So(int so) {
		int ht,hc,hd;
		//so = 123
		ht = so/100;	//1
		hc = so%100/10; //2
		hd = so%100%10;	//3
		if(ht==0)	
			if(hc==0)
				return doc1So(hd);
			else if(hd!=0)	//đọc số có 2 chữ số màng hàng đơn vị khác 0
			{
				return doc1So(hc) + " muoi "+ doc1So(hd);
			}
			else	//đoc số có 2 chữ số mà hàng đơn vị bằng 0
			{
				return doc1So(hc) + " muoi";
			}
		else if(hc!=0&&hd!=0)	//đọc số có 3 chữ số mà hàng chục và đơn vị khắc 0
		{
			return doc1So(ht) + " tram " + doc1So(hc) + " muoi "+ doc1So(hd);		
		}
		else if(hc==0&&hd!=0)	//đọc só có 3 chữ số mà hàng chục = 0 nhưng hàng đơn vị khác 0
		{
			return doc1So(ht) + " tram le " + doc1So(hd);
		}
		else					//đọc số có 3 chữ số mà hàng chục và đơn vị =0
		{
			return doc1So(ht) + " tram";
		}
	}
	//Ham main
	public static void main(String[] args) {
		int so=0;
		do {
			Scanner scan = new Scanner(System.in);
			System.out.print("Nhap 1 so (0-999): ");
			try {
				so = scan.nextInt();
			}catch(Exception ex) {
				System.out.println("\tSo nhap khong hop kieu\n");
				continue;
			}
			if(so<0||so>999)
				System.out.println("\tSo nhap phai tu 0 den 9\n");
		}
		while(so<0||so>999);
		System.out.println("Chu so la: "+doc3So(so));
	}
}
```
