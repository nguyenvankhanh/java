### Java Online

#### Static (tĩnh): Sử dụng cho biến, hàm và đoạn code

- Biến static:
  vd:
  public static String ten;
  sv1.ten = "Khanh";
  sout sv2.ten; -> cũng hiện thị là "Khanh" -> nó không giống biến bình thường, khi 1 biến static được khai báo thì tất cả các object đều có thể dùng "chung" nó
- Hàm static:
  vd:
  public static void hienTenTruong() {
   sout "tên trường là:" + this.ten;
  }
  -> không thể viết ntn được vì hàm static không được khai báo biến bình thường ở trong nó, phải dùng biến static. Vì các object sẽ dùng chung hàm static mà khai báo biến này thì nó không còn "chung" nữa
- Đoạn code static (chỉ gọi hàm static và biến static):
  Là code khởi chạy của class, chỉ chạy một lần duy nhất sau khi khởi tạo object đầu tiên
  static {
  sout "đây là đoạn code static";
  }
  -> gọi bao nhiêu lần đoạn code này thì nó cũng chỉ hiển thị 1 lần.

#### Hàm contructor:

tên hàm cùng tên class:

vd: public class SinhVien -> hàm contructor: public SinhVien

có thể có tham số vì nó là hàm

dùng để khởi tạo object

có thể không có tham số truyền vào

Hàm contructor có thể có nhiều hàm nhưng các tham số truyền vào phải khác nhau:

-> ví du:

public SinhVien(int ma) và public SinhVien(int code)

-> như vầy java sẽ không hiểu hàm khởi tạo với biến khởi tạo int là khởi tạo cho hàm nào 

-> public SinhVien(String ten) -> ok

**Từ khóa super trong kế thừa:** đây là contructor mặc định của một class, nó rỗng.

- Note:

  1. Trong contructor của class con phải gọi contructor của class cha chạy, nếu không gọi mặc định Java sẽ gọi contructor rỗng của class cha chạy.

     -> bởi vì class con kế thừa class cha, nó sẽ viết thêm các thuộc tính của nó nên phạm vi sẽ rộng hơn class cha. nên phải khởi tạo class cha trước (khai báo contructor cha), xong mới khởi tạo class con được.

  2. 

### Mảng trong Java:

- Mảng là 1 object thuộc class array

- Cách lặp các phần tử của mảng for(int a :  arr) {

  ​	sout(a);

  }

  vòng lặp for này tương đương với for(int i=0; i<arr.length; i++) {

  ​	sout(arr[i]);

  }

### Con trỏ trong Java:

- Object thực ra chính là con trỏ, trỏ đến vùng nhớ chứa dữ liệu của object đó:

  ví dụ: SinhVien sv1 = new SinhVien();

  sv1.tuoi = 20;

  SinhVien sv2 = sv1;

  

  sv2.tuoi=21;

  sout("sv1.tuoi") -> sẽ bằng 21

  Bởi vì khi gắn sv2 = sv1 không phải là ta copy sv1 sang sv2 mà là gán địa chỉ của object sv1 cho sv2

  -> vì thế nên khi gán tuổi sv2 = 21 tức là ta đang gán biến tuổi trong object có giá trị là 21

  ##### Tham chiếu và tham trị

  **tham chiếu:**

  int a = 10;

  nhanHai(a);

  sout(a);

  public static void nhanHai(int x) {

  ​	x = x * 2;

  }

  -> ở đây khi in ra a thì giá trị của nó vẫn là 10 vì bản chất là truyền giá trị của biến, tức truyền tham trị

  -> a và x là khác nhau, ở hàm nhanHai chỉ gán giá trị của a là 10 cho x rồi x nó làm gì tùy nó.

  **tham trị:**

  SinhVien sv1 =  new SinhVien();

  sv1.x = 10;

  nhanHai(sv1);

  sout(sv1.x);

  public static void nhanHai(SinhVien sv1) {

  ​	sv1.x = sv1.x * 2;

  }

  -> ở đây khi khi in ra sv1.x thì giá trị sẽ là 20 vì khi truyền sv1 tức là ta đang truyền object sv1, truyền tham chiếu. con trỏ sẽ trỏ đến vùng nhớ chứa object sv1 và nhân 2 giá trị x lên

 

### Kế thừa trong Java:

1. Class con có thể sử dụng các thuộc tính và hàm của class cha nhưng ngược lại thì không

2. Biến thì không có ghi đề khi kế thừa 

   vd: class cha có: public int tuoi = 30;

   class con kế thừa class cha cũng có public int tuoi = 20;

   khi gọi khởi tạo object class cha thì giá trị tuoi vẫn là 30. chỉ khi nào thực hiện get set thì nó mới tính là thuộc tính -> kế thừa được.
   
3. Có một cách có thể gọi nhiều class con một lúc đó là sử dụng: khai báo class cha new class con

   vd: Staff s1 = new Manager (trong đố Manager là con extend từ Staff)

   khi đó nếu gọi hàm bất kỳ: public void danhSachNhanVien(Staff[] ds) {

   ​	sout(ds[i].display());

   }

   -> display ở đây là display Manager (class con) chứ không phải class cha. Nếu không có tính năng này khi muốn code hiện danh sách Manager, bảo vệ, trưởng phòng ... sẽ mất nhiều thời gian.

   -> đây là một ví dụ về tính đa hình

4. Chú ý: nếu khai báo class con new class cha là không được

   vd: Manager m1 = new Staff();

   vì trong manager có staff nên nó có thể trỏ đến vùng nhớ của staff được, ngược lại trong staff thì không đầy đủ của manager (manager có các thuộc tính riêng của nó) nên m1 không thể trỏ đến vùng nhớ không đầy đủ của nó được

5. kế thừa này chỉ có tính 1 : 1, manager ko thể vừa extend staff vừa extend những class khác được

   Nhưng đương nhiên Staff vẫn có thể có nhiều class con extend như Manager


### Abstract class

1. Abstract function: Là hàm ảo -  hàm không có thân hàm mà chỉ có khuôn dạng (tên, tham số truyền vào, kiểu trả về). Mục đích là để bắt các class con kế thừa class có hàm ảo này phải cài đè(override) hàm ảo này

2. Khi khai báo 1 hàm ảo trong 1 class bình thường thì không được, hàm ảo thì class của nó cũng phải là class ảo vd: public abstact class NhanVien {

   }

3. Vì class abstract là class ảo nên nó không tạo được object vd: NhanVien nv = new NhanVien() là không được

4. 1 abstract class thì có thể không có, có 1 hoặc nhiều abstract function.

   


### Từ khóa final: 

​	1. Khi khai báo từ khóa này đi kèm với class thì class đó trở thành class không thể kế thừa được. 

​	vd public final class CongNhan {

​	}

​	public class SinhVien extend CongNhan -> sẽ báo lỗi

2. Khi khai báo từ khóa này đi kèm với function thì các class mà kế thừa class chứa function này sẽ không thể cài đè (override) lại function này được (ngược lại vs abstract - sinh ra để cài đè)

3. Từ khóa final mà đi với biến thì đó là hằng số, và khi khai báo thì phải gán giá trị luôn.

   vd: final int x; -> như vầy ko được mà phải là final int x = 4;

### Interface

1. Là class mà chỉ có hàm ảo(abstract function), ko có hàm thật nào cả

   vd: public interface NhanVien {

   ​	void nhapThongTin(); // không cần public abstract void nhapThongTin() luôn vì nó khi khai báo interface nó tự hiểu hàm là hàm ảo rồi

   }

2. Vậy tại sao lại cần dùng interface:

   . Thứ nhất là để đa kế thừa, 1 class chỉ có thể kế thừa 1 class vd: class SinhVien extend Nguoi, NhanVien là không được. Nhưng interface thì có thể vd: class TruongPhong implement NhanVien1, NhanVien2

   . Ngoài ra nó còn dùng để tổ chức code tốt hơn, ví dụ người viết class quanLyNhanSu sẽ cần thông tin của các class NhanVien, TruongPhong, BaoVe... để tránh phải chờ phải code hết các class kia xong thì ms code được thì sử dụng interface để gọi hàm viết class qlns trước, thân hàm cứ từ từ viết sau

   . Là khung của class, nghĩa là cứ khai báo interface xong viết hàm để đấy (các hàm ở interface chỉ có tên hàm chứ không có thân hàm, không thể code thân hàm ở đó), thằng nào kế thừa thì cài đè rồi viết sau

3. trong interface thì không có biến, chỉ có hằng số vd: public final int a = 9;

   nhưng vì mặc định trong interface là hằng số nên public final có thể bỏ đi chỉ còn int a = 9;

   -> chú ý điều này: đó không phải là biến mà là hằng số

4. 2 interface có thể extend lẫn nhau

5. default: khi một function được khai báo default trong interface, vd:

   public interface NhanVien{

   ​	void NhapThongTin();

   ​	default void HienThongTin() {

   ​		sout("có thể viết code ở đây");

   ​	}

   }

   ->khi có dùng default như thế này thì các class hay interface kế thừa interface có hàm default này có thể không cần cài đè (mặc định nó sẽ lấy code default)

6. Interface thì không tạo object được, vì nó không có hàm, chỉ có khuôn dạng hàm thì biết gọi hàm trong object kiểu gì

### Inner class

1. Là class nằm trong một class khác
2. Nó có thể có viết hàm tùy ý và cũng có thể gọi trực tiếp các hàm và biến của class bao ngoài nó. Tuy nhiên với class bao ngoài khi muốn truy xuất đến các hàm và biến ở inner class thì phải khởi tạo object trước rồi mới truy xuất được

### Anonymous class - class vô danh

1. Là inner class (nằm trong 1 class khác)
2. Không được định nghĩa tên class ở cú pháp mà chỉ được sinh ra khi biên dịch
3. Dùng khi cần sử dụng interface, ta không cần tạo class để implement mà có thể sử dụng luôn interface và cài đè những hàm cần thiết của interface -> ta có luôn 1 object của interface đó(nhưng object đó thuộc class gì thì ko biết - "vô danh")
4. Một class vô danh chỉ tạo được 1 object

### Try Catch

1. cú pháp:

   try {

   ​	code ...

   ​	// ý nghĩa: hãy thực hiện đoạn code này

   ​	// nếu đoạn code này có dòng nào gặp sự cố thì sẽ dừng không xử lý nữa và nhảy vào catch chạy

   } catch (Exception e) {

   ​	// trong đây giống như viết hàm, chỉ là 1 đoạn code bình thường

   ​	vd: sout ("Không được chia cho 0");

   }

2. Những biến khai báo trong try thì chỉ trong try mới hiểu, khai báo trong catch thì chỉ trong catch mới hiểu, nếu muốn dùng cho cả 2 thì phải khai báo ở ngoài

3. catch chồng nhau thì cách làm là khi chạy thử nó show ra exception gì thì mình copy exception đó cho vào trong catch rồi show message tương ứng. -> xem chi tiết: <https://www.youtube.com/watch?v=PzEvqFNpzRk&list=PLuIgExrod9MPSSsNerd71B21OCgOo_ab3&index=9>

4. catch (Exception e) là cha của mọi exception nên khi có nhiều catch thì thằng catch này phải để ở cuối cùng nếu không nó sẽ so khớp luôn -> những thằng catch ở dưới không thể chạy được -> báo lỗi

5. try catch thì không để ở trong hàm, vì hàm chỉ là để xử lý logic thuần túy, còn try catch nó là thông báo mang tính giao diện -> phải try catch ở chỗ khác -> sử dụng phương pháp gọi là ủy thác exception.

   Tức là chỉ là hàm đó có thể tạo ra exception gì đó -> khi gọi hàm thì phải try catch.

   Tuy nhiên tránh trường hợp có người dùng hàm mà lại không try catch, thì ta có thể bắt họ phải try catch cho hàm đó bằng cách "ủy thác" throws exception

   vd: public static phepChia(int a, int b) throws FileNotFound Exception

   -> bất kỳ chỗ nào mà gọi hàm phepChia thì phải try catch FileNotFound Exception nếu không sẽ báo lỗi
   
   Thêm nữa ở chỗ ủy thác throws kia ta có thể ủy thác nhiều exception cùng lúc, các exception cách nhau bởi dấu phẩy. Lưu ý nếu ủy thác throws Exception như thế này tức là ủy thác kiểu chung chung, vì exception nào cũng kế thừa từ Exception cả nên cần viết rõ ra là ủy thác loại exception nào

6. Tự tạo exception: Do có các exception mà java không có sẵn nên ta phải tự tạo exception riêng

   vd: int tuoi; -> tuổi luôn phải là số dương vì thế nếu nhập vào là số âm ta phải có exception

   Nếu chỉ đơn giản là bắt ngoại lệ số âm này thì đơn giản hơn là dùng if else cũng được, nhưng nếu tạo exception thì sẽ sử dụng được cho những trường hợp khác nữa.

   vd:

   try {

   ​	if(tuoi <= 0) {

   ​		Exception eTuoi = new Exception("Tuổi không được <= 0");

   ​		throw eTuoi;

   ​		// chú ý: throw không có s khác với throws có s ở bên trên

   ​	}

   } catch(Exception ex) {

   ​	.... đoạn này code tự sinh

   }

   Ngoài cách sinh exception trực tiếp như ở vd trên thì còn có cách là viết riêng file exception rồi gọi vào (gọi bằng cách gọi class exception ở chỗ new Exception bên trên)

7. Từ khóa finally:

   Khi ta sử dụng từ khóa này trong try catch thì dù có try catch vào trường hợp nào hay là không thì nó luôn chạy đoạn code trong finally