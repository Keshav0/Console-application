package com.OnlineShop.App;
import java.util.ArrayList;
import java.util.Date;
import java.text.SimpleDateFormat;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class ShoppingAdda {
	static String name=null;
	static ArrayList<Integer> arl1=new ArrayList<Integer>();
	static ArrayList<String> arl2 = new ArrayList<String>();
	static ArrayList<Integer> arl3 = new ArrayList<Integer>();
	static ArrayList<Integer> arl4 = new ArrayList<Integer>();
	static ArrayList<Integer> arl5=new ArrayList<Integer>();
	static int count=0;
	static Scanner sc=new Scanner(System.in);
	public static void main(String[] args) {
		 name=name();
		number();
		home(name);
	}
	static void number() {
		Scanner scn=new Scanner(System.in);
		System.out.println("Enter 10 digit Mobile number");
	String number=scn.next();
	if(number.length()!=10) {
		System.out.println("Enter valid mobile number");
		number();
	}
	try {
	Long.parseLong(number);
	}catch (Exception e) {
		System.out.println("Enter valid mobile number");
		number();
	}
	}
	static String name() {
		Scanner scn=new Scanner(System.in);
		System.out.println("Enter username");
		String nam=scn.nextLine();
		if(nam.length()<4) {
			System.out.println("Enter min four character");
			name();
		}
		return nam;
	}
	static void home(String name) {
		System.out.println("Welcome to Shopping Adda "+name);
		DateTimeFormatter dtf = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");
		   LocalDateTime now = LocalDateTime.now();
		   System.out.println(dtf.format(now));
		   SimpleDateFormat sdf2 = new SimpleDateFormat("EEEE");
			String stringDate2 = sdf2.format(new Date());
			System.out.println("Enjoy "+stringDate2+" dhamaka");
			System.out.println("1.  Electronics");
			System.out.println("2.  Sports");
			System.out.println("3.  Exit");
			System.out.println("enter your choice");
			int choice=0;
			Scanner scn=new Scanner(System.in);
			try {
			choice=scn.nextInt();
			}catch (Exception e) {
				System.out.println(" ");
			}
			switch (choice) {
			case 1:
			{
				electronics();
				break;
			}
			
			case 2:
			{
				sports();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("Please enter a valid choice");
				home(name);
				break;
			}
			}
	}
	
	static void electronics() {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println("Welcome to electronics department "+name);
			System.out.println("1. Mobiles");
			System.out.println("2. Laptops");
			System.out.println("3. Televisions");
			System.out.println("4. Exit");
			System.out.println("Enter your choice");
			int elecchoice=0;
			try {
			elecchoice =sc.nextInt();
			}catch (Exception e) {
				System.out.println(" ");
			}
			switch (elecchoice) {
			case 1:
			{
				mobiles();
				break;
			}
			case 2:
			{
				laptops();
				break;
			}
			case 3:
			{
				television();
				break;
			}
			case 4:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("Please enter a valid choice");
				electronics();
				break;
			}
			}
		}
	
	static void mobiles() {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println("Welcome to laptop section "+name);
		String[][] mob=new String[6][2]; 
		mob[0][0]="Product";
		mob[0][1]="                                                                  Price";
		mob[1][0]=1+". Redmi Note 4 (Black, 64 GB)  (4 GB RAM)                              ";
		mob[1][1]="10999";
		mob[2][0]=2+". Redmi Note 5 (Gold, 64 GB)  (4 GB RAM)                               ";
		mob[2][1]="11999";
		mob[3][0]=3+". Redmi Note 4 (Dark Grey, 64 GB)  (4 GB RAM)                         ";
		mob[3][1]="10999";
		mob[4][0]=4+". Honor 9 Lite (Sapphire Blue, 64 GB)  (4 GB RAM)                     ";
		mob[4][1]="14999";
		mob[5][0]=5+". Infinix Hot S3 (Blush Gold, 32 GB)  (3 GB RAM)                      ";
		mob[5][1]="8999";
		for(int i=0;i<=5;i++) {
			for(int j=0;j<2;j++) {
				System.out.print(mob[i][j]);
			}
			System.out.println();
		}
		System.out.println("6. Back");
		System.out.println("7. Exit");
		System.out.println("Select Product, Enter your choice");
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		try {
		mobchoice=scn.nextInt();
		}
		catch (Exception e) {
			System.out.println("please enter number");
		}
		switch (mobchoice) {
		case 1:
		{
			mob1(mob[1][0],mob[1][1]);
			break;
		}
		case 2:
		{
			mob2(mob[2][0],mob[2][1]);
			break;
		}
		case 3:
		{
			mob3(mob[3][0],mob[3][1]);
			break;
		}
		case 4:
		{
			mob4(mob[4][0],mob[4][1]);
			break;
		}
		case 5:
		{
			mob5(mob[5][0],mob[5][1]);
			break;
		}
		case 6:
		{
			electronics();
			break;
		}
		case 7:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("Please enter a valid choice");
			mobiles();
			break;
		}
		}
	}
	static void mob1(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			mobchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (mobchoice) {
		case 1:
		{
			
			cart(product,price);
			break;
		}
		case 2:
		{
			
			mobiles();
			break;
		}
		case 3:
		{
			
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			mob1(product,price);
			break;
		}
		}
	
	}
	
	static void mob2(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			mobchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (mobchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			mobiles();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			mob2(product,price);
			break;
		}
		}
	
	}
	static void mob3(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			mobchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (mobchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			mobiles();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			mob3(product,price);
			break;
		}
		}
	
	}
	static void mob4(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			mobchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (mobchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			mobiles();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			mob4(product,price);
			break;
		}
		}
	
	}
	static void mob5(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int mobchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			mobchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (mobchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			mobiles();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			mob5(product,price);
			break;
		}
		}
	
	}
	
	private static void laptops() {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println("Welcome to laptop section "+name);
		String[][] lap=new String[6][2]; 
		lap[0][0]="Product";
		lap[0][1]="                                                                                                                     Price";
		lap[1][0]="1. Lenovo Core i3 6th Gen - (4 GB/1 TB HDD/Windows 10 Home)                    ";
		lap[1][1]="28990";
		lap[2][0]="2. Lenovo APU Dual Core A6 7th Gen - (4 GB/1 TB HDD/DOS)                        ";
		lap[2][1]="19990";
		lap[3][0]="3. Lenovo Ideapad Core i3 6th Gen - (4 GB / 1 TB HDD/DOS)                           ";
		lap[3][1]="24990";
		lap[4][0]="4. Lenovo Ideapad Core i3 6th Gen - (4 GB/2 TB HDD/Windows 10 Home)    ";
		lap[4][1]="31990";
		lap[5][0]="5. Lenovo Yoga 510 Core i3 6th Gen - (4 GB/1 TB HDD/Windows 10 Home)";
		lap[5][1]="40049";
		for(int i=0;i<=5;i++) {
			for(int j=0;j<2;j++) {
				System.out.print(lap[i][j]);
			}
			System.out.println();
		}
		System.out.println("6. Back");
		System.out.println("7. Exit");
		System.out.println("Select Product, Enter your choice");
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		try {
		lapchoice=scn.nextInt();
		}
		catch (Exception e) {
			System.out.println("please enter number");
		}
		switch (lapchoice) {
		case 1:
		{
			lap1(lap[1][0],lap[1][1]);
			break;
		}
		case 2:
		{
			lap2(lap[2][0],lap[2][1]);
			break;
		}
		case 3:
		{
			lap3(lap[3][0],lap[3][1]);
			break;
		}
		case 4:
		{
			lap4(lap[4][0],lap[4][1]);
			break;
		}
		case 5:
		{
			lap5(lap[5][0],lap[5][1]);
			break;
		}
		case 6:
		{
			electronics();
			break;
		}
		case 7:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("Please enter a valid choice");
			laptops();
			break;
		}
		}
	}
	static void lap1(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			lapchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (lapchoice) {
		case 1:
		{
			
			cart(product,price);
			break;
		}
		case 2:
		{
			
			laptops();
			break;
		}
		case 3:
		{
			
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			lap1(product,price);
			break;
		}
		}
	
	}
	
	static void lap2(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			lapchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (lapchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			laptops();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			lap2(product,price);
			break;
		}
		}
	
	}
	static void lap3(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			lapchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (lapchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			laptops();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			lap3(product,price);
			break;
		}
		}
	
	}
	static void lap4(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			lapchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (lapchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			laptops();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			lap4(product,price);
			break;
		}
		}
	
	}
	static void lap5(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int lapchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			lapchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (lapchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			laptops();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			lap5(product,price);
			break;
		}
		}
	
	}
	
	
	static void television() {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println("Welcome to laptop section "+name);
			String[][] tv=new String[6][2]; 
			tv[0][0]="Product";
			tv[0][1]="                                                                  Price";
			tv[1][0]="1. CloudWalker 139 cm (55 inch) Ultra HD (4K) LED Smart TV)            ";
			tv[1][1]="39999";
			tv[2][0]="2. Sony 80.1 cm (32 inch) Full HD LED Smart TV  (KLV-32W672E)          ";
			tv[2][1]="32999";
			tv[3][0]="3. Vu 80 cm (32 inch) HD Ready LED Smart TV  (32D6475_HD smart)        ";
			tv[3][1]="19500";
			tv[4][0]="4. LG 108 cm (43 inch) Full HD LED Smart TV  (43LJ554T)                ";
			tv[4][1]="40999";
			tv[5][0]="5. Micromax 81 cm (32 inch) HD Ready LED Smart TV  (CanvasS2)          ";
			tv[5][1]="18999";
			for(int i=0;i<=5;i++) {
				for(int j=0;j<2;j++) {
					System.out.print(tv[i][j]);
				}
				System.out.println();
			}
			System.out.println("6. Back");
			System.out.println("7. Exit");
			System.out.println("Select Product, Enter your choice");
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			try {
			tvchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
			switch (tvchoice) {
			case 1:
			{
				tv1(tv[1][0],tv[1][1]);
				break;
			}
			case 2:
			{
				tv2(tv[2][0],tv[2][1]);
				break;
			}
			case 3:
			{
				tv3(tv[3][0],tv[3][1]);
				break;
			}
			case 4:
			{
				tv4(tv[4][0],tv[4][1]);
				break;
			}
			case 5:
			{
				tv5(tv[5][0],tv[5][1]);
				break;
			}
			case 6:
			{
				electronics();
				break;
			}
			case 7:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("Please enter a valid choice");
				television();
				break;
			}
			}
		}
		static void tv1(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				tvchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (tvchoice) {
			case 1:
			{
				
				cart(product,price);
				break;
			}
			case 2:
			{
				
				television();
				break;
			}
			case 3:
			{
				
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				tv1(product,price);
				break;
			}
			}
		
		}
		
		static void tv2(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				tvchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (tvchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				television();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				tv2(product,price);
				break;
			}
			}
		
		}
		static void tv3(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				tvchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (tvchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				television();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				tv3(product,price);
				break;
			}
			}
		
		}
		static void tv4(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				tvchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (tvchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				television();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				tv4(product,price);
				break;
			}
			}
		
		}
		static void tv5(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int tvchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				tvchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (tvchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				television();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				tv5(product,price);
				break;
			}
			}
		
	}

	static void exit() {
		System.out.println("Thank you for visiting");
		System.exit(0);
	}
	
	static void sports() {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println("Welcome to electronics department "+name);
			System.out.println("1. Cricket");
			System.out.println("2. Badminton");
			System.out.println("3. Exit");
			System.out.println("Enter your choice");
			int elecchoice=0;
			try {
			elecchoice =sc.nextInt();
			}catch (Exception e) {
				System.out.println(" ");
			}
			switch (elecchoice) {
			case 1:
			{
				cricket();
				break;
			}
			case 2:
			{
				badminton();
				break;
			}
			
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("Please enter a valid choice");
				electronics();
				break;
			}
			}
	}
	static void badminton() {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println("Welcome to laptop section "+name);
			String[][] bad=new String[6][2]; 
			bad[0][0]="Product";
			bad[0][1]="                                                                  Price";
			bad[1][0]="1. ARTENGO by Decathlon BR800 G2 Strung  (Black, Yellow, Weight)       ";
			bad[1][1]="1199";
			bad[2][0]="2. ARTENGO by Decathlon BR900V G2 Strung  (Green, Weight - 76 g)       ";
			bad[2][1]="3499";
			bad[3][0]="3. ARTENGO by Decathlon BR800 G2 Strung  (Yellow, Weight - 75 g)       ";
			bad[3][1]="1099";
			bad[4][0]="4. ARTENGO by Decathlon BR700 G2 Strung  (Pink, Weight - 125 g)        ";
			bad[4][1]="249";
			bad[5][0]="5. ARTENGO by Decathlon BR730 G2 Strung  (Red, Weight - 90 g)          ";
			bad[5][1]="449";
			for(int i=0;i<=5;i++) {
				for(int j=0;j<2;j++) {
					System.out.print(bad[i][j]);
				}
				System.out.println();
			}
			System.out.println("6. Back");
			System.out.println("7. Exit");
			System.out.println("Select Product, Enter your choice");
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			try {
			badchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
			switch (badchoice) {
			case 1:
			{
				bad1(bad[1][0],bad[1][1]);
				break;
			}
			case 2:
			{
				bad2(bad[2][0],bad[2][1]);
				break;
			}
			case 3:
			{
				bad3(bad[3][0],bad[3][1]);
				break;
			}
			case 4:
			{
				bad4(bad[4][0],bad[4][1]);
				break;
			}
			case 5:
			{
				bad5(bad[5][0],bad[5][1]);
				break;
			}
			case 6:
			{
				sports();;
				break;
			}
			case 7:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("Please enter a valid choice");
				badminton();
				break;
			}
			}
		}
		static void bad1(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				badchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (badchoice) {
			case 1:
			{
				
				cart(product,price);
				break;
			}
			case 2:
			{
				
				sports();
				break;
			}
			case 3:
			{
				
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				bad1(product,price);
				break;
			}
			}
		
		}
		
		static void bad2(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				badchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (badchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				sports();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				bad2(product,price);
				break;
			}
			}
		
		}
		static void bad3(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				badchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (badchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				sports();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				bad3(product,price);
				break;
			}
			}
		
		}
		static void bad4(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				badchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (badchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				sports();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				bad4(product,price);
				break;
			}
			}
		
		}
		static void bad5(String product,String price) {
			System.out.println("Welcome to Shopping Adda "+name);
			System.out.println(product);
			System.out.println(price);
			int badchoice=0;
			Scanner scn=new Scanner(System.in);
			System.out.println("1. Buy");
			System.out.println("2. Back");
			System.out.println("3. Exit");
			try {
				badchoice=scn.nextInt();
				}
				catch (Exception e) {
					System.out.println("please enter number");
				}
			switch (badchoice) {
			case 1:
			{
				cart(product,price);
				break;
			}
			case 2:
			{
				sports();
				break;
			}
			case 3:
			{
				exit();
				break;
			}
			default:
			{
				System.out.println("please enter a valid choice");
				bad5(product,price);
				break;
			}
			}
	}
	static void cricket() {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println("Welcome to laptop section "+name);
		String[][] cric=new String[6][2]; 
		cric[0][0]="Product";
		cric[0][1]="                                                                  Price";
		cric[1][0]="1. Puma Unisex- 89409401 Kashmir Willow Cricket Bat (Short Handle)     ";
		cric[1][1]="999";
		cric[2][0]="2. Shrey Match Helmet With Mild Steel Visor Cricket Helmet(Navy Blue)  ";
		cric[2][1]="981";
		cric[3][0]="3. Prokyde Aligator Batting Glove Batting Gloves (Men, White)          ";
		cric[3][1]="191";
		cric[4][0]="4. Adidas AB7090 Kashmir Willow Cricket Bat  (Short Handle, 1280 g)    ";
		cric[4][1]="1277";
		cric[5][0]="5. Prokyde Rookie Poplar Cricket Bat(Short Handle, 1000 - 1200 g)      ";
		cric[5][1]="333";
		for(int i=0;i<=5;i++) {
			for(int j=0;j<2;j++) {
				System.out.print(cric[i][j]);
			}
			System.out.println();
		}
		System.out.println("6. Back");
		System.out.println("7. Exit");
		System.out.println("Select Product, Enter your choice");
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		try {
		cricchoice=scn.nextInt();
		}
		catch (Exception e) {
			System.out.println("please enter number");
		}
		switch (cricchoice) {
		case 1:
		{
			cric1(cric[1][0],cric[1][1]);
			break;
		}
		case 2:
		{
			cric2(cric[2][0],cric[2][1]);
			break;
		}
		case 3:
		{
			cric3(cric[3][0],cric[3][1]);
			break;
		}
		case 4:
		{
			cric4(cric[4][0],cric[4][1]);
			break;
		}
		case 5:
		{
			cric5(cric[5][0],cric[5][1]);
			break;
		}
		case 6:
		{
			sports();;
			break;
		}
		case 7:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("Please enter a valid choice");
			cricket();
			break;
		}
		}
	}
	static void cric1(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			cricchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (cricchoice) {
		case 1:
		{
			
			cart(product,price);
			break;
		}
		case 2:
		{
			
			cricket();
			break;
		}
		case 3:
		{
			
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cric1(product,price);
			break;
		}
		}
	
	}
	
	static void cric2(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			cricchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (cricchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			cricket();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cric2(product,price);
			break;
		}
		}
	
	}
	static void cric3(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			cricchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (cricchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			cricket();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cric3(product,price);
			break;
		}
		}
	
	}
	static void cric4(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			cricchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (cricchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			cricket();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cric4(product,price);
			break;
		}
		}
	
	}
	static void cric5(String product,String price) {
		System.out.println("Welcome to Shopping Adda "+name);
		System.out.println(product);
		System.out.println(price);
		int cricchoice=0;
		Scanner scn=new Scanner(System.in);
		System.out.println("1. Buy");
		System.out.println("2. Back");
		System.out.println("3. Exit");
		try {
			cricchoice=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (cricchoice) {
		case 1:
		{
			cart(product,price);
			break;
		}
		case 2:
		{
			cricket();
			break;
		}
		case 3:
		{
			exit();
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cric5(product,price);
			break;
		}
		}
	
	}
	
	
	static void cart(String product,String price) {
		arl1.add(++count);
		arl2.add(product);
		int pric=Integer.parseInt(price);
		arl3.add(pric);
		System.out.println("Enter Quantity");
		int quan=0;
		Scanner scn=new Scanner(System.in);
		try {
			quan=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		arl4.add(quan);
		
		int total=pric*quan;
		arl5.add(total);
		System.out.println("Product added to cart");
		System.out.println("1. Checkout");
		System.out.println("2. Continue Shopping");
		int ch=0;
		try {
			ch=scn.nextInt();
			}
			catch (Exception e) {
				System.out.println("please enter number");
			}
		switch (ch) {
		case 1:
		{
			checkout();
			break;
		}
		case 2:
		{
			home(name);
			break;
		}
		default:
		{
			System.out.println("please enter a valid choice");
			cart(product,price);
			break;
		}
	}
	
	}
	
	static void checkout() {
		float gti=0,gtf=0;
		float dis=0,gt=0;
		System.out.println("S.No. Products                       price            quantity              total");
		for(int i=0;i<arl1.size();i++) {
			System.out.println(arl1.get(i)+"  "+arl2.get(i)+"   "+arl3.get(i)+"   "+arl4.get(i)+"    "+arl5.get(i));
			gti=gti+arl5.get(i);
		}
		
		if(gti>0&&gti<=5000) {
			dis=((gti*5)/100);
		}
		else if(gti>5000&&gti<=20000) {
			dis=((gti*10)/100);
		}
		else if(gti>20000&&gti<=500000) {
			dis=((gti*15)/100);
		}
		else if(gti>500000) {
			dis=((gti*15)/100);
		}
		System.out.println("discount ="+dis);
		gtf=gti-dis;
		float gst1=gtf*6/100;
		float gst2=gtf*6/100;
		System.out.println("gst = "+gst1);
		System.out.println("sgst = "+gst2);
		gt=gtf+gst1+gst2;
		System.out.println("total = "+gt);
		Scanner scn=new Scanner(System.in);
		System.out.println("Enter your address");
		String add=scn.nextLine();
		System.out.println("your products will delivered to this address");
		System.out.println(add);
		if(gti>50000) {
			System.out.println("thank you for shopping, you got a lifetime discount of 15% by shopping more than 50000");
			System.exit(0);
		}
		else
		{
			System.out.println("Goodbye"+"thank you for shopping");
			System.exit(0);
		}
		scn.close();
	}
	
}



