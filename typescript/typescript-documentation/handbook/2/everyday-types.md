# Everyday Types

[Online Version](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)

Trong chương này, chúng ta sẽ đề cập đến một số kiểu giá trị phổ biến nhất mà bạn sẽ tìm thấy trong mã JavaScript và giải thích các cách tương ứng để mô tả các kiểu đó trong TypeScript. Đây không phải là một danh sách đầy đủ và các chương trong tương lai sẽ mô tả nhiều cách hơn để đặt tên và sử dụng các kiểu khác.

<details>
  <summary>English version</summary>

  > In this chapter, we’ll cover some of the most common types of values you’ll find in JavaScript code, and explain the corresponding ways to describe those types in TypeScript. This isn’t an exhaustive list, and future chapters will describe more ways to name and use other types.
</details>

Các kiểu cũng có thể xuất hiện trong nhiều _vị trí_ hơn là chỉ
_type annotations_. Khi chúng ta tìm hiểu về bản thân các kiểu, chúng ta cũng sẽ tìm hiểu về những nơi mà chúng ta có thể tham khảo các kiểu này để hình thành các cấu trúc mới.

<details>
  <summary>English version</summary>

  > Types can also appear in many more _places_ than just type annotations. As we learn about the types themselves, we’ll also learn about the places where we can refer to these types to form new constructs.
</details>

Chúng ta sẽ bắt đầu bằng cách xem xét các kiểu cơ bản và phổ biến nhất mà bạn có thể gặp khi viết mã JavaScript hoặc TypeScript. Những thứ này sau này sẽ tạo thành các khối xây dựng cốt lõi của nhiều kiểu phức tạp hơn.

<details>
  <summary>English version</summary>

  > We’ll start by reviewing the most basic and common types you might encounter when writing JavaScript or TypeScript code. These will later form the core building blocks of more complex types.
</details>

## Kiểu dữ liệu nguyên thủy: `string`, `number`, và `boolean`

JavaScript có ba kiểu [nguyên thủy](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) được sử dụng rất phổ biến: `string`, `number` và `boolean`. Mỗi kiểu có một kiểu tương ứng trong TypeScript. Như bạn có thể mong đợi, đây là những tên giống như bạn sẽ thấy nếu bạn đã sử dụng toán tử JavaScript `typeof` trên một giá trị của các kiểu đó:
   - `string` đại diện cho các giá trị chuỗi như `"Hello, world"`
   - `number` dành cho các số như `42`. JavaScript không có giá trị runtime đặc biệt cho số nguyên, vì vậy không có giá trị tương đương với `int` hoặc `float` - mọi thứ chỉ đơn giản là `number`
   - `boolean` dành cho hai giá trị `true` và `false`

<details>
  <summary>English version</summary>

  > JavaScript has three very commonly used [primitives](https://developer.mozilla.org/en-US/docs/Glossary/Primitive): `string`, `number`, and `boolean`. Each has a corresponding type in TypeScript. As you might expect, these are the same names you’d see if you used the JavaScript `typeof` operator on a value of those types:
  >   - `string` represents string values like `"Hello, world"`
  >   - `number` is for numbers like `42`. JavaScript does not have a special runtime value for integers, so there’s no equivalent to `int` or `float` - everything is simply `number`
  >   - `boolean` is for the two values `true` and `false`
</details>

> Tên kiểu **String**, **Number** và **Boolean** (bắt đầu bằng chữ in hoa) là hợp lệ, nhưng đề cập đến một số kiểu tích hợp đặc biệt sẽ rất hiếm khi xuất hiện trong mã của bạn. Tốt nhất _luôn_ sử dụng **string**, **number** hoặc **boolean** cho các kiểu.

<details>
  <summary>English version</summary>

  > The type names **String**, **Number**, and **Boolean** (starting with capital letters) are legal, but refer to some special built-in types that will very rarely appear in your code. _Always_ use **string**, **number**, or **boolean** for types.
</details>

## Arrays

Để chỉ định kiểu của một mảng như `[1, 2, 3]`, bạn có thể sử dụng cú pháp `number[]`; cú pháp này hoạt động cho bất kỳ kiểu nào (ví dụ: `string[]` là một mảng các chuỗi, v.v.). Bạn cũng có thể thấy điều này được viết là `Array<number>`, có nghĩa tương tự. Chúng ta sẽ tìm hiểu thêm về cú pháp `T<U>` khi chúng ta đề cập đến _generics_.

<details>
  <summary>English version</summary>

  > To specify the type of an array like `[1, 2, 3]`, you can use the syntax `number[]`; this syntax works for any type (e.g. `string[]` is an array of strings, and so on). You may also see this written as `Array<number>`, which means the same thing. We’ll learn more about the syntax `T<U>` when we cover _generics_.
</details>

> Lưu ý rằng **[number]** là một thứ khác; tham khảo phần về [Tuples](objects.md#tuple-types).

<details>
  <summary>English version</summary>

  > Note that **[number]** is a different thing; refer to the section on [Tuples](objects.md#tuple-types).
</details>

## any

TypeScript cũng có một kiểu đặc biệt, `any`, mà bạn có thể sử dụng bất cứ khi nào bạn không muốn một giá trị cụ thể có thể gây ra lỗi khi kiểm tra kiểu.

<details>
  <summary>English version</summary>

  > TypeScript also has a special type, `any`, that you can use whenever you don’t want a particular value to cause typechecking errors.
</details>

Khi một giá trị thuộc kiểu `any`, bạn có thể truy cập vào bất kỳ thuộc tính nào của nó (lần lượt sẽ là loại `any`), gọi nó như một hàm, gán nó cho (hoặc từ) một giá trị thuộc bất kỳ loại nào, hoặc khá nhiều thứ khác hợp lệ về mặt cú pháp:

<details>
  <summary>English version</summary>

  > When a value is of type `any`, you can access any properties of it (which will in turn be of type `any`), call it like a function, assign it to (or from) a value of any type, or pretty much anything else that’s syntactically legal:
</details>

```typescript
let obj: any = { x: 0 };
// None of the following lines of code will throw compiler errors.
// Using `any` disables all further type checking, and it is assumed
// you know the environment better than TypeScript.
obj.foo();
obj();
obj.bar = 100;
obj = "hello";
const n: number = obj;
```

Kiểu `any` hữu ích khi bạn không muốn viết ra một kiểu dài dòng chỉ để thuyết phục TypeScript rằng một dòng mã cụ thể là được.

<details>
  <summary>English version</summary>

  > The `any` type is useful when you don’t want to write out a long type just to convince TypeScript that a particular line of code is okay.
</details>

### noImplicitAny

Khi bạn không chỉ định một kiểu và TypeScript không thể suy ra nó từ ngữ cảnh, trình biên dịch thường sẽ mặc định thành `any`.

<details>
  <summary>English version</summary>

  > When you don’t specify a type, and TypeScript can’t infer it from context, the compiler will typically default to `any`.
</details>

Tuy nhiên, bạn thường muốn tránh điều này vì `any` không được kiểm tra kiểu. Sử dụng cờ trình biên dịch [noImplicitAny](../../tsconfig.md#no-implicit-any---noimplicitany) để gắn cờ tồn tại bất kỳ kiểu `any` nào trong đoạn mã đều là lỗi.

<details>
  <summary>English version</summary>

  > You usually want to avoid this, though, because `any` isn’t type-checked. Use the compiler flag [noImplicitAny](../../tsconfig.md#no-implicit-any---noimplicitany) to flag any implicit `any` as an error.
</details>

## Type Annotations on Variables

Khi bạn khai báo một biến bằng cách sử dụng `const`, `var` hoặc `let`, bạn có thể tùy chọn thêm _type annotatio_ để chỉ định rõ ràng kiểu của biến:

<details>
  <summary>English version</summary>

  > When you declare a variable using `const`, `var`, or `let`, you can optionally add a type annotation to explicitly specify the type of the variable:
</details>

```typescript
let myName: string = "Alice";
```

> TypeScript không sử dụng khai báo kiểu “kiểu ở bên trái” như **int x = 0;** Chú thích kiểu sẽ luôn đi _sau_ thứ được nhập.

<details>
  <summary>English version</summary>

  > TypeScript doesn’t use “types on the left”-style declarations like **int x = 0;** Type annotations will always go _after_ the thing being typed.
</details>

Tuy nhiên, trong hầu hết các trường hợp, điều này là không cần thiết. Bất cứ khi nào có thể, TypeScript cố gắng tự động _suy luận_ các kiểu trong mã của bạn. Ví dụ: kiểu của một biến được suy ra dựa trên kiểu của bộ khởi tạo của nó:

<details>
  <summary>English version</summary>

  > In most cases, though, this isn’t needed. Wherever possible, TypeScript tries to automatically _infer_ the types in your code. For example, the type of a variable is inferred based on the type of its initializer:
</details>

```typescript
// No type annotation needed -- 'myName' inferred as type 'string'
let myName = "Alice";
```

Đối với hầu hết các phần, bạn không cần phải học rõ ràng các quy tắc suy luận. Nếu bạn đang bắt đầu, hãy thử sử dụng ít _type annotations_ hơn bạn nghĩ - bạn có thể ngạc nhiên về số lượng mà bạn cần để TypeScript có thể hiểu đầy đủ những gì đang xảy ra.

<details>
  <summary>English version</summary>

  > For the most part you don’t need to explicitly learn the rules of inference. If you’re starting out, try using fewer type annotations than you think - you might be surprised how few you need for TypeScript to fully understand what’s going on.
</details>

## Hàm

Các hàm là phương tiện chính để truyền dữ liệu trong JavaScript. TypeScript cho phép bạn chỉ định kiểu của cả giá trị đầu vào và đầu ra của các hàm.

<details>
  <summary>English version</summary>

  > Functions are the primary means of passing data around in JavaScript. TypeScript allows you to specify the types of both the input and output values of functions.
</details>

### Type Annotations Tham số

Khi bạn khai báo một hàm, bạn có thể thêm _type annotations_ sau mỗi tham số để khai báo kiểu tham số mà hàm chấp nhận. _Type annotations_ tham số đi sau tên tham số:

<details>
  <summary>English version</summary>

  > When you declare a function, you can add type annotations after each parameter to declare what types of parameters the function accepts. Parameter type annotations go after the parameter name:
</details>

```typescript
// Parameter type annotation
function greet(name: string) {
  console.log("Hello, " + name.toUpperCase() + "!!");
}
```

Khi một tham số có _type annotation_, các đối số cho hàm đó sẽ được kiểm tra:

<details>
  <summary>English version</summary>

  > When a parameter has a type annotation, arguments to that function will be checked:
</details>

![func-param-type-inno](../../images/func-param-type-inno.png)

> Ngay cả khi bạn không có _type annotation_ trên các tham số của mình, TypeScript vẫn sẽ kiểm tra xem bạn đã chuyển đúng số lượng tham số chưa.

<details>
  <summary>English version</summary>

  > Even if you don’t have type annotations on your parameters, TypeScript will still check that you passed the right number of arguments.
</details>

### Type Annotations Trả về

Bạn cũng có thể thêm _type annotations_ trả về. Các _type annotations_ trả về xuất hiện sau danh sách tham số:

<details>
  <summary>English version</summary>

  > You can also add return type annotations. Return type annotations appear after the parameter list:
</details>

```typescript
function getFavoriteNumber(): number {
  return 26;
}
```

Giống như _type annotations_ biến, bạn thường không cần _type annotations_ trả về vì TypeScript sẽ suy ra kiểu trả về của hàm dựa trên các câu lệnh `return` của nó. _Type annotations_ trong ví dụ trên không thay đổi bất kỳ điều gì. Một số cơ sở mã sẽ chỉ định rõ ràng kiểu trả về cho mục đích tài liệu, để ngăn chặn những thay đổi ngẫu nhiên hoặc chỉ vì sở thích cá nhân.

<details>
  <summary>English version</summary>

  > Much like variable type annotations, you usually don’t need a return type annotation because TypeScript will infer the function’s return type based on its `return` statements. The type annotation in the above example doesn’t change anything. Some codebases will explicitly specify a return type for documentation purposes, to prevent accidental changes, or just for personal preference.
</details>

### Hàm Anonymous

Hàm ẩn danh hơi khác một chút so với khai báo hàm. Khi một hàm xuất hiện ở nơi mà TypeScript có thể xác định cách nó sẽ được gọi, các tham số của hàm đó sẽ tự động được cung cấp theo kiểu.

<details>
  <summary>English version</summary>

  > Anonymous functions are a little bit different from function declarations. When a function appears in a place where TypeScript can determine how it’s going to be called, the parameters of that function are automatically given types.
</details>

Đây là một ví dụ:

<details>
  <summary>English version</summary>

  > Here’s an example:
</details>

![func-anonymous](../../images/func-anonymous.png)

Mặc dù tham số `s` không có chú thích kiểu, TypeScript đã sử dụng các kiểu của hàm `forEach`, cùng với kiểu suy ra của mảng, để xác định kiểu mà `s` sẽ có.

<details>
  <summary>English version</summary>

  > Even though the parameter `s` didn’t have a type annotation, TypeScript used the types of the `forEach` function, along with the inferred type of the array, to determine the type `s` will have.
</details>

Quá trình này được gọi là _contextual typing_ vì _context_ mà hàm xuất hiện bên trong thông báo kiểu nó phải có.

<details>
  <summary>English version</summary>

  > This process is called _contextual typing_ because the _context_ that the function occurred within informs what type it should have.
</details>

Tương tự như các quy tắc suy luận, bạn không cần phải tìm hiểu rõ ràng cách điều này xảy ra, nhưng hiểu rằng điều đó _nhất định_ xảy ra có thể giúp bạn nhận thấy khi nào không cần _type annotations_. Sau đó, chúng ta sẽ xem thêm các ví dụ về cách ngữ cảnh mà một giá trị xuất hiện có thể ảnh hưởng đến kiểu của nó.

<details>
  <summary>English version</summary>

  > Similar to the inference rules, you don’t need to explicitly learn how this happens, but understanding that it _does_ happen can help you notice when type annotations aren’t needed. Later, we’ll see more examples of how the context that a value occurs in can affect its type.
</details>

## Object Types

Ngoài kiểu nguyên thủy, kiểu phổ biến nhất mà bạn sẽ gặp là _object type_. Điều này đề cập đến bất kỳ giá trị JavaScript nào có thuộc tính, gần như là tất cả chúng! Để xác định một kiểu đối tượng, chúng ta chỉ cần liệt kê các thuộc tính của nó và các kiểu của chúng.

<details>
  <summary>English version</summary>

  > Apart from primitives, the most common sort of type you’ll encounter is an _object type_. This refers to any JavaScript value with properties, which is almost all of them! To define an object type, we simply list its properties and their types.
</details>

Ví dụ: đây là một hàm nhận một đối tượng _point-like_:

<details>
  <summary>English version</summary>

  > For example, here’s a function that takes a point-like object:
</details>

```typescript
// The parameter's type annotation is an object type
function printCoord(pt: { x: number; y: number }) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
printCoord({ x: 3, y: 7 });
```

Ở đây, chúng ta đã thêm _type annotations_ cho tham số với một kiểu có hai thuộc tính - `x` và `y` - cả hai đều thuộc kiểu `số`. Bạn có thể sử dụng `,` hoặc `;` để phân tách các thuộc tính và dấu phân tách cuối cùng là tùy chọn dù dùng cách nào.

<details>
  <summary>English version</summary>

  > Here, we annotated the parameter with a type with two properties - `x` and `y` - which are both of type `number`. You can use `,` or `;` to separate the properties, and the last separator is optional either way.
</details>

Phần kiểu của mỗi thuộc tính cũng là tùy chọn. Nếu bạn không chỉ định một kiểu, nó sẽ được giả định là `any`.

<details>
  <summary>English version</summary>

  > The type part of each property is also optional. If you don’t specify a type, it will be assumed to be `any`.
</details>

### Thuộc tính tùy chọn

Các kiểu đối tượng cũng có thể chỉ định rằng một số hoặc tất cả các thuộc tính của chúng là `tùy chọn`. Để thực hiện việc này, hãy thêm dấu `?` Vào sau tên thuộc tính:

<details>
  <summary>English version</summary>

  > Object types can also specify that some or all of their properties are `optional`. To do this, add a `?` after the property name:
</details>

```typescript
function printName(obj: { first: string; last?: string }) {
  // ...
}
// Both OK
printName({ first: "Bob" });
printName({ first: "Alice", last: "Alisson" });
```

Trong JavaScript, nếu bạn truy cập một thuộc tính không tồn tại, bạn sẽ nhận được giá trị `undefined` chứ không phải là lỗi thời gian chạy. Do đó, khi bạn _truy xuất_ một thuộc tính tùy chọn, bạn sẽ phải kiểm tra `undefined` trước khi sử dụng nó.

<details>
  <summary>English version</summary>

  > In JavaScript, if you access a property that doesn’t exist, you’ll get the value `undefined` rather than a runtime error. Because of this, when you _read_ from an optional property, you’ll have to check for `undefined` before using it.
</details>

![obj-undefined](../../images/obj-undefined.png)

## Kiểu Tập hợp

Hệ thống kiểu của TypeScript cho phép bạn tạo các kiểu mới từ những kiểu hiện có bằng cách sử dụng nhiều toán tử. Giờ chúng ta đã biết cách viết một số kiểu, đã đến lúc bắt đầu _kết hợp_ chúng theo những cách thú vị.

<details>
  <summary>English version</summary>

  > TypeScript’s type system allows you to build new types out of existing ones using a large variety of operators. Now that we know how to write a few types, it’s time to start _combining_ them in interesting ways.
</details>

### Định nghĩa Kiểu Tập hợp

Cách đầu tiên để kết hợp các kiểu mà bạn có thể thấy là kiểu _tập hợp_. Kiểu tập hợp là kiểu được hình thành từ hai hoặc nhiều kiểu khác, đại diện cho các giá trị có thể là _bất kỳ kiểu nào_ trong số các kiểu đó. Chúng ta gọi mỗi kiểu này là _phần tử_ của tập hợp.

<details>
  <summary>English version</summary>

  > The first way to combine types you might see is a _union_ type. A union type is a type formed from two or more other types, representing values that may be _any one_ of those types. We refer to each of these types as the union’s _members_.
</details>

Hãy viết một hàm có thể hoạt động trên chuỗi hoặc số:

<details>
  <summary>English version</summary>

  > Let’s write a function that can operate on strings or numbers:
</details>

![union-type](../../images/union-type.png)

### Làm việc với Kiểu Tập hợp

Thật dễ dàng để _cung cấp_ một giá trị phù hợp với một kiểu tập hợp - chỉ cần cung cấp một kiểu phù hợp với bất kỳ phần tử nào của tập hợp. Nếu bạn _có_ một giá trị của kiểu tập hợp, bạn làm việc với nó như thế nào?

<details>
  <summary>English version</summary>

  > It’s easy to _provide_ a value matching a union type - simply provide a type matching any of the union’s members. If you _have_ a value of a union type, how do you work with it?
</details>

TypeScript sẽ chỉ cho phép một hoạt động nếu nó hợp lệ với _mọi_ phần tử của tập hợp. Ví dụ, nếu bạn có tập hợp `string | number`, bạn không thể sử dụng các phương thức chỉ có sẵn trên `string`:

<details>
  <summary>English version</summary>

  > TypeScript will only allow an operation if it is valid for _every_ member of the union. For example, if you have the union `string | number`, you can’t use methods that are only available on `string`:
</details>

![union-methods](../../images/union-methods.png)

Giải pháp là _narrow_ kết hợp với mã, giống như bạn làm trong JavaScript mà không có _type annotations_. _Narrowing_ xảy ra khi TypeScript có thể suy ra một kiểu cụ thể hơn cho một giá trị dựa trên cấu trúc của mã.

<details>
  <summary>English version</summary>

  > The solution is to _narrow_ the union with code, the same as you would in JavaScript without type annotations. _Narrowing_ occurs when TypeScript can deduce a more specific type for a value based on the structure of the code.
</details>

Ví dụ, TypeScript biết rằng chỉ một giá trị `string` sẽ có một `typeof` giá trị `"string"`:

<details>
  <summary>English version</summary>

  > For example, TypeScript knows that only a `string` value will have a `typeof` value `"string"`:
</details>

```typescript
function printId(id: number | string) {
  if (typeof id === "string") {
    // In this branch, id is of type 'string'
    console.log(id.toUpperCase());
  } else {
    // Here, id is of type 'number'
    console.log(id);
  }
}
```

Một ví dụ khác là sử dụng một hàm như `Array.isArray`:

<details>
  <summary>English version</summary>

  > Another example is to use a function like `Array.isArray`:
</details>

```typescript
function welcomePeople(x: string[] | string) {
  if (Array.isArray(x)) {
    // Here: 'x' is 'string[]'
    console.log("Hello, " + x.join(" and "));
  } else {
    // Here: 'x' is 'string'
    console.log("Welcome lone traveler " + x);
  }
}
```

Lưu ý rằng trong nhánh `else`, chúng ta không cần phải làm gì đặc biệt - nếu `x` không phải là `string[]`, thì nó phải là một `string`.

<details>
  <summary>English version</summary>

  > Notice that in the `else` branch, we don’t need to do anything special - if `x` wasn’t a `string[]`, then it must have been a `string`.
</details>

Đôi khi bạn sẽ có một tập hợp mà tất cả các phần tử đều có điểm chung. Ví dụ, cả mảng và chuỗi đều có phương thức `slice`. Nếu mọi phần tử trong tập hợp có thuộc tính chung, bạn có thể sử dụng thuộc tính đó mà không bị thu hẹp:

<details>
  <summary>English version</summary>

  > Sometimes you’ll have a union where all the members have something in common. For example, both arrays and strings have a `slice` method. If every member in a union has a property in common, you can use that property without narrowing:
</details>

```typescript
// Return type is inferred as number[] | string
function getFirstThree(x: number[] | string) {
  return x.slice(0, 3);
}
```

> Có thể gây nhầm lẫn rằng _tập hợp_ của các kiểu dường như có thuộc tính _giao nhau_ của các kiểu đó. Đây không phải là một sự tình cờ - cái tên _tập hợp_ xuất phát từ lý thuyết kiểu. _Tập hợp_ **number | string** được cấu tạo bằng cách lấy tập hợp của các _giá trị_ từ mỗi kiểu. Lưu ý rằng đã cho hai tập hợp với các dữ kiện tương ứng về mỗi tập hợp, chỉ _phần tử_ của các dữ kiện đó mới áp dụng cho _tập hợp_ của chính các tập hợp đó. Ví dụ: nếu chúng ta có một phòng gồm những người cao đội mũ và một phòng khác gồm những người nói tiếng Tây Ban Nha đội mũ, sau khi kết hợp các phòng đó, điều duy nhất chúng ta biết về _mọi người_ là họ phải đội mũ.

<details>
  <summary>English version</summary>

  > It might be confusing that a _union_ of types appears to have the _intersection_ of those types’ properties. This is not an accident - the name _union_ comes from type theory. The _union_ **number | string** is composed by taking the union of the _values_ from each type. Notice that given two sets with corresponding facts about each set, only the _intersection_ of those facts applies to the _union_ of the sets themselves. For example, if we had a room of tall people wearing hats, and another room of Spanish speakers wearing hats, after combining those rooms, the only thing we know about _every_ person is that they must be wearing a hat.
</details>

## Bí danh của kiểu

Chúng ta đã và đang sử dụng các kiểu đối tượng và kiểu tập hợp bằng cách viết chúng trực tiếp trong _type annotations_. Điều này rất tiện lợi, nhưng bạn thường muốn sử dụng cùng một loại nhiều lần và gọi nó bằng một tên duy nhất.

<details>
  <summary>English version</summary>

  > We’ve been using object types and union types by writing them directly in type annotations. This is convenient, but it’s common to want to use the same type more than once and refer to it by a single name.
</details>

_Bí danh của kiểu_ chính xác là như vậy - một _tên_ cho bất kỳ _kiểu_ nào. Cú pháp cho bí danh kiểu là:

<details>
  <summary>English version</summary>

  > A _type alias_ is exactly that - a _name_ for any _type_. The syntax for a type alias is:
</details>

```typescript
type Point = {
  x: number;
  y: number;
};

// Exactly the same as the earlier example
function printCoord(pt: Point) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}

printCoord({ x: 100, y: 100 });
```

Bạn thực sự có thể sử dụng bí danh của kiểu để đặt tên cho bất kỳ kiểu nào, không chỉ là kiểu đối tượng. Ví dụ: bí danh kiểu có thể đặt tên cho kiểu tập hợp:

<details>
  <summary>English version</summary>

  > You can actually use a type alias to give a name to any type at all, not just an object type. For example, a type alias can name a union type:
</details>

```typescript
type ID = number | string;
```

Lưu ý rằng bí danh _chỉ_ là bí danh - bạn không thể sử dụng bí danh của kiểu để tạo các “phiên bản” khác nhau/riêng biệt của cùng một kiểu. Khi bạn sử dụng bí danh, nó chính xác như thể bạn đã viết loại bí danh. Nói cách khác, mã này có thể _trông_ không hợp lệ, nhưng theo TypeScript thì được vì cả hai kiểu đều là bí danh cho cùng một kiểu:

<details>
  <summary>English version</summary>

  > Note that aliases are _only_ aliases - you cannot use type aliases to create different/distinct “versions” of the same type. When you use the alias, it’s exactly as if you had written the aliased type. In other words, this code might _look_ illegal, but is OK according to TypeScript because both types are aliases for the same type:
</details>

```typescript
type UserInputSanitizedString = string;

function sanitizeInput(str: string): UserInputSanitizedString {
  return sanitize(str);
}

// Create a sanitized input
let userInput = sanitizeInput(getInput());

// Can still be re-assigned with a string though
userInput = "new input";
```

## Interfaces

Khai báo _interface_ là một cách khác để đặt tên cho kiểu đối tượng:

<details>
  <summary>English version</summary>

  > An _interface declaration_ is another way to name an object type:
</details>

```typescript
interface Point {
  x: number;
  y: number;
}

function printCoord(pt: Point) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}

printCoord({ x: 100, y: 100 });
```

Giống như khi chúng ta sử dụng bí danh của kiểu ở trên, ví dụ này hoạt động giống như khi chúng ta sử dụng kiểu đối tượng ẩn danh. TypeScript chỉ quan tâm đến _kết cấu_ của giá trị mà chúng ta đã chuyển cho `printCoord` - nó chỉ quan tâm đến việc nó có các thuộc tính mong đợi. Chỉ quan tâm đến cấu trúc và khả năng của các kiểu là lý do tại sao chúng ta gọi TypeScript là một hệ thống kiểu kiểu _về mặt cấu trúc_.

<details>
  <summary>English version</summary>

  > Just like when we used a type alias above, the example works just as if we had used an anonymous object type. TypeScript is only concerned with the _structure_ of the value we passed to `printCoord` - it only cares that it has the expected properties. Being concerned only with the structure and capabilities of types is why we call TypeScript a _structurally_ typed type system.
</details>

### Sự khác biệt giữa bí danh của kiểu và interface

Bí danh của kiểu và interface rất giống nhau, và trong nhiều trường hợp, bạn có thể thoải mái lựa chọn giữa chúng. Hầu hết tất cả các tính năng của một `interface` đều có sẵn trong `kiểu`, điểm khác biệt chính là một loại không thể thêm các thuộc tính mới so với một interface luôn có thể mở rộng.

<details>
  <summary>English version</summary>

  > Type aliases and interfaces are very similar, and in many cases you can choose between them freely. Almost all features of an `interface` are available in `type`, the key distinction is that a type cannot be re-opened to add new properties vs an interface which is always extendable.
</details>

### Interface

Mở rộng interface

<details>
  <summary>English version</summary>

  > Extending an interface
</details>

```typescript
interface Animal {
  name: string
}

interface Bear extends Animal {
  honey: boolean
}

const bear = getBear()
bear.name
bear.honey
```

Thêm các trường mới vào interface hiện có

<details>
  <summary>English version</summary>

  > Adding new fields to an existing interface
</details>

```typescript
interface Window {
  title: string
}

interface Window {
  ts: TypeScriptAPI
}

const src = 'const a = "Hello World"';
window.ts.transpileModule(src, {});
```

### Type

Mở rộng một kiểu qua giao các tập hợp

<details>
  <summary>English version</summary>

  > Extending a type via intersections
</details>

```typescript
type Animal = {
  name: string
}

type Bear = Animal & {
  honey: boolean
}

const bear = getBear();
bear.name;
bear.honey;
```

Một kiểu không thể thay đổi sau khi được tạo

<details>
  <summary>English version</summary>

  > A type cannot be changed after being created
</details>

```typescript
type Window = {
  title: string
}

type Window = {
  ts: TypeScriptAPI
}

 // Error: Duplicate identifier 'Window'.
 ```


Bạn sẽ tìm hiểu thêm về những khái niệm này trong các chương sau, vì vậy đừng lo lắng nếu bạn chưa hiểu tất cả những khái niệm này ngay lập tức.

<details>
  <summary>English version</summary>

  > You’ll learn more about these concepts in later chapters, so don’t worry if you don’t understand all of these right away.
</details>

  - Trước phiên bản TypeScript 4.2, tên bí danh của kiểu _có thể_ xuất hiện trong thông báo lỗi, đôi khi thay cho kiểu ẩn danh tương đương (có thể có hoặc có thể không mong muốn). Các interface sẽ luôn có tên trong các thông báo lỗi.
   - Bí danh của kiểu có thể không tham gia vào việc hợp nhất khai báo, nhưng các interface thì có thể.
   - Interface chỉ được sử dụng để khai báo hình dạng của đối tượng, không được đổi tên kiểu nguyên thủy.
   - Tên interface sẽ _luôn luôn_ xuất hiện ở dạng ban đầu trong thông báo lỗi, nhưng _chỉ_ khi chúng được sử dụng theo tên.

<details>
  <summary>English version</summary>

  > - Prior to TypeScript version 4.2, type alias names _may_ appear in error messages, sometimes in place of the equivalent anonymous type (which may or may not be desirable). Interfaces will always be named in error messages.
  > - Type aliases may not participate in declaration merging, but interfaces can.
  > - Interfaces may only be used to declare the shapes of objects, not rename primitives.
  > - Interface names will _always_ appear in their original form in error messages, but _only_ when they are used by name.
</details>

Đối với hầu hết các phần, bạn có thể chọn dựa trên sở thích cá nhân và TypeScript sẽ cho bạn biết nếu nó cần một thứ gì đó làm kiểu khai báo khác. Nếu bạn muốn tự tìm tòi, hãy sử dụng `interface` cho đến khi bạn cần sử dụng các tính năng từ `kiểu`.

<details>
  <summary>English version</summary>

  > For the most part, you can choose based on personal preference, and TypeScript will tell you if it needs something to be the other kind of declaration. If you would like a heuristic, use `interface` until you need to use features from `type`.
</details>

## Type Assertions

Đôi khi bạn sẽ có thông tin về kiểu giá trị mà TypeScript không thể biết.

<details>
  <summary>English version</summary>

  > Sometimes you will have information about the type of a value that TypeScript can’t know about.
</details>

Ví dụ: nếu bạn đang sử dụng `document.getElementById`, TypeScript chỉ biết rằng điều này sẽ trả về một số kiểu `HTMLElement`, nhưng bạn có thể biết rằng trang của bạn sẽ luôn có một `HTMLCanvasElement` với một ID nhất định.

<details>
  <summary>English version</summary>

  > For example, if you’re using `document.getElementById`, TypeScript only knows that this will return some kind of `HTMLElement`, but you might know that your page will always have an `HTMLCanvasElement` with a given ID.
</details>

Trong trường hợp này, bạn có thể sử dụng _type assertion_ để chỉ định một loại cụ thể hơn:

<details>
  <summary>English version</summary>

  > In this situation, you can use a _type assertion_ to specify a more specific type:
</details>

```typescript
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
```

Giống như _type annotation_, _type assertion_ sẽ bị trình biên dịch xóa và sẽ không ảnh hưởng đến hoạt động runtime của mã của bạn.

<details>
  <summary>English version</summary>

  > Like a type annotation, type assertions are removed by the compiler and won’t affect the runtime behavior of your code.
</details>

Bạn cũng có thể sử dụng cú pháp dấu ngoặc nhọn (ngoại trừ nếu mã nằm trong file `.tsx`), tương đương:

<details>
  <summary>English version</summary>

  > You can also use the angle-bracket syntax (except if the code is in a `.tsx` file), which is equivalent:
</details>

```typescript
const myCanvas = <HTMLCanvasElement>document.getElementById("main_canvas");
```

> Nhắc nhở: Bởi vì _type assertions_ bị xóa trong thời gian biên dịch, không có kiểm tra thời gian chạy nào được liên kết với _type assertions_. Sẽ không có ngoại lệ hoặc **null** được tạo nếu xác nhận kiểu sai.

<details>
  <summary>English version</summary>

  > Reminder: Because type assertions are removed at compile-time, there is no runtime checking associated with a type assertion. There won’t be an exception or **null** generated if the type assertion is wrong.
</details>

TypeScript chỉ cho phép _type assertions_ chuyển đổi sang phiên bản _cụ thể hơn hoặc ít cụ thể hơn_ của một kiểu. Quy tắc này ngăn chặn các cưỡng chế "không thể" như:

<details>
  <summary>English version</summary>

  > TypeScript only allows type assertions which convert to a _more specific or less specific_ version of a type. This rule prevents “impossible” coercions like:
</details>

![assertions](../../images/assertions.png)

Đôi khi quy tắc này có thể quá thận trọng và sẽ không cho phép các cưỡng chế phức tạp hơn có thể hợp lệ. Nếu điều này xảy ra, bạn có thể sử dụng hai xác nhận, trước tiên cho `any` (hoặc `unknown`, mà chúng tôi sẽ giới thiệu sau), sau đó đến kiểu mong muốn:

<details>
  <summary>English version</summary>

  > Sometimes this rule can be too conservative and will disallow more complex coercions that might be valid. If this happens, you can use two assertions, first to `any` (or `unknown`, which we’ll introduce later), then to the desired type:
</details>

```typescript
const a = (expr as any) as T;
```

## Literal Types

Ngoài các kiểu chung `string` và `number`, chúng ta có thể tham khảo chuỗi và số _riêng_ ở các vị trí kiểu.

<details>
  <summary>English version</summary>

  > In addition to the general types `string` and `number`, we can refer to _specific_ strings and numbers in type positions.
</details>

Một cách để suy nghĩ về điều này là xem xét cách JavaScript đi kèm với các cách khác nhau để khai báo một biến. Cả `var` và `let` đều cho phép thay đổi những gì được giữ bên trong biến, còn `const` thì không. Điều này được phản ánh trong cách TypeScript tạo ra các kiểu cho các chữ.

<details>
  <summary>English version</summary>

  > One way to think about this is to consider how JavaScript comes with different ways to declare a variable. Both `var` and `let` allow for changing what is held inside the variable, and `const` does not. This is reflected in how TypeScript creates types for literals.
</details>

![literal-1](../../images/literal-1.png)

Tự bản thân, các kiểu chữ không có giá trị lắm:

<details>
  <summary>English version</summary>

  > By themselves, literal types aren’t very valuable:
</details>

![literal-2](../../images/literal-2.png)

Việc có một biến chỉ có thể có một giá trị cũng chẳng ích lợi gì!

<details>
  <summary>English version</summary>

  > It’s not much use to have a variable that can only have one value!
</details>

Nhưng bằng cách kết hợp các ký tự thành các tập hợp, bạn có thể thể hiện một khái niệm hữu ích hơn nhiều - ví dụ: các hàm chỉ chấp nhận một tập hợp nhất định của các giá trị đã biết:

<details>
  <summary>English version</summary>

  > But by combining literals into unions, you can express a much more useful concept - for example, functions that only accept a certain set of known values:
</details>

![literal-3](../../images/literal-3.png)

Các kiểu chữ số hoạt động theo cùng một cách:

<details>
  <summary>English version</summary>

  > Numeric literal types work the same way:
</details>

```typescript
function compare(a: string, b: string): -1 | 0 | 1 {
  return a === b ? 0 : a > b ? 1 : -1;
}
```

Tất nhiên, bạn có thể kết hợp chúng với các loại không phải chữ:

<details>
  <summary>English version</summary>

  > Of course, you can combine these with non-literal types:
</details>

![literal-4](../../images/literal-4.png)

Còn một loại chữ nữa: chữ boolean. Chỉ có hai kiểu chữ boolean và như bạn có thể đoán, chúng là kiểu `true` và `false`. Bản thân kiểu `boolean` thực ra chỉ là một bí danh cho tập hợp `true | false`.

<details>
  <summary>English version</summary>

  > There’s one more kind of literal type: boolean literals. There are only two boolean literal types, and as you might guess, they are the types true and false. The type boolean itself is actually just an alias for the union true | false.
</details>

### Suy luận Literal

Khi bạn khởi tạo một biến với một đối tượng, TypeScript giả định rằng các thuộc tính của đối tượng đó có thể thay đổi giá trị sau này. Ví dụ: nếu bạn viết mã như thế này:

<details>
  <summary>English version</summary>

  > When you initialize a variable with an object, TypeScript assumes that the properties of that object might change values later. For example, if you wrote code like this:
</details>

```typescript
const obj = { counter: 0 };
if (someCondition) {
  obj.counter = 1;
}
```

TypeScript không cho rằng việc gán `1` cho một trường mà trước đó có `0` là một lỗi. Một cách khác để nói điều này là `obj.counter` phải có kiểu `number`, không phải `0`, bởi vì các kiểu được sử dụng để xác định cả hành vi _đọc_ và _viết_.

<details>
  <summary>English version</summary>

  > TypeScript doesn’t assume the assignment of `1` to a field which previously had `0` is an error. Another way of saying this is that `obj.counter` must have the type `number`, not `0`, because types are used to determine both _reading_ and _writing_ behavior.
</details>

Điều tương tự cũng áp dụng cho các chuỗi:

<details>
  <summary>English version</summary>

  > The same applies to strings:
</details>

![literal-5](../../images/literal-5.png)

Trong ví dụ trên `req.method` được suy ra là `string`, không phải `"GET"`. Vì mã có thể được đánh giá giữa việc tạo `req` và lệnh gọi `handleRequest` có thể gán một chuỗi mới như `"GUESS"` thành `req.method`, nên TypeScript coi mã này có lỗi.

<details>
  <summary>English version</summary>

  > In the above example `req.method` is inferred to be `string`, not `"GET"`. Because code can be evaluated between the creation of `req` and the call of `handleRequest` which could assign a new string like `"GUESS"` to `req.method`, TypeScript considers this code to have an error.
</details>

Có hai cách để giải quyết vấn đề này.

<details>
  <summary>English version</summary>

  > There are two ways to work around this.
</details>

  1. Bạn có thể thay đổi suy luận bằng cách thêm _type assertion_ vào một trong hai vị trí:

<details>
  <summary>English version</summary>

  > 1. You can change the inference by adding a type assertion in either location:
</details>

```typescript
// Change 1:
const req = { url: "https://example.com", method: "GET" as "GET" };
// Change 2
handleRequest(req.url, req.method as "GET");
```

  Thay đổi 1 có nghĩa là “Tôi dự định cho `req.method` luôn có kiểu _literal_ `"GET"`”, ngăn cản việc gán `"GUESS"` cho trường đó sau đó. Thay đổi 2 có nghĩa là “Tôi biết vì những lý do khác mà `req.method` có giá trị `"GET"`”.

<details>
  <summary>English version</summary>

  > Change 1 means “I intend for `req.method` to always have the _literal_ type `"GET"`”, preventing the possible assignment of `"GUESS"` to that field after. Change 2 means “I know for other reasons that `req.method` has the value `"GET"`”.
</details>

  2. Bạn có thể sử dụng `as const` để chuyển đổi toàn bộ đối tượng thành kiểu chữ:

<details>
  <summary>English version</summary>

  > 2. You can use `as const` to convert the entire object to be type literals:
</details>

```typescript
const req = { url: "https://example.com", method: "GET" } as const;
handleRequest(req.url, req.method);
```

Hậu tố `as const` hoạt động giống như `const` nhưng đối với hệ thống kiểu, đảm bảo rằng tất cả các thuộc tính được gán kiểu chữ thay vì một phiên bản tổng quát hơn như `string` hoặc `number`.

<details>
  <summary>English version</summary>

  > The `as const` suffix acts like `const` but for the type system, ensuring that all properties are assigned the literal type instead of a more general version like `string` or `number`.
</details>

## `null` and `undefined`

JavaScript có hai giá trị nguyên thủy được sử dụng để báo hiệu giá trị vắng mặt hoặc chưa được khởi tạo: `null` và `undefined`.

<details>
  <summary>English version</summary>

  > JavaScript has two primitive values used to signal absent or uninitialized value: `null` and `undefined`.
</details>

TypeScript có hai _kiểu_ tương ứng với tên giống nhau. Các loại này hoạt động như thế nào phụ thuộc vào việc bạn có bật tùy chọn [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) hay không.

<details>
  <summary>English version</summary>

  > TypeScript has two corresponding _types_ by the same names. How these types behave depends on whether you have the [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) option on.
</details>

### `strictNullChecks` off

Với [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) _off_, các giá trị có thể là `null` hoặc `undefined` vẫn có thể được truy cập bình thường và các giá trị `null` và `undefined` có thể được gán cho một thuộc tính thuộc bất kỳ kiểu nào. Điều này tương tự như cách các ngôn ngữ không có kiểm tra null (ví dụ: C#, Java) hoạt động. Việc thiếu kiểm tra các giá trị này có xu hướng là một nguồn lỗi chính; chúng tôi luôn khuyến nghị mọi người nên bật [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) nếu có thể.

<details>
  <summary>English version</summary>

  > With [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) _off_, values that might be `null` or `undefined` can still be accessed normally, and the values `null` and `undefined` can be assigned to a property of any type. This is similar to how languages without null checks (e.g. C#, Java) behave. The lack of checking for these values tends to be a major source of bugs; we always recommend people turn [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) on if it’s practical to do so in their codebase.
</details>

### `strictNullChecks` on

Với [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) _on_, khi giá trị là `null` hoặc `undefined`, bạn sẽ cần phải kiểm tra các giá trị đó trước khi sử dụng các phương thức hoặc các thuộc tính trên giá trị đó. Cũng giống như việc kiểm tra `undefined` trước khi sử dụng thuộc tính tùy chọn, chúng ta có thể sử dụng _narrowing_ để kiểm tra các giá trị có thể là `null`:

<details>
  <summary>English version</summary>

  > With [strictNullChecks](../../tsconfig.md#strict-null-checks---strictnullchecks) _on_, when a value is `null` or `undefined`, you will need to test for those values before using methods or properties on that value. Just like checking for `undefined` before using an optional property, we can use _narrowing_ to check for values that might be `null`:
</details>

```typescript
function doSomething(x: string | null) {
  if (x === null) {
    // do nothing
  } else {
    console.log("Hello, " + x.toUpperCase());
  }
}
```

### Toán tử Non-null Assertion (Hậu tố `!`)

TypeScript cũng có một cú pháp đặc biệt để loại bỏ `null` và `undefined` khỏi một kiểu mà không cần thực hiện bất kỳ kiểm tra rõ ràng nào. Viết `!`

<details>
  <summary>English version</summary>

  > TypeScript also has a special syntax for removing `null` and `undefined` from a type without doing any explicit checking. Writing `!` after any expression is effectively a type assertion that the value isn’t `null` or `undefined`:
</details>

```typescript
function liveDangerously(x?: number | null) {
  // No error
  console.log(x!.toFixed());
}
```

Cũng giống như các _type assertions_ khác, điều này không thay đổi hành vi runtime của mã của bạn, vì vậy điều quan trọng là chỉ sử dụng `!` Khi bạn biết rằng giá trị _không thể_ là `null` hoặc `undefined`.

<details>
  <summary>English version</summary>

  > Just like other type assertions, this doesn’t change the runtime behavior of your code, so it’s important to only use `!` when you know that the value _can’t_ be `null` or `undefined`.
</details>

## Enums

Enums là một tính năng được TypeScript thêm vào JavaScript cho phép mô tả một giá trị có thể là một trong một tập hợp các hằng số có thể được đặt tên. Không giống như hầu hết các tính năng của TypeScript, đây _không phải_ là một bổ sung cấp kiểu cho JavaScript nhưng là thứ được thêm vào ngôn ngữ và runtime. Bởi vì điều này, đó là một tính năng mà bạn nên biết là có tồn tại, nhưng có thể ngừng sử dụng trừ khi bạn chắc chắn. Bạn có thể đọc thêm về enum trong [Trang tham khảo enum](../enums.md).

<details>
  <summary>English version</summary>

  > Enums are a feature added to JavaScript by TypeScript which allows for describing a value which could be one of a set of possible named constants. Unlike most TypeScript features, this is _not_ a type-level addition to JavaScript but something added to the language and runtime. Because of this, it’s a feature which you should know exists, but maybe hold off on using unless you are sure. You can read more about enums in the [Enum reference page](../enums.md).
</details>

## Các kiểu nguyên thủy ít phổ biến hơn

Điều đáng nói là phần còn lại của các kiểu nguyên thủy trong JavaScript được thể hiện trong hệ thống kiểu. Mặc dù chúng tôi sẽ không đi sâu vào đây.

<details>
  <summary>English version</summary>

  > It’s worth mentioning the rest of the primitives in JavaScript which are represented in the type system. Though we will not go into depth here.
</details>

### bigint

Từ ES2020 trở đi, có một kiểu nguyên thủy trong JavaScript được sử dụng cho các số nguyên rất lớn, `BigInt`:

<details>
  <summary>English version</summary>

  > From ES2020 onwards, there is a primitive in JavaScript used for very large integers, `BigInt`:
</details>

```typescript
// Creating a bigint via the BigInt function
const oneHundred: bigint = BigInt(100);

// Creating a BigInt via the literal syntax
const anotherHundred: bigint = 100n;
```

Bạn có thể tìm hiểu thêm về BigInt trong [TypeScript 3.2 release notes](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-2.html#bigint).

<details>
  <summary>English version</summary>

  > You can learn more about BigInt in the [TypeScript 3.2 release notes](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-2.html#bigint).
</details>

### symbol

Có một kiểu nguyên thủy trong JavaScript được sử dụng để tạo một tham chiếu duy nhất trên toàn cục thông qua hàm `Symbol()`:

<details>
  <summary>English version</summary>

  > There is a primitive in JavaScript used to create a globally unique reference via the function `Symbol()`:
</details>

![symbol](../../images/symbol.png)

Bạn có thể tìm hiểu thêm về chúng trong [Trang tham khảo Symbols](../symbols.md).

<details>
  <summary>English version</summary>

  > You can learn more about them in [Symbols reference page](../symbols.md).
</details>

## Liên kết hữu dụng
- [Trước](basic-types.md) - The Basics - Bước đầu tiên khi học TypeScript: Các kiểu cơ bản.
- [Tiếp theo](narrowing.md) - Narrowing - Hiểu cách TypeScript sử dụng kiến thức JavaScript để giảm số lượng cú pháp kiểu trong các dự án của bạn.
