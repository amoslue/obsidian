# rust

[[🔗 LINK]](https://course.rs/basic/base-type/statement-expression.html) — 语句与表达式 - Rust语言圣经(Rust Course)

- 表达式不能包含分号。这一点非常重要，一旦你在表达式后加上分号，它就会变成一条语句，再也不会返回一个值，请牢记！

[[🔗 LINK]](https://course.rs/basic/base-type/function.html) — 函数 - Rust语言圣经(Rust Course)

- 当用 ! 作函数返回类型的时候，表示该函数永不返回( diverge function )，特别的，这种语法往往用做会导致程序崩溃的函数

[[🔗 LINK]](https://course.rs/basic/ownership/ownership.html) — 所有权 - Rust语言圣经(Rust Course)

- Rust 中每一个值都被一个变量所拥有，该变量被称为值的所有者 一个值同时只能被一个变量所拥有，或者说一个值只能拥有一个所有者 当所有者(变量)离开作用域范围时，这个值将被丢弃(drop)
- 对于基本类型（存储在栈上），Rust 会自动拷贝，但是 String 不是基本类型，而且是存储在堆上的，因此不能自动拷贝。
- String 类型是一个复杂类型，由存储在栈中的堆指针、字符串长度、字符串容量共同组成
- 当 s1 赋予 s2 后，Rust 认为 s1 不再有效，因此也无需在 s1 离开作用域后 drop 任何东西，这就是把所有权从 s1 转移给了 s2，s1 在被赋予 s2 后就马上失效了。
- Rust 永远也不会自动创建数据的 “深拷贝”
- 原因是像整型这样的基本类型在编译时是已知大小的，会被存储在栈上，所以拷贝其实际的值是快速的。这意味着没有理由在创建变量 y 后使 x 无效（x、y 都仍然有效）。
- Rust 有一个叫做 Copy 的特征，可以用在类似整型这样在栈中存储的类型。如果一个类型拥有 Copy 特征，一个旧的变量在被赋值给其他变量后仍然可用
- 如下是一些 Copy 的类型：  所有整数类型，比如 u32。 布尔类型，bool，它的值是 true 和 false。 所有浮点数类型，比如 f64。 字符类型，char。 元组，当且仅当其包含的类型也都是 Copy 的时候。比如，(i32, i32) 是 Copy 的，但 (i32, String) 就不是。 不可变引用 &T ，例如转移所有权中的最后一个例子，但是注意: 可变引用 &mut T 是不可以 Copy的
- 

[[🔗 LINK]](https://course.rs/advance/lifetime/basic.html) — 认识生命周期 - Rust语言圣经(Rust Course)

- 生命周期，简而言之就是引用的有效作用域
- 生命周期标注并不会改变任何引用的实际作用域

[[🔗 LINK]](https://course.rs/basic/compound-type/enum.html) — 枚举 - Rust语言圣经(Rust Course)

- 如果使用 None 而不是 Some，需要告诉 Rust Option<T> 是什么类型的
- 只要一个值不是 Option<T> 类型，你就 可以 安全的认定它的值不为空

[[🔗 LINK]](https://course.rs/basic/compound-type/array.html) — 数组 - Rust语言圣经(Rust Course)

- 基本类型在Rust中赋值是以Copy的形式，这时候你就懂了吧，let array=[3;5]底层就是不断的Copy出来的，但很可惜复杂类型都没有深拷贝，只能一个个创建。

[[🔗 LINK]](https://course.rs/basic/match-pattern/all-patterns.html) — 全模式列表 - Rust语言圣经(Rust Course)

- 在之前，我们提到可以使用匹配守卫来解决模式中变量覆盖的问题，那里 match 表达式的模式中新建了一个变量而不是使用 match 之外的同名变量。内部变量覆盖了外部变量，意味着此时不能够使用外部变量的值，下面代码展示了如何使用匹配守卫修复这个问题。
- @（读作 at）运算符允许为一个字段绑定另外一个变量

[[🔗 LINK]](https://course.rs/basic/method.html) — 方法 Method - Rust语言圣经(Rust Course)

- 这种定义在 impl 中且没有 self 的函数被称之为关联函数： 因为它没有 self，不能用 f.read() 的形式调用，因此它是一个函数而不是方法，它又在 impl 中，与结构体紧密关联，因此称为关联函数。

- 因为是函数，所以不能用 . 的方式来调用，我们需要用 :: 来调用，例如 let sq = Rectangle::new(3, 3);。这个方法位于结构体的命名空间中：:: 语法用于关联函数和模块创建的命名空间

[[🔗 LINK]](https://course.rs/basic/trait/trait.html) — 特征 Trait - Rust语言圣经(Rust Course)

- 这里使用 trait 关键字来声明一个特征，Summary 是特征名。在大括号中定义了该特征的所有方法，在这个例子中是： fn summarize(&self) -> String。  特征只定义行为看起来是什么样的，而不定义行为具体是怎么样的。因此，我们只定义特征方法的签名，而不进行实现，此时方法签名结尾是 ;，而不是一个 {}。
- 你可以使用任何实现了 Summary 特征的类型作为该函数的参数，同时在函数体内，还可以调用该特征的方法，例如 summarize 方法。具体的说，可以传递 Post 或 Weibo 的实例来作为参数，而其它类如 String 或者 i32 的类型则不能用做该函数的参数，因为它们没有实现 Summary 特征。
- pub fn notify<T: Summary>(item1: &T, item2: &T) {}

[[🔗 LINK]](https://course.rs/basic/trait/generic.html#%E6%B3%9B%E5%9E%8B%E8%AF%A6%E8%A7%A3) — 泛型 Generics - Rust语言圣经(Rust Course)

fn largest<T>(list: &[T]) -> T {}

- 该泛型函数的作用是从列表中找出最大的值，其中列表中的元素类型为 T。首先 `largest<T>`
 对泛型参数 `T` 进行了声明，然后才在函数参数中进行使用该泛型参数 `list: &[T]`

[[🔗 LINK]](https://course.rs/basic/trait/trait-object.html) — 特征对象 - Rust语言圣经(Rust Course)

- dyn 关键字只用在特征对象的类型声明上，在创建时无需使用 dyn
- // 若 T 实现了 Draw 特征， 则调用该函数时传入的 Box<T> 可以被隐式转换成函数参数签名中的 Box<dyn Draw> fn draw1(x: Box<dyn Draw>) {     // 由于实现了 Deref 特征，Box 智能指针会自动解引用为它所包裹的值，然后调用该值对应的类型上定义的 `draw` 方法     x.draw(); }  fn draw2(x: &dyn Draw) {     x.draw(); }
- 无需在运行时检查一个值是否实现了特定方法或者担心在调用时因为值没有实现方法而产生错误。如果值没有实现特征对象所需的特征， 那么 Rust 根本就不会编译这些代码：
- 注意 dyn 不能单独作为特征对象的定义，例如下面的代码编译器会报错，原因是特征对象可以是任意实现了某个特征的类型，编译器在编译期不知道该类型的大小，不同的类型大小是不同的。
- 特征对象指向实现了 Draw 特征的类型的实例，也就是指向了 Button 或者 SelectBox 的实例，这种映射关系是存储在一张表中，可以在运行时通过特征对象找到具体调用的类型方法。  可以通过 & 引用或者 Box<T> 智能指针的方式来创建特征对象。
- draw1 函数的参数是 Box<dyn Draw> 形式的特征对象，该特征对象是通过 Box::new(x) 的方式创建的 draw2 函数的参数是 &dyn Draw 形式的特征对象，该特征对象是通过 &x 的方式创建的 dyn 关键字只用在特征对象的类型声明上，在创建时无需使用 dyn
- 注意 dyn 不能单独作为特征对象的定义，例如下面的代码编译器会报错，原因是特征对象可以是任意实现了某个特征的类型，编译器在编译期不知道该类型的大小，不同的类型大小是不同的。
- 泛型是在编译期完成处理的：编译器会为每一个泛型参数对应的具体类型生成一份代码，这种方式是静态分发(static dispatch)，因为是在编译期完成的，对于运行期性能完全没有任何影响。
- 简而言之，当类型 Button 实现了特征 Draw 时，类型 Button 的实例对象 btn 可以当作特征 Draw 的特征对象类型来使用，btn 中保存了作为特征对象的数据指针（指向类型 Button 的实例数据）和行为指针（指向 vtable）。
- 一定要注意，此时的 btn 是 Draw 的特征对象的实例，而不再是具体类型 Button 的实例，而且 btn 的 vtable 只包含了实现自特征 Draw 的那些方法（比如 draw），因此 btn 只能调用实现于特征 Draw 的 draw 方法，而不能调用类型 Button 本身实现的方法和类型 Button 实现于其他特征的方法。也就是说，btn 是哪个特征对象的实例，它的 vtable 中就包含了该特征的方法。
- 不是所有特征都能拥有特征对象，只有对象安全的特征才行。当一个特征的所有方法都有如下属性时，它的对象才是安全的：  方法的返回类型不能是 Self 方法没有任何泛型参数

[[🔗 LINK]](https://course.rs/basic/collections/hashmap.html) — KV 存储 HashMap - Rust语言圣经(Rust Course)

- or_insert 返回了 &mut v 引用，因此可以通过该可变引用直接修改 map 中对应的值 使用 count 引用时，需要先进行解引用 *count，否则会出现类型不匹配

[[🔗 LINK]](https://course.rs/basic/converse.html) — 类型转换 - Rust语言圣经(Rust Course)

- &i32 实现了特征 Trait， &mut i32 可以转换为 &i32，但是 &mut i32 依然无法作为 Trait 来使用。

[[🔗 LINK]](https://course.rs/basic/crate-module/crate.html) — 包 Crate - Rust语言圣经(Rust Course)

- 同一个包中不能有同名的类型，但是在不同包中就可以。

[[🔗 LINK]](https://course.rs/basic/crate-module/module.html) — 模块 Module - Rust语言圣经(Rust Course)