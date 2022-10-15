[English Version](http://openbookproject.net/thinkcs/python/english3e/preface.html)

# Lời nói đầu

Bởi Jeffrey Elkner

Cuốn sách này có được sự tồn tại của nó nhờ sự hợp tác giữa Internet và phong trào phần mềm tự do. Ba tác giả của nó — một giáo sư đại học, một giáo viên trung học và một lập trình viên chuyên nghiệp — chưa bao giờ gặp mặt trực tiếp để làm việc về nó, nhưng chúng tôi đã có thể cộng tác chặt chẽ, được hỗ trợ bởi nhiều người khác, những người đã dành thời gian và năng lượng để gửi cho chúng tôi phản hồi của họ.

<details>
  <summary>English version</summary>

  > This book owes its existence to the collaboration made possible by the Internet and the free software movement. Its three authors—a college professor, a high school teacher, and a professional programmer—never met face to face to work on it, but we have been able to collaborate closely, aided by many other folks who have taken the time and energy to send us their feedback.
</details>

Chúng tôi nghĩ rằng cuốn sách này là một minh chứng cho những lợi ích và khả năng trong tương lai của hình thức hợp tác này, khung làm việc  đã được Richard Stallman và Tổ chức Phần mềm Tự do đưa ra.

<details>
  <summary>English version</summary>

  > We think this book is a testament to the benefits and future possibilities of this kind of collaboration, the framework for which has been put in place by Richard Stallman and the Free Software Foundation.
</details>

## Làm thế nào và tại sao tôi sử dụng Python

Năm 1999, lần đầu tiên kỳ thi Khoa học Máy tính của College Board’s Advanced Placement (AP) được tổ chức bằng C++. Cũng như ở nhiều trường trung học trong cả nước, quyết định thay đổi ngôn ngữ có ảnh hưởng trực tiếp đến chương trình giảng dạy môn khoa học máy tính tại trường trung học Yorktown ở Arlington, Virginia, nơi tôi giảng dạy. Cho đến thời điểm này, Pascal là ngôn ngữ giảng dạy trong cả các khóa học năm thứ nhất và AP của chúng tôi. Để phù hợp với thông lệ trước đây là cho sinh viên tiếp xúc với cùng một ngôn ngữ trong hai năm, chúng tôi đã quyết định chuyển sang C++ trong khóa học năm đầu tiên cho năm học 1997-98 để chúng tôi bắt kịp với sự thay đổi của Hội đồng Quản trị Cao đẳng đối với khóa học AP vào năm sau.

<details>
  <summary>English version</summary>

  > In 1999, the College Board’s Advanced Placement (AP) Computer Science exam was given in C++ for the first time. As in many high schools throughout the country, the decision to change languages had a direct impact on the computer science curriculum at Yorktown High School in Arlington, Virginia, where I teach. Up to this point, Pascal was the language of instruction in both our first-year and AP courses. In keeping with past practice of giving students two years of exposure to the same language, we made the decision to switch to C++ in the first year course for the 1997-98 school year so that we would be in step with the College Board’s change for the AP course the following year.
</details>

Hai năm sau, tôi tin rằng C++ là một lựa chọn tồi để sử dụng cho việc giới thiệu với sinh viên về khoa học máy tính. Mặc dù nó chắc chắn là một ngôn ngữ lập trình rất mạnh mẽ, nhưng nó cũng là một ngôn ngữ cực kỳ khó học và dạy. Tôi thấy mình liên tục đấu tranh với cú pháp khó của C++ và nhiều cách làm việc, và kết quả là tôi đã mất nhiều sinh viên một cách không cần thiết. Tin chắc rằng phải có một lựa chọn ngôn ngữ tốt hơn cho lớp học năm nhất của chúng tôi, tôi đã tìm kiếm một giải pháp thay thế cho C++.

<details>
  <summary>English version</summary>

  > Two years later, I was convinced that C++ was a poor choice to use for introducing students to computer science. While it is certainly a very powerful programming language, it is also an extremely difficult language to learn and teach. I found myself constantly fighting with C++’s difficult syntax and multiple ways of doing things, and I was losing many students unnecessarily as a result. Convinced there had to be a better language choice for our first-year class, I went looking for an alternative to C++.
</details>

Tôi cần một ngôn ngữ có thể chạy trên các máy GNU/Linux trong phòng thí nghiệm của chúng tôi cũng như trên các nền tảng Windows và Macintosh mà hầu hết sinh viên có ở nhà. Tôi muốn nó là phần mềm miễn phí, để sinh viên có thể sử dụng nó ở nhà bất kể thu nhập của họ như thế nào. Tôi muốn một ngôn ngữ được sử dụng bởi các lập trình viên chuyên nghiệp và một ngôn ngữ có cộng đồng nhà phát triển tích cực xung quanh nó. Nó phải hỗ trợ cả lập trình thủ tục và hướng đối tượng. Và quan trọng nhất, nó phải dễ học và dễ dạy. Khi tôi xem xét các lựa chọn với những mục tiêu này, Python nổi bật là ứng cử viên tốt nhất cho công việc.

<details>
  <summary>English version</summary>

  > I needed a language that would run on the machines in our GNU/Linux lab as well as on the Windows and Macintosh platforms most students have at home. I wanted it to be free software, so that students could use it at home regardless of their income. I wanted a language that was used by professional programmers, and one that had an active developer community around it. It had to support both procedural and object-oriented programming. And most importantly, it had to be easy to learn and teach. When I investigated the choices with these goals in mind, Python stood out as the best candidate for the job.
</details>

Tôi đã đề nghị một trong những sinh viên tài năng của Yorktown, Matt Ahrens, dùng thử Python. Trong hai tháng, anh ấy không chỉ học ngôn ngữ mà còn viết một ứng dụng có tên là pyTicket cho phép nhân viên của chúng tôi báo cáo các vấn đề công nghệ qua Web. Tôi biết rằng Matt không thể hoàn thành một ứng dụng có quy mô đó trong thời gian ngắn như vậy bằng C++ và thành tích này, kết hợp với đánh giá tích cực của Matt về Python, cho thấy Python là giải pháp mà tôi đang tìm kiếm.

<details>
  <summary>English version</summary>

  > I asked one of Yorktown’s talented students, Matt Ahrens, to give Python a try. In two months he not only learned the language but wrote an application called pyTicket that enabled our staff to report technology problems via the Web. I knew that Matt could not have finished an application of that scale in so short a time in C++, and this accomplishment, combined with Matt’s positive assessment of Python, suggested that Python was the solution I was looking for.
</details>

## Tìm sách giáo khoa

Khi quyết định sử dụng Python trong cả hai lớp khoa học máy tính nhập môn của tôi vào năm sau, vấn đề cấp bách nhất là thiếu một cuốn sách giáo khoa có sẵn.

<details>
  <summary>English version</summary>

  > Having decided to use Python in both of my introductory computer science classes the following year, the most pressing problem was the lack of an available textbook.
</details>

`@todo:` Tài liệu miễn phí đã đến để giải cứu. Đầu năm, Richard Stallman đã giới thiệu tôi với Allen Downey. Cả hai chúng tôi đã viết thư cho Richard bày tỏ sự quan tâm đến việc phát triển các tài liệu giáo dục miễn phí. Allen đã viết một cuốn sách giáo khoa khoa học máy tính năm đầu tiên, Cách suy nghĩ như một nhà khoa học máy tính. Khi tôi đọc cuốn sách này, tôi biết ngay rằng tôi muốn sử dụng nó trong lớp của mình. Đó là văn bản khoa học máy tính rõ ràng và hữu ích nhất mà tôi từng thấy. Nó nhấn mạnh các quá trình suy nghĩ liên quan đến lập trình hơn là các tính năng của một ngôn ngữ cụ thể. Đọc nó ngay lập tức khiến tôi trở thành một giáo viên tốt hơn.

<details>
  <summary>English version</summary>

  > Free documents came to the rescue. Earlier in the year, Richard Stallman had introduced me to Allen Downey. Both of us had written to Richard expressing an interest in developing free educational materials. Allen had already written a first-year computer science textbook, How to Think Like a Computer Scientist. When I read this book, I knew immediately that I wanted to use it in my class. It was the clearest and most helpful computer science text I had seen. It emphasized the processes of thought involved in programming rather than the features of a particular language. Reading it immediately made me a better teacher.
</details>

"Làm thế nào để suy nghĩ như một nhà khoa học máy tính" không chỉ là một cuốn sách xuất sắc, mà nó đã được phát hành theo giấy phép công cộng GNU, có nghĩa là nó có thể được sử dụng tự do và sửa đổi để đáp ứng nhu cầu của người dùng. Khi tôi quyết định sử dụng Python, tôi chợt nhận ra rằng tôi có thể dịch phiên bản Java gốc của cuốn sách của Allen sang ngôn ngữ mới. Mặc dù tôi không thể tự viết sách giáo khoa, nhưng việc có cuốn sách của Allen đã giúp tôi có thể làm như vậy, đồng thời chứng minh rằng mô hình phát triển hợp tác được sử dụng rất tốt trong phần mềm cũng có thể hoạt động cho giáo dục.

<details>
  <summary>English version</summary>

  > How to Think Like a Computer Scientist was not just an excellent book, but it had been released under the GNU public license, which meant it could be used freely and modified to meet the needs of its user. Once I decided to use Python, it occurred to me that I could translate Allen’s original Java version of the book into the new language. While I would not have been able to write a textbook on my own, having Allen’s book to work from made it possible for me to do so, at the same time demonstrating that the cooperative development model used so well in software could also work for educational materials.
</details>

Làm việc trên cuốn sách này trong hai năm qua rất bổ ích cho cả tôi và học sinh, và các học sinh của tôi đóng một vai trò quan trọng trong quá trình này. Vì tôi có thể thay đổi ngay lập tức bất cứ khi nào ai đó phát hiện ra lỗi chính tả hoặc đoạn văn khó, nên tôi khuyến khích họ tìm lỗi trong sách bằng cách cho họ điểm thưởng mỗi khi họ đưa ra đề xuất dẫn đến thay đổi trong văn bản. Điều này mang lại lợi ích gấp đôi là khuyến khích họ đọc kỹ văn bản hơn và được các nhà phê bình quan trọng nhất của nó, những sinh viên sử dụng nó để học khoa học máy tính xem xét kỹ lưỡng.

<details>
  <summary>English version</summary>

  > Working on this book for the last two years has been rewarding for both my students and me, and my students played a big part in the process. Since I could make instant changes whenever someone found a spelling error or difficult passage, I encouraged them to look for mistakes in the book by giving them a bonus point each time they made a suggestion that resulted in a change in the text. This had the double benefit of encouraging them to read the text more carefully and of getting the text thoroughly reviewed by its most important critics, students using it to learn computer science.
</details>

Trong nửa sau của cuốn sách về lập trình hướng đối tượng, tôi biết rằng cần phải có người có kinh nghiệm lập trình thực tế hơn tôi mới có thể làm đúng. Cuốn sách ở trạng thái chưa hoàn thành trong hơn một năm cho đến khi cộng đồng nguồn mở một lần nữa cung cấp các phương tiện cần thiết để hoàn thành cuốn sách.

<details>
  <summary>English version</summary>

  > For the second half of the book on object-oriented programming, I knew that someone with more real programming experience than I had would be needed to do it right. The book sat in an unfinished state for the better part of a year until the open source community once again provided the needed means for its completion.
</details>

Tôi đã nhận được một email từ Chris Meyers bày tỏ sự quan tâm đến cuốn sách. Chris là một lập trình viên chuyên nghiệp, người đã bắt đầu giảng dạy một khóa học lập trình bằng Python vào năm ngoái tại trường Cao đẳng Cộng đồng Lane ở Eugene, Oregon. Triển vọng giảng dạy khóa học đã đưa Chris đến với cuốn sách và anh ấy bắt đầu giúp đỡ nó ngay lập tức. Vào cuối năm học, anh ấy đã tạo một dự án đồng hành trên Trang web của chúng tôi tại [http://openbookproject.net](http://openbookproject.net) có tên là [Python for Fun](http://openbookproject.net/py4fun) và đang làm việc với một số sinh viên tiên tiến nhất của tôi với tư cách là một giáo viên chính, hướng dẫn họ vượt ra ngoài nơi tôi có thể lấy chúng.

<details>
  <summary>English version</summary>

  > I received an email from Chris Meyers expressing interest in the book. Chris is a professional programmer who started teaching a programming course last year using Python at Lane Community College in Eugene, Oregon. The prospect of teaching the course had led Chris to the book, and he started helping out with it immediately. By the end of the school year he had created a companion project on our Website at http://openbookproject.net called *Python for Fun* and was working with some of my most advanced students as a master teacher, guiding them beyond where I could take them.
</details>

## Giới thiệu lập trình với Python

Quá trình dịch và sử dụng "Cách suy nghĩ như một nhà khoa học máy tính" trong hai năm qua đã xác nhận tính phù hợp của Python để dạy học sinh mới bắt đầu. Python đơn giản hóa đáng kể các ví dụ lập trình và làm cho các ý tưởng lập trình quan trọng dễ dạy hơn.

<details>
  <summary>English version</summary>

  > The process of translating and using How to Think Like a Computer Scientist for the past two years has confirmed Python’s suitability for teaching beginning students. Python greatly simplifies programming examples and makes important programming ideas easier to teach.
</details>

Ví dụ đầu tiên từ văn bản minh họa điểm này. Đây là chương trình `hello, world` truyền thống, trong phiên bản Java của cuốn sách trông giống như sau:

<details>
  <summary>English version</summary>

  > The first example from the text illustrates this point. It is the traditional hello, world program, which in the Java version of the book looks like this:
</details>

```java
class Hello {
  public static void main (String[] args) {
      System.out.println ("Hello, world.");
  }
}
```

trong phiên bản Python, nó trở thành:

<details>
  <summary>English version</summary>

  > in the Python version it becomes:
</details>

```python
print("Hello, World!")
```

`@todo:` Mặc dù đây là một ví dụ nhỏ, nhưng những ưu điểm của Python vẫn rất nổi bật. Khóa học Khoa học Máy tính của Yorktown I không có điều kiện tiên quyết, vì vậy nhiều sinh viên nhìn thấy ví dụ này đang xem chương trình đầu tiên của họ. Một số người trong số họ chắc chắn là một chút lo lắng, khi nghe nói rằng lập trình máy tính rất khó học. Phiên bản Java luôn buộc tôi phải chọn giữa hai tùy chọn không hài lòng: hoặc giải thích lớp Hello, public static void main, String [] args, {, và }, các câu lệnh và có nguy cơ gây nhầm lẫn hoặc đe dọa một số sinh viên ngay khi bắt đầu, hoặc nói với họ, Bây giờ đừng lo lắng về tất cả những thứ đó; chúng ta sẽ nói về nó sau, và rủi ro tương tự. Mục tiêu giáo dục tại thời điểm này trong khóa học là giới thiệu cho sinh viên ý tưởng về một câu lệnh lập trình và để họ viết chương trình đầu tiên của họ, từ đó giới thiệu họ với môi trường lập trình. Chương trình Python có chính xác những gì cần thiết để thực hiện những điều này và không có gì hơn.

<details>
  <summary>English version</summary>

  > Even though this is a trivial example, the advantages of Python stand out. Yorktown’s Computer Science I course has no prerequisites, so many of the students seeing this example are looking at their first program. Some of them are undoubtedly a little nervous, having heard that computer programming is difficult to learn. The Java version has always forced me to choose between two unsatisfying options: either to explain the class Hello, public static void main, String[] args, {, and }, statements and risk confusing or intimidating some of the students right at the start, or to tell them, Just don’t worry about all of that stuff now; we will talk about it later, and risk the same thing. The educational objectives at this point in the course are to introduce students to the idea of a programming statement and to get them to write their first program, thereby introducing them to the programming environment. The Python program has exactly what is needed to do these things, and nothing more.
</details>

`@todo:` So sánh văn bản giải thích của chương trình trong mỗi phiên bản của cuốn sách sẽ minh họa rõ hơn điều này có ý nghĩa như thế nào đối với học sinh mới bắt đầu. Có bảy đoạn giải thích về Hello, world! trong phiên bản Java; trong phiên bản Python, chỉ có một số câu. Quan trọng hơn, sáu đoạn văn bị thiếu không liên quan đến những ý tưởng lớn trong lập trình máy tính mà là những điều vụn vặt của cú pháp Java. Tôi thấy điều này xảy ra tương tự trong suốt cuốn sách. Toàn bộ đoạn văn chỉ đơn giản là biến mất khỏi phiên bản Python của văn bản vì cú pháp rõ ràng hơn nhiều của Python khiến chúng trở nên không cần thiết.

<details>
  <summary>English version</summary>

  > Comparing the explanatory text of the program in each version of the book further illustrates what this means to the beginning student. There are seven paragraphs of explanation of Hello, world! in the Java version; in the Python version, there are only a few sentences. More importantly, the missing six paragraphs do not deal with the big ideas in computer programming but with the minutia of Java syntax. I found this same thing happening throughout the book. Whole paragraphs simply disappear from the Python version of the text because Python’s much clearer syntax renders them unnecessary.
</details>

`@todo:` Sử dụng một ngôn ngữ cấp rất cao như Python cho phép giáo viên hoãn việc nói về các chi tiết cấp thấp của máy cho đến khi học sinh có kiến ​​thức nền tảng mà họ cần hiểu rõ hơn về các chi tiết. Do đó, nó tạo ra khả năng đặt những điều đầu tiên lên hàng đầu về mặt sư phạm. Một trong những ví dụ tốt nhất về điều này là cách Python xử lý các biến. Trong Java, một biến là tên của một nơi chứa giá trị nếu nó là một kiểu dựng sẵn và một tham chiếu đến một đối tượng nếu nó không phải. Việc giải thích sự khác biệt này đòi hỏi một cuộc thảo luận về cách máy tính lưu trữ dữ liệu. Do đó, ý tưởng về một biến được gắn với phần cứng của máy. Khái niệm cơ bản và mạnh mẽ về một biến đã đủ khó đối với học sinh mới bắt đầu (trong cả khoa học máy tính và đại số). Byte và địa chỉ không giúp ích gì cho vấn đề. Trong Python, một biến là tên dùng để chỉ một thứ. Đây là một khái niệm trực quan hơn nhiều cho học sinh mới bắt đầu và gần với ý nghĩa của biến mà các em đã học trong các khóa học toán của mình. Tôi đã gặp ít khó khăn hơn nhiều khi dạy các biến trong năm nay so với trước đây và tôi đã dành ít thời gian hơn để giúp học sinh giải quyết các vấn đề khi sử dụng chúng.

<details>
  <summary>English version</summary>

  > Using a very high-level language like Python allows a teacher to postpone talking about low-level details of the machine until students have the background that they need to better make sense of the details. It thus creates the ability to put first things first pedagogically. One of the best examples of this is the way in which Python handles variables. In Java a variable is a name for a place that holds a value if it is a built-in type, and a reference to an object if it is not. Explaining this distinction requires a discussion of how the computer stores data. Thus, the idea of a variable is bound up with the hardware of the machine. The powerful and fundamental concept of a variable is already difficult enough for beginning students (in both computer science and algebra). Bytes and addresses do not help the matter. In Python a variable is a name that refers to a thing. This is a far more intuitive concept for beginning students and is much closer to the meaning of variable that they learned in their math courses. I had much less difficulty teaching variables this year than I did in the past, and I spent less time helping students with problems using them.
</details>

`@todo:` Một ví dụ khác về cách Python hỗ trợ trong việc dạy và học lập trình là ở cú pháp của nó cho các hàm. Học sinh của tôi luôn gặp rất nhiều khó khăn trong việc hiểu các hàm. Vấn đề chính xoay quanh sự khác biệt giữa định nghĩa hàm và lệnh gọi hàm, và sự khác biệt liên quan giữa tham số và đối số. Python đến để giải cứu với cú pháp không có gì đẹp đẽ. Các định nghĩa hàm bắt đầu bằng từ khóa def, vì vậy tôi chỉ đơn giản nói với các sinh viên của mình, Khi bạn định nghĩa một hàm, hãy bắt đầu bằng def, theo sau là tên của hàm mà bạn đang định nghĩa; khi bạn gọi một hàm, chỉ cần gọi (nhập) tên của nó. Các tham số đi cùng với các định nghĩa; các đối số đi kèm với các cuộc gọi. Không có kiểu trả về, kiểu tham số hoặc các tham số tham chiếu và giá trị để cản trở, vì vậy tôi hiện có thể dạy các hàm trong thời gian ngắn hơn một nửa so với thời gian trước đây, với khả năng hiểu tốt hơn.

<details>
  <summary>English version</summary>

  > Another example of how Python aids in the teaching and learning of programming is in its syntax for functions. My students have always had a great deal of difficulty understanding functions. The main problem centers around the difference between a function definition and a function call, and the related distinction between a parameter and an argument. Python comes to the rescue with syntax that is nothing short of beautiful. Function definitions begin with the keyword def, so I simply tell my students, When you define a function, begin with def, followed by the name of the function that you are defining; when you call a function, simply call (type) out its name. Parameters go with definitions; arguments go with calls. There are no return types, parameter types, or reference and value parameters to get in the way, so I am now able to teach functions in less than half the time that it previously took me, with better comprehension.
</details>

`@todo:` Sử dụng Python đã cải thiện hiệu quả của chương trình khoa học máy tính của chúng tôi cho tất cả học sinh. Tôi thấy mức độ thành công chung cao hơn và mức độ thất vọng thấp hơn so với kinh nghiệm giảng dạy bằng C++ hoặc Java. Tôi đã di chuyển nhanh hơn với kết quả tốt hơn. Nhiều sinh viên rời khóa học với khả năng tạo ra các chương trình có ý nghĩa và với thái độ tích cực đối với trải nghiệm lập trình mà điều này tạo ra.

<details>
  <summary>English version</summary>

  > Using Python improved the effectiveness of our computer science program for all students. I saw a higher general level of success and a lower level of frustration than I experienced teaching with either C++ or Java. I moved faster with better results. More students left the course with the ability to create meaningful programs and with the positive attitude toward the experience of programming that this engenders.
</details>

## Xây dựng cộng đồng

Tôi đã nhận được email từ khắp nơi trên thế giới từ những người sử dụng cuốn sách này để học hoặc dạy lập trình. Một cộng đồng người dùng đã bắt đầu xuất hiện và nhiều người đã đóng góp cho dự án bằng cách gửi tài liệu cho Trang web đồng hành tại [http://openbookproject.net/pybiblio](http://openbookproject.net/pybiblio).

<details>
  <summary>English version</summary>

  > I have received email from all over the globe from people using this book to learn or to teach programming. A user community has begun to emerge, and many people have been contributing to the project by sending in materials for the companion Website at http://openbookproject.net/pybiblio.
</details>

Với sự phát triển không ngừng của Python, tôi hy vọng sự phát triển trong cộng đồng người dùng sẽ tiếp tục và tăng tốc. Sự xuất hiện của cộng đồng người dùng này và khả năng nó gợi ý cho sự hợp tác tương tự giữa các nhà giáo dục là những phần thú vị nhất khi làm việc trong dự án này đối với tôi. Bằng cách làm việc cùng nhau, chúng ta có thể nâng cao chất lượng tài liệu sẵn có để sử dụng và tiết kiệm thời gian quý báu. Tôi mời bạn tham gia cộng đồng của chúng tôi và mong nhận được phản hồi từ bạn. Vui lòng viết thư cho tôi tại [jeff@elkner.net](jeff@elkner.net).

<details>
  <summary>English version</summary>

  > With the continued growth of Python, I expect the growth in the user community to continue and accelerate. The emergence of this user community and the possibility it suggests for similar collaboration among educators have been the most exciting parts of working on this project for me. By working together, we can increase the quality of materials available for our use and save valuable time. I invite you to join our community and look forward to hearing from you. Please write to me at jeff@elkner.net.
</details>

Jeffrey Elkner

Governor’s Career and Technical Academy in Arlington

Arlington, Virginia

## Liên kết hữu dụng
- [Mục lục](README.md)
- [Trang trước](foreword.md) - Lời tựa
- [Trang kế](preface3-rle.md) - Rhodes Local Edition (RLE) (Phiên bản Tháng 8 năm 2012)
