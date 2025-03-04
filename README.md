# pbo-no.1
package tugaspboayu;
/**
 *
 * @author ANISYA NANDA AYU K
 */
// Kelas abstrak Bangun Datar
abstract class BangunDatar {
    abstract float luas();
    abstract double keliling();
}
// Kelas Persegi
class Persegi extends BangunDatar {
    float sisi;
    Persegi(float sisi) {
        this.sisi = sisi;
    }
    @Override
    float luas() {
        return sisi * sisi;
    }
    @Override
    double keliling() {
        return 4 * sisi;
    }
}

// Kelas Lingkaran
class Lingkaran extends BangunDatar {
    float r;
    Lingkaran(float r) {
        this.r = r;
    }
    @Override
    float luas() {
        return (float) (Math.PI * r * r);
    }
    @Override
    double keliling() {
        return 2 * Math.PI * r;
    }
}

// Kelas Segitiga
class Segitiga extends BangunDatar {
    float alas, tinggi;
    Segitiga(float alas, float tinggi) {
        this.alas = alas;
        this.tinggi = tinggi;
    }
    @Override
    float luas() {
        return 0.5f * alas * tinggi;
    }
    @Override
    double keliling() {
        // Mengasumsikan segitiga siku-siku, sehingga sisi miring bisa dihitung dengan Pythagoras
        double sisiMiring = Math.sqrt(alas * alas + tinggi * tinggi);
        return alas + tinggi + sisiMiring;
    }
}

// Kelas Main untuk menjalankan program
public class Main {
    public static void main(String[] args) {
        Persegi persegi = new Persegi(6);
        Lingkaran lingkaran = new Lingkaran(14);
        Segitiga segitiga = new Segitiga(4, 6);

        System.out.println("Luas Persegi: " + persegi.luas());
        System.out.println("Keliling Persegi: " + persegi.keliling());

        System.out.println("Luas Lingkaran: " + lingkaran.luas());
        System.out.println("Keliling Lingkaran: " + lingkaran.keliling());

        System.out.println("Luas Segitiga: " + segitiga.luas());
        System.out.println("Keliling Segitiga: " + segitiga.keliling());
    }
}
