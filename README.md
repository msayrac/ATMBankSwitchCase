# ATMBankSwitchCase
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        String userName, password;
        int right = 3;
        int balance = 1500;
        int select;
        Scanner input = new Scanner(System.in);
        while (right > 0) {
            System.out.println("Kullanici adinizi giriniz : ");
            userName = input.nextLine();
            System.out.println("Sifrenizi giriniz : ");
            password = input.nextLine();
            if (userName.equals("patika") && password.equals("dev123")) {
                System.out.println("Merhaba Kodluyoruz Bank a hosgeldiniz : ");
                do {
                    System.out.println("Lutfen yapmak istediginiz islemi seciniz : ");
                    System.out.println("1- para yatirma\n" +
                            "2-para cekme \n" +
                            "3- Bakiye sorgulama\n" +
                            "4- Cikis yap");
                    select = input.nextInt();
                    switch (select){
                        case 1:
                            System.out.println("Para miktari : ");
                            int price = input.nextInt();
                            balance = balance + price;
                            System.out.println("Toplam paraniz : " + balance);
                            break;
                        case 2:
                            System.out.println("Para miktari : ");
                            int price1 = input.nextInt();
                            if (price1 > balance) {
                                System.out.println("Hesabinizde yeterli baliye bulunmamaktadir");
                            } else {
                                balance = balance - price1;
                                System.out.println("Kalan paraniz : " + balance);
                            }
                            break;
                        case 3:
                            System.out.println("Bakiyeniz : " + balance);
                            break;
                    }

                } while (select != 4);
                System.out.println("Tekrar g??r????mek ??zere. ");
                break;
            } else {
                --right;
                if (right == 0) {
                    System.out.println("Hesabiniz bloke olmu??tur. L??tfen banka ile ileti??ime geciniz");
                    break;
                }
                System.out.println("Hatali kullanici adi veya sifre. Tekrar deneyiniz.");
                System.out.println("Kalan hakkiniz : " + right);
            }
        }
    }
}


