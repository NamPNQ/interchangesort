title: Phần I
subtitle: Giải thuật
class: segue dark nobackground

---

title: I.Giải thuật
subtitle: 1.Định nghĩa cặp nghịch thế
class: 

Cho dãy số gồm N phần tử A[1], A[2], A[3],......A[N].<br>Cặp số thỏa điều kiện A > A[j] và j > i thì cặp số đó gọi là cặp nghịch thế.

---

title: I.Giải thuật
subtitle: 2.Giải thuật bài toán
class: big
build_lists: true

- Thực hiện xét các cặp nghịch thế trong dãy số rồi triệt tiêu dần chúng đi bằng cách đổi chỗ 2 phần tử tương ứng trong cặp nghịch thế đó.
- Lặp lại cách xử lí trên cho đến khi hết các cặp nghịch thế trong dãy.

---

title: I.Giải thuật
subtitle: 3.Các bước tiến hành
class: big
build_lists: true

- Bước 1: i = 1; //bắt đầu từ đầu dãy
- Bước 2: j = i + 1//tìm các phần tử a[j] < a[i], j > i
- Bước 3: <br>Trong khi j < N thực hiện.<br>
Nếu a[j] < a[i] thì hoán vị a[j], a[i];<br> Nếu i < n: Lặp lại Bước 2<br> Ngược lại: Dừng<br>
j = j + 1;
- Bước 4: i = i + 1 ;

---

title: Phần II
subtitle: Cài đặt thuật toán
class: segue dark nobackground

---

title: II.Cài đặt thuật toán

<pre class="prettyprint" data-lang="c">
void InterchangeSort(int[] a, int N){
	int i, j;
	for(int i=0; i&lt;= N-1; i++)
		for(int j=i+1; j&lt; N; j++)
			if(a[j]&lt;a[i])
				Swap(a[j],a[i]);
}
</pre>

---

title: Phần III
subtitle: Demo
class: segue dark nobackground

---

<iframe src="/demo/ComparisonSort.html"></iframe>

---

title: Phần IV
subtitle: Đánh giá thuật toán
class: segue dark nobackground

---

title: IV.Đánh giá thuật toán
class: 

Thấy ngay số phép so sánh là luôn không đổi, tức không phụ thuộc vào tình trạng ban đầu của dãy.<br> Ta có thể ước lượng số phép so sánh bằng
(n-1) + (n-2) + … + 1 = n(n-1)/2 <br>
(phần tử thứ i được so sánh với n-i phần tử còn lại.)<br>
Số phép hoán vị (tương đương 3 phép gán) lại phụ thuộc vào tình trạng ban đầu của dãy. Cụ thể như sau:<br>
* Trường hợp tốt nhất: Dãy ban đầu đã có thứ tự. Ta thấy ngay ta hông tốn một phép hoán vị nào.<br>
* Trường hợp xấu nhất: Dãy ban đầu có thứ tự ngược. Ta thấy ngay mỗi lần so sánh phần tử thứ i với n-i phần tử còn lại, ta đều phải thực hiện hoán vị. Điều này có nghĩa là số phép hoán vị bằng n(n-1)/2.<br>
Tổng kết lại, ta có độ phức tạp của Interchange Sort thuộc O(n<sup>2<sup>) trong mọi trường hợp.<br>

---

title: V.Tham khảo
class: big
build_lists: true

- Visualizing Algorithms, David Galles, University of San Francisco.
