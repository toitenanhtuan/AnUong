package nguoi;
import java.util.Scanner;

class Nguoi {
    private String ten;
    private int tuoi;
    private double chieuCao;
    private String monAn;

    public Nguoi() {
        ten = "";
        tuoi = 0;
        chieuCao = 0.0;
        monAn = "";
    }

    public Nguoi(String ten, int tuoi, double chieuCao, String monAn) {
        this.ten = ten;
        this.tuoi = tuoi;
        this.chieuCao = chieuCao;
        this.monAn = monAn;
    }

    public String getTen() {
        return ten;
    }

    public void setTen(String ten) {
        this.ten = ten;
    }

    public int getTuoi() {
        return tuoi;
    }

    public void setTuoi(int tuoi) {
        this.tuoi = tuoi;
    }

    public double getChieuCao() {
        return chieuCao;
    }

    public void setChieuCao(double chieuCao) {
        this.chieuCao = chieuCao;
    }

    public String getMonAn() {
        return monAn;
    }

    public void setMonAn(String monAn) {
        this.monAn = monAn;
    }

    public void nhapThongTin() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập tên: ");
        ten = scanner.nextLine();
        System.out.print("Nhập tuổi: ");
        tuoi = scanner.nextInt();
        System.out.print("Nhập chiều cao (m): ");
        chieuCao = scanner.nextDouble();
        scanner.nextLine();
        System.out.print("Nhập món ăn: ");
        monAn = scanner.nextLine();
    }

    public void cao() {
        if (chieuCao >= 1.7 && monAn.equalsIgnoreCase("cơm")) {
            xuatThongTin();
        }
    }

    public void xuatThongTin() {
        System.out.println("Tên: " + ten);
        System.out.println("Tuổi: " + tuoi);
        System.out.println("Chiều cao: " + chieuCao + "m");
        System.out.println(ten + " đang ăn " + monAn);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập số người: ");
        int n = scanner.nextInt();
        scanner.nextLine(); // Đọc ký tự Enter sau khi nhập số người

        Nguoi[] danhSachNguoi = new Nguoi[n]; // Tạo mảng để lưu thông tin n người

        // Nhập thông tin của n người
        for (int i = 0; i < n; i++) {
            System.out.println("Nhập thông tin người thứ " + (i + 1));
            danhSachNguoi[i] = new Nguoi();
            danhSachNguoi[i].nhapThongTin();
        }

        // Xuất thông tin của n người
        System.out.println("Thông tin của các người:");
        for (int i = 0; i < n; i++) {
            danhSachNguoi[i].xuatThongTin();
        }

        // Xuất thông tin của những người có chiều cao trên 1.7 và đang ăn cơm
        System.out.println("Thông tin của những người có chiều cao trên 1.7 và đang ăn cơm:");
        for (int i = 0; i < n; i++) {
            danhSachNguoi[i].cao();
        }
    }
}
