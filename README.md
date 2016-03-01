# Lập trình MapReduce với Python

Trong bài viết này, ta sẽ thiết kế và cài đặt các thuật toán MapReduce cho các tác vụ xử lý dữ liệu thông thường. Mô hình lập trình MapReduce được đề xuất trong một bài báo năm 2004 từ một nhóm nghiên cứu tại Google. MapReduce là một mô hình đơn giản để xử lý song song các tập dữ liệu lớn (Big Data).

Bài viết này giúp bạn làm quen với tư duy lập trình MapReduce. Ta sẽ sử dụng tập dữ liệu nhỏ để dễ kiểm tra kết quả thực thi cũng như để quan sát hoạt động bên trong MapReduce như thế nào.

# Giới thiệu về tập dữ liệu

**books.json**

Đây là tập dữ liệu chứa danh sách các văn bản. Mỗi dòng tương ứng với một văn bản gồm document_id và text. Quan sát 3 dòng đầu tiên của tập dữ liệu.

```
["milton-paradise.txt", "[ Paradise Lost by John Milton 1667 ] Book I Of Man ' s first disobedience , and the fruit Of that forbidden tree whose mortal taste Brought death into the World , and all our woe , With loss of Eden , till one greater Man Restore us , and regain the blissful seat , Sing , Heavenly Muse , that , on the secret top Of Oreb , or of Sinai , didst inspire That shepherd who first taught the chosen seed In the beginning how the heavens and earth Rose out of Chaos : or , if Sion hill Delight thee more , and Siloa ' s brook that flowed Fast by the oracle of God , I thence Invoke thy aid to my adventurous song , That with no middle flight intends to soar Above th ' Aonian mount , while it pursues Things unattempted yet in prose or rhyme ."]
["edgeworth-parents.txt", "[ The Parent ' s Assistant , by Maria Edgeworth ] THE ORPHANS . Near the ruins of the castle of Rossmore , in Ireland , is a small cabin , in which there once lived a widow and her four children . As long as she was able to work , she was very industrious , and was accounted the best spinner in the parish ; but she overworked herself at last , and fell ill , so that she could not sit to her wheel as she used to do , and was obliged to give it up to her eldest daughter , Mary ."]
["austen-emma.txt", "[ Emma by Jane Austen 1816 ] VOLUME I CHAPTER I Emma Woodhouse , handsome , clever , and rich , with a comfortable home and happy disposition , seemed to unite some of the best blessings of existence ; and had lived nearly twenty - one years in the world with very little to distress or vex her . She was the youngest of the two daughters of a most affectionate , indulgent father ; and had , in consequence of her sister ' s marriage , been mistress of his house from a very early period . Her mother had died too long ago for her to have more than an indistinct remembrance of her caresses ; and her place had been supplied by an excellent woman as governess , who had fallen little short of a mother in affection ."]
...
```

**records.json**

Đây là tập dữ liệu chứa thông tin các đơn hàng gồm Order và LineItem. Order chứa thông tin về một đơn hàng, LineItem chứa thông tin các sản phẩm thuộc về một đơn hàng. Quan sát các dòng dữ liệu thuộc về đơn hàng có id=1.


