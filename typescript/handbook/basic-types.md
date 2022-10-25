# Những thứ cơ bản

[Online version](https://www.typescriptlang.org/docs/handbook/2/basic-types.html)

Chào mừng đến với trang đầu tiên của cuốn sổ tay. Nếu đây là trải nghiệm đầu tiên của bạn với TypeScript - bạn có thể muốn bắt đầu tại một trong các hướng dẫn ['Bắt đầu'](intro.md#bắt-đầu)

<details>
  <summary>English version</summary>

  > Welcome to the first page of the handbook. If this is your first experience with TypeScript - you may want to start at one of the 'Getting Started' guides
</details>

Mỗi và mọi giá trị trong JavaScript đều có một tập hợp các hành vi mà bạn có thể quan sát khi chạy các hoạt động khác nhau. Điều đó nghe có vẻ trừu tượng, nhưng là một ví dụ nhanh, hãy xem xét một số hoạt động chúng ta có thể chạy trên một thông báo có tên biến.

<details>
  <summary>English version</summary>

  > Each and every value in JavaScript has a set of behaviors you can observe from running different operations. That sounds abstract, but as a quick example, consider some operations we might run on a variable named message.
</details>

```typescript
// Accessing the property 'toLowerCase'
// on 'message' and then calling it
message.toLowerCase();
// Calling 'message'
message();
```

Nếu chúng ta chia nhỏ điều này, dòng mã chạy được đầu tiên sẽ truy cập một thuộc tính có tên là `toLowerCase` và sau đó gọi nó. Dòng mã thứ hai cố gắng gọi trực tiếp `message`.

<details>
  <summary>English version</summary>

  > If we break this down, the first runnable line of code accesses a property called `toLowerCase` and then calls it. The second one tries to call `message` directly.
</details>

Nhưng giả sử chúng ta không biết giá trị của `message` - và điều đó khá phổ biến - chúng ta không thể nói chắc chắn rằng chúng ta sẽ nhận được kết quả gì khi cố gắng chạy bất kỳ đoạn mã nào trong số này. Hành vi của mỗi hoạt động phụ thuộc hoàn toàn vào giá trị mà chúng ta đã có ngay từ đầu.

<details>
  <summary>English version</summary>

  > But assuming we don’t know the value of `message` - and that’s pretty common - we can’t reliably say what results we’ll get from trying to run any of this code. The behavior of each operation depends entirely on what value we had in the first place.
</details>

- Có thể gọi được `message` không?
- Nó có thuộc tính `toLowerCase` trên đó không?
- Nếu có thì `toLowerCase` có thể gọi được không?
- Nếu cả hai giá trị này đều có thể gọi được thì chúng trả về giá trị gì?

<details>
  <summary>English version</summary>

  > - Is `message` callable?
  > - Does it have a property called `toLowerCase` on it?
  > - If it does, is `toLowerCase` even callable?
  > - If both of these values are callable, what do they return?
</details>

Câu trả lời cho những câu hỏi này thường là những thứ chúng ta ghi nhớ trong đầu khi viết JavaScript và chúng ta phải hy vọng rằng chúng ta đã hiểu đúng tất cả các chi tiết.

<details>
  <summary>English version</summary>

  > The answers to these questions are usually things we keep in our heads when we write JavaScript, and we have to hope we got all the details right.
</details>

Giả sử `message` được xác định theo cách sau.

<details>
  <summary>English version</summary>

  > Let’s say `message` was defined in the following way.
</details>

```typescript
const message = "Hello World!";
```

Như bạn có thể đoán, nếu chúng ta cố gắng chạy message.toLowerCase (), chúng ta sẽ chỉ nhận được cùng một chuỗi viết thường.

<details>
  <summary>English version</summary>

  > As you can probably guess, if we try to run message.toLowerCase(), we’ll get the same string only in lower-case.
</details>

Còn dòng mã thứ hai thì sao? Nếu bạn đã quen với JavaScript, bạn sẽ biết điều này không thành công với một ngoại lệ:

<details>
  <summary>English version</summary>

  > What about that second line of code? If you’re familiar with JavaScript, you’ll know this fails with an exception:
</details>

```typescript
TypeError: message is not a function
```

Thật tuyệt nếu chúng ta có thể tránh được những sai lầm như thế này.

<details>
  <summary>English version</summary>

  > It’d be great if we could avoid mistakes like this.
</details>

Khi chúng ta chạy mã của mình, cách mà JavaScript runtime của chúng ta chọn việc cần làm là tìm ra kiểu của giá trị - loại hành vi và khả năng mà nó có. Đó là một phần của những gì TypeError đang ám chỉ - nó nói rằng chuỗi "Hello World!" không thể được gọi là một hàm.

<details>
  <summary>English version</summary>

  > When we run our code, the way that our JavaScript runtime chooses what to do is by figuring out the type of the value - what sorts of behaviors and capabilities it has. That’s part of what that TypeError is alluding to - it’s saying that the string "Hello World!" cannot be called as a function.
</details>

Đối với một số giá trị, chẳng hạn như kiểu nguyên thủy chuỗi và số, chúng ta có thể xác định kiểu của chúng trong thời gian chạy bằng cách sử dụng toán tử typeof. Nhưng đối với những thứ khác như hàm, không có cơ chế thời gian chạy tương ứng để xác định loại của chúng. Ví dụ, hãy xem xét hàm này:

<details>
  <summary>English version</summary>

  > For some values, such as the primitives string and number, we can identify their type at runtime using the typeof operator. But for other things like functions, there’s no corresponding runtime mechanism to identify their types. For example, consider this function:
</details>

```typescript
function fn(x) {
  return x.flip();
}
```

Chúng ta có thể _quan sát_ bằng cách đọc mã rằng hàm này sẽ chỉ hoạt động nếu được cung cấp một đối tượng có thuộc tính callable `flip`, nhưng JavaScript không hiển thị thông tin này theo cách mà chúng ta có thể kiểm tra khi mã đang chạy. Cách duy nhất trong JavaScript thuần túy để biết những gì `fn` làm với một giá trị cụ thể là gọi nó và xem điều gì sẽ xảy ra. Loại hành vi này khiến bạn khó dự đoán mã sẽ làm gì trước khi chạy, điều đó có nghĩa là khó biết mã của bạn sẽ làm gì trong khi viết.

<details>
  <summary>English version</summary>

  > We can _observe_ by reading the code that this function will only work if given an object with a callable `flip` property, but JavaScript doesn’t surface this information in a way that we can check while the code is running. The only way in pure JavaScript to tell what `fn` does with a particular value is to call it and see what happens. This kind of behavior makes it hard to predict what code will do before it runs, which means it’s harder to know what your code is going to do while you’re writing it.
</details>

Nhìn theo cách này, một kiểu là khái niệm mô tả giá trị nào có thể được chuyển tới `fn` và giá trị nào sẽ bị lỗi. JavaScript chỉ thực sự cung cấp kiểu _động_ - chạy mã để xem điều gì xảy ra.

<details>
  <summary>English version</summary>

  > Seen in this way, a type is the concept of describing which values can be passed to `fn` and which will crash. JavaScript only truly provides _dynamic_ typing - running the code to see what happens.
</details>

Giải pháp thay thế là sử dụng hệ thống kiểu _tĩnh_ để đưa ra dự đoán về những gì mã được mong đợi trước khi nó chạy.

<details>
  <summary>English version</summary>

  > The alternative is to use a _static_ type system to make predictions about what code is expected before it runs.
</details>

## Kiểm tra kiểu tĩnh

Hãy nghĩ lại về `TypeError` mà chúng ta đã có trước đó khi cố gắng gọi một `chuỗi` dưới dạng một hàm. _Đa số mọi người_ không muốn gặp bất kỳ loại lỗi nào khi chạy mã của họ - những lỗi đó được coi là lỗi! Và khi chúng ta viết mã mới, chúng ta cố gắng hết sức để tránh các lỗi mới.

<details>
  <summary>English version</summary>

  > Think back to that `TypeError` we got earlier from trying to call a `string` as a function. _Most people_ don’t like to get any sorts of errors when running their code - those are considered bugs! And when we write new code, we try our best to avoid introducing new bugs.
</details>

Nếu chúng ta chỉ thêm một chút mã, lưu tệp của mình, chạy lại mã và ngay lập tức thấy lỗi, chúng ta có thể nhanh chóng giải quyết vấn đề; nhưng không phải lúc nào cũng vậy. Chúng ta có thể đã không kiểm tra tính năng này đủ kỹ lưỡng, vì vậy chúng ta có thể không bao giờ thực sự gặp phải một lỗi tiềm ẩn sẽ xảy ra! Hoặc nếu chúng ta đủ may mắn để chứng kiến lỗi, chúng ta có thể đã thực hiện tái cấu trúc lớn và thêm nhiều mã khác nhau mà chúng ta buộc phải tìm hiểu kỹ.

<details>
  <summary>English version</summary>

  > If we add just a bit of code, save our file, re-run the code, and immediately see the error, we might be able to isolate the problem quickly; but that’s not always the case. We might not have tested the feature thoroughly enough, so we might never actually run into a potential error that would be thrown! Or if we were lucky enough to witness the error, we might have ended up doing large refactorings and adding a lot of different code that we’re forced to dig through.
</details>

Lý tưởng nhất là chúng ta có thể có một công cụ giúp chúng ta tìm ra những lỗi này _trước_ khi mã của chúng ta chạy. Đó là những gì một trình kiểm tra kiểu tĩnh như TypeScript làm. _Hệ thống kiểu tĩnh_ mô tả hình dạng và hành vi của giá trị của chúng ta sẽ như thế nào khi chúng ta chạy chương trình của mình. Một trình kiểm tra kiểu như TypeScript sử dụng thông tin đó và cho chúng ta biết khi nào mọi thứ có thể đi chệch hướng.

<details>
  <summary>English version</summary>

  > Ideally, we could have a tool that helps us find these bugs _before_ our code runs. That’s what a static type-checker like TypeScript does. _Static types systems_ describe the shapes and behaviors of what our values will be when we run our programs. A type-checker like TypeScript uses that information and tells us when things might be going off the rails.
</details>

![static-type-checking](../images/static-type-checking.png)

Chạy mẫu cuối cùng đó với TypeScript sẽ cung cấp cho chúng tôi một thông báo lỗi trước khi chúng tôi chạy mã ngay từ đầu.

<details>
  <summary>English version</summary>

  > Running that last sample with TypeScript will give us an error message before we run the code in the first place.
</details>

## Không có lỗi ngoại lệ

Cho đến nay, chúng ta đã thảo luận về một số vấn đề nhất định như lỗi thời gian chạy - các trường hợp thời gian chạy JavaScript cho chúng ta biết rằng nó nghĩ rằng điều gì đó vô nghĩa. Những trường hợp đó xảy ra vì [đặc tả ECMAScript](https://tc39.github.io/ecma262/) có hướng dẫn rõ ràng về cách ngôn ngữ sẽ hoạt động khi nó gặp sự cố không mong muốn.

<details>
  <summary>English version</summary>

  > So far we’ve been discussing certain things like runtime errors - cases where the JavaScript runtime tells us that it thinks something is nonsensical. Those cases come up because [the ECMAScript specification](https://tc39.github.io/ecma262/) has explicit instructions on how the language should behave when it runs into something unexpected.
</details>

Ví dụ: đặc tả nói rằng việc cố gắng gọi một thứ gì đó không thể gọi được sẽ gây ra lỗi. Có thể điều đó nghe giống như "hành vi rõ ràng", nhưng bạn có thể tưởng tượng rằng việc truy cập một thuộc tính không tồn tại trên một đối tượng cũng sẽ gây ra lỗi. Thay vào đó, JavaScript cung cấp cho chúng ta các hành vi khác nhau và trả về giá trị `undefined`:

<details>
  <summary>English version</summary>

  > For example, the specification says that trying to call something that isn’t callable should throw an error. Maybe that sounds like “obvious behavior”, but you could imagine that accessing a property that doesn’t exist on an object should throw an error too. Instead, JavaScript gives us different behavior and returns the value `undefined`:
</details>

```typescript
const user = {
  name: "Daniel",
  age: 26,
};
user.location; // returns undefined
```

Cuối cùng, hệ thống loại tĩnh phải thực hiện lệnh gọi mã nào sẽ được gắn cờ là lỗi trong hệ thống của nó, ngay cả khi JavaScript “hợp lệ” sẽ không gây ra lỗi ngay lập tức. Trong TypeScript, đoạn mã sau tạo ra lỗi về `location` không được xác định:

<details>
  <summary>English version</summary>

  > Ultimately, a static type system has to make the call over what code should be flagged as an error in its system, even if it’s “valid” JavaScript that won’t immediately throw an error. In TypeScript, the following code produces an error about location not being defined:
</details>

![location_is_not_exists](../images/location_is_not_exists.png)

Mặc dù đôi khi điều đó ngụ ý đánh đổi những gì bạn có thể thể hiện, nhưng mục đích là để tìm ra các lỗi hợp pháp trong các chương trình của chúng ta. Và TypeScript bắt được rất nhiều lỗi hợp pháp.

<details>
  <summary>English version</summary>

  > While sometimes that implies a trade-off in what you can express, the intent is to catch legitimate bugs in our programs. And TypeScript catches a lot of legitimate bugs.
</details>

Ví dụ: lỗi chính tả,

<details>
  <summary>English version</summary>

  > For example: typos,
</details>

```typescript
const announcement = "Hello World!";

// How quickly can you spot the typos?
announcement.toLocaleLowercase();
announcement.toLocalLowerCase();

// We probably meant to write this...
announcement.toLocaleLowerCase();
```

các hàm không thể gọi,

<details>
  <summary>English version</summary>

  > uncalled functions,
</details>

![uncalled-funcs](../images/uncalled-funcs.png)

hoặc các lỗi logic cơ bản.

<details>
  <summary>English version</summary>

  > or basic logic errors.
</details>

![logic-errors](../images/logic-errors.png)

## Types for Tooling

TypeScript có thể bắt lỗi khi chúng ta mắc lỗi trong mã của mình. Điều đó thật tuyệt, nhưng TypeScript cũng có thể ngăn chúng ta mắc phải những sai lầm đó ngay từ đầu.

<details>
  <summary>English version</summary>

  > TypeScript can catch bugs when we make mistakes in our code. That’s great, but TypeScript can also prevent us from making those mistakes in the first place.
</details>

Trình kiểm tra kiểu có thông tin để kiểm tra những thứ như liệu chúng ta có đang truy cập vào các thuộc tính phù hợp trên các biến và các thuộc tính khác hay không. Khi có thông tin đó, nó cũng có thể bắt đầu đề xuất những thuộc tính nào bạn có thể muốn sử dụng.

<details>
  <summary>English version</summary>

  > The type-checker has information to check things like whether we’re accessing the right properties on variables and other properties. Once it has that information, it can also start suggesting which properties you might want to use.
</details>

Điều đó có nghĩa là TypeScript cũng có thể được tận dụng để chỉnh sửa mã và trình kiểm tra kiểu lõi có thể cung cấp thông báo lỗi và hoàn thành mã khi bạn nhập vào trình soạn thảo. Đó là một phần của những gì mọi người thường đề cập đến khi họ nói về công cụ trong TypeScript.

<details>
  <summary>English version</summary>

  > That means TypeScript can be leveraged for editing code too, and the core type-checker can provide error messages and code completion as you type in the editor. That’s part of what people often refer to when they talk about tooling in TypeScript.
</details>

![suggestion](../images/suggestion.png)

TypeScript coi trọng việc sử dụng công cụ và điều đó vượt ra ngoài sự hoàn thiện và sai sót khi bạn nhập. Một trình soạn thảo hỗ trợ TypeScript có thể cung cấp "các bản sửa lỗi nhanh" để tự động sửa lỗi, tái cấu trúc để dễ dàng tổ chức lại mã và các tính năng điều hướng hữu ích để chuyển đến định nghĩa của một biến hoặc tìm tất cả các tham chiếu đến một biến nhất định. Tất cả điều này được xây dựng trên trình kiểm tra kiểu và hoàn toàn đa nền tảng, vì vậy hãy xem [trình soạn thảo yêu thích của bạn có hỗ trợ TypeScript](https://github.com/Microsoft/TypeScript/wiki/TypeScript-Editor-Support).

<details>
  <summary>English version</summary>

  > TypeScript takes tooling seriously, and that goes beyond completions and errors as you type. An editor that supports TypeScript can deliver “quick fixes” to automatically fix errors, refactorings to easily re-organize code, and useful navigation features for jumping to definitions of a variable, or finding all references to a given variable. All of this is built on top of the type-checker and is fully cross-platform, so it’s likely that [your favorite editor has TypeScript support available](https://github.com/Microsoft/TypeScript/wiki/TypeScript-Editor-Support).
</details>

## `tsc`, trình biên dịch TypeScript

Chúng ta đã nói về type-_checking_, nhưng chúng ta chưa sử dụng type-checker của mình. Hãy làm quen với người bạn mới `tsc` của chúng ta, trình biên dịch TypeScript. Trước tiên, chúng ta sẽ cần lấy nó qua npm.

<details>
  <summary>English version</summary>

  > We’ve been talking about type-_checking_, but we haven’t yet used our type-checker. Let’s get acquainted with our new friend `tsc`, the TypeScript compiler. First we’ll need to grab it via npm.
</details>

```shell
npm install -g typescript
```

> Điều này sẽ cài đặt Trình biên dịch TypeScript **tsc** trên toàn cục. Thay vào đó, bạn có thể sử dụng **npx** hoặc các công cụ tương tự nếu muốn chạy **tsc** từ gói node_modules cục bộ.

<details>
  <summary>English version</summary>

  > This installs the TypeScript Compiler **tsc** globally. You can use **npx** or similar tools if you’d prefer to run **tsc** from a local node_modules package instead.
</details>

Bây giờ chúng ta hãy chuyển đến một thư mục trống và thử viết chương trình TypeScript đầu tiên của chúng ta `hello.ts`

<details>
  <summary>English version</summary>

  > Now let’s move to an empty folder and try writing our first TypeScript program: `hello.ts:`
</details>

```typescript
// Greets the world.
console.log("Hello world!");
```

Lưu ý rằng không có kiểu cách nào ở đây; chương trình “hello world” này trông giống với những gì bạn viết cho chương trình “hello world” bằng JavaScript. Và bây giờ chúng ta hãy gõ kiểm tra nó bằng cách chạy lệnh `tsc` đã được cài đặt cho chúng ta bởi gói `typescript`.

<details>
  <summary>English version</summary>

  > Notice there are no frills here; this “hello world” program looks identical to what you’d write for a “hello world” program in JavaScript. And now let’s type-check it by running the command `tsc` which was installed for us by the `typescript` package.
</details>

```shell
tsc hello.ts
```

Tada!

Wait, “tada” what exactly? We ran tsc and nothing happened! Well, there were no type errors, so we didn’t get any output in our console since there was nothing to report.

But check again - we got some file output instead. If we look in our current directory, we’ll see a hello.js file next to hello.ts. That’s the output from our hello.ts file after tsc compiles or transforms it into a plain JavaScript file. And if we check the contents, we’ll see what TypeScript spits out after it processes a .ts file:
