import java.util.Scanner;
public class Main {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);
        String ad, sifre;

        int bakiye = 1000;



        int dogru = 3;

        while (dogru > 0) {

            System.out.print("Kullanıcı Adınızı Giriniz: ");
            ad = input.nextLine();
            System.out.print("Şifrenizi Giriniz: ");
            sifre = input.nextLine();


            if (ad.equals("deniz") && sifre.equals("2404")) {
                System.out.println("Giriş Yaptınız, İşleminizi Seçin ");
                int islem;
                do {

                    System.out.println("\n1-Para Yatırma\n2-Para Çekme\n3-Bakiye Sorgulama\n4-Çıkış");

                    System.out.print("Seçiminiz: ");
                    islem = input.nextInt();

                    switch (islem) {

                        case 1:
                            System.out.print("Yatırılacak Tutar:");
                            int tutar = input.nextInt();
                            bakiye = tutar + bakiye;
                            break;

                        case 2:
                            System.out.print("Çekilecek Tutar:");
                            int cekme = input.nextInt();

                            if (cekme > bakiye) {
                                System.out.println("Yetersiz Bakiye");
                            } else {
                                bakiye = bakiye - cekme;
                            }
                            break;

                        case 3:
                            System.out.println("\nBakiyeniz: " + bakiye);
                            break;

                        case 4:
                            System.out.println("Çıkış Yaptınız.");
                            break;

                        default:
                            System.out.println("Hatali Bir Giriş Yaptınız");
                            break;

                    }
                }while (islem !=4);
                break;



            } else {
                dogru--;


                if(dogru <= 0){
                    System.out.println("Hesabınız Bloke Olmuştur");
                }
                    else {
                    System.out.println("Hatalı Giriş Yaptınız, Lütfen Tekrar Deneyin");
                    System.out.println("Kalan Hakkınız:"+ dogru);
                }
        }
    }
    }
}
