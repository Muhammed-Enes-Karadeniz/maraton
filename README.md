public class Deneme {

    public static void main(String[] args) {
        String[] isimler = {"kadir", "gökhan", "hakan", "suzan", "pınar", "mehmet", "ali", "emel", "fırat", "james", "jale", "ersin", "deniz", "gözde", "anıl", "burak"};
        int[] dereceler = {341, 273, 278, 329, 445, 402, 388, 270, 243, 334, 412, 393, 299, 343, 317, 265};
        eniyiüçderece(isimler, dereceler);
        sınıflandırveyaz(dereceler);
    }
    public static void eniyiüçderece(String[] isimler, int[] dereceler) {
        int[] siraliDereceler = new int[dereceler.length];
        for (int i = 0; i < dereceler.length; i++) {
            siraliDereceler[i] = dereceler[i];
        }
        for (int i = 0; i < siraliDereceler.length - 1; i++) {
            for (int j = i + 1; j < siraliDereceler.length; j++) {
                if (siraliDereceler[j] < siraliDereceler[i]) {
                    int temp = siraliDereceler[i];
                    siraliDereceler[i] = siraliDereceler[j];
                    siraliDereceler[j] = temp;
                }
            }
        }
        int sayac = 0;
        for (int i = 0; i < siraliDereceler.length; i++) {
            if (sayac >= 3) {
                break;
            }
            for (int j = 0; j < dereceler.length; j++) {
                if (dereceler[j] == siraliDereceler[i]) {
                    System.out.println(isimler[j] + " - " + dereceler[j] + " dakika");
                    sayac++;
                    break;
                }
            }
        }
    }
    public static void sınıflandırveyaz(int[] dereceler) {
        int asınıfı = 0;
        int bsınıfı = 0;
        int csınıfı = 0;
        for (int dakika : dereceler) {
            if (dakika <= 300) {
                asınıfı++;
            } else if (dakika <= 400) {
                bsınıfı++;
            } else {
                csınıfı++;
            }
        }
        System.out.println("A →" + asınıfı + ", B →" + bsınıfı + ", C →" + csınıfı);
    }
}
