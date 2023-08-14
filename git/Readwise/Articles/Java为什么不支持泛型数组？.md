# Java为什么不支持泛型数组？

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article1.be68295a7e40.png)

## Metadata
- Author: [[zhihu.com]]
- Full Title: Java为什么不支持泛型数组？
- Category: #articles
- URL: https://www.zhihu.com/question/20928981/answer/117521433

## Highlights
- 但是！泛型有个什么问题呢？就是泛型是用**擦除（Erasure）**实现的，运行时类型参数会被擦掉。比如下面的例子，无论你声明的的是`List<String>`，还是`List<Integer>`或者[原生类](https://www.zhihu.com/search?q=%E5%8E%9F%E7%94%9F%E7%B1%BB&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A117521433%7D)`List`，容器实际类型都是`List<Object>`。 **所以泛型实际上都是[狼外婆](https://www.zhihu.com/search?q=%E7%8B%BC%E5%A4%96%E5%A9%86&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A117521433%7D)，它看上去像外婆，但实际上是大灰狼。**
  // 以下三个容器实际类型都是List<Object>
  List<String> strList = new ArrayList<String>(); 
  List<Integer> intList = new ArrayList<Integer>();
  List rawList = new ArrayList();
  所以数组小鸭子遇到泛型狼外婆就要吃苦头了。对数组小鸭子`Object[]` 来说，`GrandMother<RealGrandMother>`和`GrandMother<Wolf>`运行时看起来都是`GrandMother`。 那小鸭子岂不是要被吃掉？ 所以有正义感的程序员哥哥就禁止掉了这件事。
  public static void main(String[] args) {
  GrandMother<RealGrandMother>[] gm = new GrandMother<RealGrandMother>[3]; // 真外婆
  Object[] ducks = gm; // 我们告诉数组小鸭子，只有见到外婆才能开门
  ducks[0] = new GrandMother<Wolf>(); // 运行时狼外婆看起来和真外婆一模一样
  RealGrandMother rgm = ducks[0].get(); // BOOM! 跳出一只狼外婆，小鸭子懵圈了
  } 
  唯一绕过限制，创建[泛型数组](https://www.zhihu.com/search?q=%E6%B3%9B%E5%9E%8B%E6%95%B0%E7%BB%84&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra=%7B%22sourceType%22%3A%22answer%22%2C%22sourceId%22%3A117521433%7D)的方式，是先创建一个原生类型数组，然后再强制转型。
  List[] ga = (List<Integer>[])new ArrayList[10]; ([View Highlight](https://read.readwise.io/read/01gyeb24a1bfyndb7y2xefsejh))
    - Note: java不能创建泛型数组的原因。
