---
title: "客观、全面的比较 Rust 与 Go"
date: 2020-11-10T00:07:00+08:00
toc: true
isCJKLanguage: true
tags: 
  - Golang
  - Go
  - Rust
---

> 最近一年，将 Rust 和 Go 进行比较的不少，但不少都不公正，带感情色彩。而这篇文章客观、全面的分析对比了 Rust 和 Go，让你具体项目时选择最合适的。

Rust 还是 Go，哪个更好？你应该为下一个项目选择哪种语言，为什么？两者在性能，简单性，安全性，功能，规模和并发性等方面如何比较？它们有什么共同点，并且在根本上有何不同？来自 [For the Go of Love](https://bitfieldconsulting.com/books/) 系列图书的作者，友好而公正的比较 Rust 和 Golang。

## Rust 和 Go 都很棒

首先，非常重要的一点是，Go 和 Rust 都是绝对优秀的编程语言。它们是现代的，强大的，被广泛采用的，并且具有出色的性能。你可能已经阅读了一些文章和博客文章，目的是说服 Go 比 Rust 更好，反之亦然。但这确实没有道理；每种编程语言都代表一组权衡。每种语言针对不同的事物进行了优化，因此，应根据适合你的语言以及你要解决的问题来确定语言的选择。

在本文中，我将简要概述我认为 Go 是理想的选择，以及我认为 Rust 是更好的选择的地方。不过，理想情况下，你应该对这两种语言都有一定的了解。尽管它们的语法和样式差异很大，但 Rust 和 Go 都是用于构建软件的一流工具。话虽如此，让我们仔细看看这两种语言。

## 相似之处

Rust 和 Go 有很多共同点，这是你经常听到他们一起被提及的原因之一。两种语言的共同目标是什么？

> Rust 是一种专注于安全性和性能的低级静态类型多范式编程语言。*—*[Gints Dreimanis](https://serokell.io/blog/rust-guide)

> Go 是一种开放源代码编程语言，可轻松构建简单，可靠和高效的软件。—[Golang.org](https://golang.org/)

### 内存安全

Go 和 Rust 都属于优先考虑内存安全性的现代编程语言。数十年来，使用 C 和 C++ 等较旧的语言已经很清楚，导致错误和安全漏洞的最大原因之一是不安全或不正确地访问内存。 Rust 和 Go 以不同的方式处理此问题，但是两者的目的都是要比其他有关内存管理的语言更聪明，更安全，并帮助你编写正确且性能良好的程序。

### 快速，紧凑的可执行文件

它们都是编译语言，这意味着你的程序直接转换为可执行的机器代码，因此你可以将程序作为单个二进制文件进行部署；与 Python 和 Ruby 等解释型语言不同，你无需随程序一起分发解释器，大量库和依赖项，这是一大优势。与解释型语言相比，这也使 Rust 和 Go 程序都非常快。

### 通用语言

Rust 和 Go 都是功能强大，可扩展的通用编程语言，你可以使用它们来开发各种现代软件，从Web应用程序到分布式微服务，或者从嵌入式微控制器到移动应用程序。两者都具有出色的标准库和蓬勃发展的第三方生态系统，以及强大的商业支持和庞大的用户群。它们都已经存在了很多年，并将在未来几年继续被广泛使用。今天学习 Go 或 Rust 将是你的时间和精力的明智投资。

### 务实（Pragmatic）的编程风格

两种语言都不是纯函数式语言（例如 Scala 或 Elixir），也不是全面面向对象的语言（例如 Java 和 C#）。相反，尽管 Go 和 Rust 都具有与函数和面向对象的编程相关的功能，但它们都是务实的语言，旨在以最合适的方式解决问题，而不是强迫你采用特定的处理方式。 （不过，如果你喜欢函数式编程风格，则在 Rust 中会发现更多的函数式特性，因为 Rust 的函数式功能比 Go 多得多。）

> 我们可以讨论什么是“面向对象”语言，但是公平地说，Go 或 Rust 中都没有 C++，Java 或 C# 用户期望的面向对象编程风格。—Jack Mott

### 大规模发展

Rust 和 Go 都具有一些有用的特性，这使其适合于大型编程，包括大型团队，大型代码库，或两者兼而有之。

例如，尽管 C 程序员多年来一直在争论括号的位置，以及是否应使用制表符或空格使代码缩进，但 Rust 和 Go 都通过使用标准格式工具（gofmt 用于 Go，rustfmt 用于 Rust）完全消除了此类问题。 它使用规范样式自动格式化你的代码。并不是说这种特殊的样式本身如此出色：而是 Rust 和 Go 程序员所欣赏的标准化。

> gofmt 的风格不是每个人的最爱，但 gofmt 是每个人的最爱。*—*[Rob Pike](https://www.youtube.com/watch?v=PAAkCSZUG1c&t=8m43s)

两种语言得分很高的另一个领域是构建管道（build pipeline）。两者都具有出色的内置高性能标准构建和依赖管理工具。不再需要为复杂的第三方构建系统而费力，也不必每两年学习一次新的。

> 在我早期的职业生涯中，具有 Java 和 Ruby 背景的 Go 和 Rust 代码构建工作似乎使我无法承受。当我在 Google 时，遇到用 Go 编写的服务感到很欣慰，因为我知道它易于构建和运行。 Rust 的情况也是如此，尽管我只是在较小的规模上进行了研究。我希望无限可配置的构建系统的日子已经一去不复返了，所有语言都附带了它们自己专用的构建工具，这些工具可以直接使用。*—*[Sam Rose](https://samwho.dev/)

## 那有什么大惊小怪的？

考虑到所有这些，并且看到这两种语言的设计和功能如此强大，你可能想知道所有的圣战是关于什么的（我也是）。人们为什么对 “Go vs Rust” 如此大惊小怪，陷入愤怒的社交媒体争吵中，并写了很长的博客文章，内容涉及只有白痴才会使用Rust，或者 Go 不是真正的编程语言等等。它可能会让他们感觉更好，但对于试图决定要为项目使用哪种语言的人，或者应该学习哪种语言来促进编程事业的人，这并不能完全为你提供帮助。明智的人不会根据谁喊得最多而做出重要的选择。

现在，让我们继续探讨一些成年人在某些方面可能会比较喜欢一种语言而不是另一种语言的问题。

## 性能

我们已经说过，Go 和 Rust 都能生成非常快的程序，因为它们被编译为本机代码，而无需通过解释器或虚拟机。但是，Rust 的性能特别出色，它可与 C 和 C++ 相媲美（C/C++ 通常被认为是性能最高的编译语言），但与这些较旧的语言不同，它还提供了内存安全性和并发安全性，而执行速度却基本没有任何成本。 Rust 还允许你创建复杂的抽象，而无需在运行时付出性能损失。

相比之下，尽管 Go 程序的性能也非常好，但是 Go 的主要目的是提高开发速度（包括编译），而不是提高执行速度。 Go 编译器不会花费很多时间来尝试生成尽可能高效的机器代码；它更关心快速编译大量代码。因此，Rust 通常会在运行时基准测试中击败 Go。

Rust 的运行时性能也始终如一且可预测，因为它不使用垃圾回收。 Go 的垃圾收集器非常高效，并且经过优化，可以使其 STW 的时间尽可能短（并且在每个新的 Go 版本中都变得更短）。但是垃圾回收不可避免地在程序的行为方式中引入了一些不可预测性，这在某些应用程序（例如嵌入式系统）中可能是一个严重的问题。

由于 Rust 旨在使程序员能够完全控制底层硬件，因此有可能将 Rust 程序优化为非常接近机器的最大理论性能。对于执行速度超过所有其他考虑因素的领域（例如游戏编程，操作系统内核，Web 浏览器组件和实时控制系统），Rust 使其成为绝佳的选择。

## 简单

如果没有人能弄清楚如何使用它，那么编程语言有多快也没关系。 Go 被故意认为是对 C++ 等语言不断增长的复杂性的一种反应。它的语法很少，关键字也不多，而且功能也很少。这意味着学习 Go 语言并不需要很长时间，你可以在其中编写有用的程序。

> Go 非常容易学习。我知道这是一个经常被吹捧的好处，但是我对能够这么快地提高生产力感到非常惊讶。多亏了语言，文档和工具，我实际上在两天之后就编写了有趣的，可提交的代码。— [Rust 程序员对 Go 的早期印象](https://medium.com/better-programming/early-impressions-of-go-from-a-rust-programmer-f4fd1074c410)

这里的关键词是简单。当然，简单（simple）与容易（easy）并不相同，但是简单的小型语言比复杂的大型语言更容易学习。要做的事情没有太多不同的方式，因此所有编写良好的 Go 代码看起来都一样。深入研究不熟悉的服务并了解其功能很容易。	

```go
fmt.Println("Gopher's Diner Breakfast Menu")
for dish, price := range menu {
    fmt.Println(dish, price)
}
```

尽管核心语言很小，但 Go 的标准库功能非常强大。这意味着你的学习曲线还需要包括所需的标准库部分，而不仅仅是Go语法。另一方面，将功能从语言中移出并移入标准库意味着你现在可以专注于仅学习与你相关的库。

Go 还被设计用于具有大型代码库和大型团队的大规模软件开发。在这种情况下，重要的是，新开发人员必须尽快上手。

> 使用 Go，你可以快速完成工作。 Go 是我使用过的最具生产力的语言之一。口头禅是：解决今天的实际问题。*—*[Matthias Endler](https://endler.dev/2017/go-vs-rust/)

## 特性

> 与其他几种编程语言相比，Rust 支持更多的复杂特性，因此，你可以用它实现更多的功能。例如，它支持泛型。*—*[Devathon](https://devathon.com/blog/rust-vs-go-which-programming-language-to-choose/)

Rust 专门设计为包含许多强大而有用的功能，以帮助程序员以最少的代码完成最多的工作。例如，Rust 的 match 功能使你可以非常简洁地编写灵活的表达逻辑：

```rust
fn is_prime(n: u64) -> bool {
    match n {
        0...1 => false,
        _ => !(2..n).any(|d| n % d == 0),
    }
}
```

由于 Rust 的功能很多，这意味着有很多东西要学习，尤其是在一开始的时候。但这没关系：在 C++ 或 Java 中也有很多东西要学习，而且你没有获得 Rust 附带的高级功能，例如内存安全性。批评 Rust 是一种复杂的语言，没有抓住重点：它被设计成具有表现力，这意味着具有许多功能，并且在许多情况下，这是编程语言所需要的。当然，这是一条学习曲线，但是一旦你开始使用它，就可以了。

> Rust 为准备接受更复杂的语法和语义（可能会带来更高的可读性成本）以换取最大可能的性能的程序员，与 C++ 和 D 竞争思想共享。*—*[Dave Cheney](https://dave.cheney.net/2015/07/02/why-go-and-rust-are-not-competitors)

## 并发

大多数语言都对并发编程提供某种形式的支持（一次执行多项操作），但是 Go 是专为这项工作而设计的。 Go 不使用操作系统线程，而是提供了一种轻量级的替代方案：goroutines。每个 goroutine 是一个独立执行的 Go 函数，Go 调度程序会将其映射到其控制下的 OS 线程之一。这意味着调度程序仅使用有限数量的 OS 线程即可非常有效地管理大量并发的goroutine。

因此，你可以在一个程序中运行数百万个并发 goroutine，而不会造成严重的性能问题。这使 Go 成为 Web 服务器和微服务等大规模并发应用程序的理想选择。

Go 还提供了快速，安全，有效的方式，goroutine 使用 channel 进行通信和共享数据。 Go 的并发支持设计良好，使用起来很愉快。通常很难对并发程序进行推理，而构建可靠，正确的并发程序对任何语言都是一个挑战。但是，由于它是从一开始就内置在语言中的，而不是事后才想到的，Go 中的并发编程简单、合理、良好的集成进语言中。

> Go 使构建易于分解的应用程序变得非常容易，该应用程序在作为一组微服务部署时充分利用了并发性。 Rust 也可以做这些事情，但是可以说有点困难。从某些方面来说，Rust 对防止与内存相关的安全漏洞的痴迷意味着程序员必须竭尽全力来执行使用其他语言（包括 Go）更简单的任务。*—*[Sonya Koptyev](https://sdtimes.com/softwaredev/the-developers-dilemma-choosing-between-go-and-rust/)

相比之下，Rust 中的并发是一个很新的特性，并且还有待稳定中，但是它的发展非常活跃，因此请留意这块。例如，Rust 的 [rayon](https://github.com/rayon-rs/rayon) 提供了一种非常优雅且轻巧的方法，可以将顺序计算转换为并行计算。

> 具有轻量级 Goroutine 和 Channel 语法确实很棒。它确实显示出语法的威力，即如此小的细节使并发编程比其他语言感觉更好。— [Rust 程序员对 Go 的早期印象](https://medium.com/better-programming/early-impressions-of-go-from-a-rust-programmer-f4fd1074c410)

虽然在 Rust 中实现并发程序可能会不太直接，但仍然可以实现，并且这些程序可以利用 Rust 的安全保证。标准库的 Mutex 类就是一个很好的例子：在 Go 中，你可以忘记在访问某些东西之前先获得一个互斥锁，但是 Rust 不允许你这样做。

> Go 将并发作为第一类概念。这并不是说你无法在 Rust 中找到类似 Go 的并发方式，而是留给程序员练习。*—*[Dave Cheney](https://dave.cheney.net/2015/07/02/why-go-and-rust-are-not-competitors)

## 安全性

前面我们已经看到，Go 和 Rust 都以不同的方式来防止与内存管理有关的大量常见编程错误。但是，尤其是 Rust 会竭尽全力确保你不会做本不该做的不安全的事情。

> Rust 的程序编辑器非常严格且学究（pedantic），它会检查你使用的每个变量以及引用的每个内存地址。它避免了可能的数据争用情况，并通知你有关未定义行为的信息。从根本上讲，并发和内存安全问题根本不可能进入Rust的安全子集。*—*[Why Rust?](https://bitbucket.org/blog/why-rust)

这会使 Rust 中的编程成为几乎所有其他语言的不同体验，而且一开始可能具有挑战性。但对很多人来说，努力工作是值得的。

> 对我来说，Rust 的主要优点是感觉编译器成为我的靠山，不会让任何错误漏出（有时感觉像魔术）。*—Grzegorz Nosek*

包括 Go 在内的许多语言都具有帮助程序员避免错误的功能，但是 Rust 将其提升到了一个新的高度，因此潜在的错误程序甚至无法编译。

> 使用 Rust，库程序员可以使用很多工具来防止用户犯错误。 Rust 使我们能够说我们拥有特定的数据。其他任何人都不可能拥有所有权，因此我们知道其他任何人都无法对其进行修改。我想不到曾经有过这么多工具来防止意外滥用。真是太好了。*—*[Sam Rose](https://samwho.dev/)

对于新手 Rust 程序员来说，“与借阅检查器（borrow checker）打架”是一个常见的症状，但是在大多数情况下，它发现的问题是代码中的真正错误（或至少是潜在的错误）。这可能会迫使你从根本上重新架构程序，以避免遇到这些问题。当正确性和可靠性是你的重中之重时，这是一件好事。语言不会改变编程方式的重点是什么？当你使用其他语言工作时，Rust 讲授的有关安全性的课程也会很有用。

> 如果选择 Rust，通常需要该语言提供的保证：防止空指针和数据竞争的安全性，可预测的运行时行为以及对硬件的完全控制。如果你不需要这些功能，Rust 对于你的下一个项目可能不是一个好的选择。这是因为这些保证要付出一定的代价：学习坡度，时间问题。你将需要学习不良习惯并学习新概念。很有可能，刚开始时，你将与借阅检查器进行很多斗争。*—*[Matthias Endler](https://endler.dev/2017/go-vs-rust/)

你发现 Rust 的编程模型的挑战性可能取决于你以前在其他语言中所拥有的经验。 Python 或 Ruby 程序员可能会发现它有限制；而其他人可能很高兴。

> 如果你是一位花了数周时间寻找这些语言的内存安全性错误的 C 或 C++ 程序员，那么你将非常感谢 Rust。 “对抗借阅检查器”变为“编译器可以检测到吗？凉！”—Grzegorz Nosek

## 规模

> 当今的服务器程序包含数千万行代码，由成百上千的程序员进行处理，并且每天都会更新。 Go 的设计和开发旨在提高在这种环境下的工作效率。 Go 的设计考虑因素包括严格的依赖关系管理，随着系统增长的软件体系结构的适应性以及跨组件边界的鲁棒性。*—*[Rob Pike](https://talks.golang.org/2012/splash.article)

当你自己或以小组形式处理问题时，选择简单语言还是丰富语言是你的偏爱。但是随着软件变得越来越大，越来越复杂，以及团队越来越大，这种差异真正开始显现出来。对于大型应用程序和分布式系统，执行速度不如开发速度重要：像 Go 这样的故意最小化的语言减少了新开发人员的启动时间，并使他们更容易使用大型代码库。

> 使用 Go，初级开发人员更容易提高工作效率，而中级开发人员更难引入脆弱的抽象，而抽象将导致问题。由于这些原因，Rust 在企业软件开发方面不如 Go 引人注目。*—*[Loris Cro](https://kristoff.it/blog/why-go-and-not-rust)

当涉及到大型软件开发时，清晰胜于灵活。 Go 的限制性实际上使它比 Rust 等更复杂、功能更强大的语言更适合企业和大型组织。

## 差异

尽管 Rust 和 Go 都是流行的，现代的，广泛使用的语言，但从故意针对完全不同的用例的意义上来说，它们并不是真正的竞争对手。 Go 的整个编程方法与 Rust 的方法完全不同，每种语言都适合某些人，同时又会激怒其他人。绝对很好，而且如果 Rust 和 Go 都以或多或少相同的方式或多或少地完成了相同的事情，那么我们实际上就不需要两种不同的语言。

那么，通过发现它们采取截然不同的方法的问题，我们是否能够了解 Rust 和 Go 的各自性质？让我们找出答案。

### 垃圾回收

“进行垃圾收集或不进行垃圾收集”是没有正确答案的问题之一。垃圾回收和自动内存管理通常使开发可靠，高效的程序变得快速简便，对于某些人来说，这是必不可少的。但是其他人说，垃圾回收的性能开销和停顿，使程序在运行时无法正常运行，并引入了无法接受的延迟。争论不休。

> Go 与 Rust 完全不同。尽管两者都可以模糊地描述为系统语言或 C 语言的替代品，但它们具有不同的目标和应用，语言设计风格以及优先级。垃圾收集确实是一个巨大的区别。在 Go 中使用 GC 可使该语言变得更加简单和小巧。
>
> 在 Rust 中不使用 GC 可以使它真正更快（特别是如果你需要保证的等待时间，而不仅仅是高吞吐量），并启用 Go 中无法实现的特性和编程模式（或者至少在不牺牲性能的情况下）。*—*[PingCAP](https://medium.com/better-programming/early-impressions-of-go-from-a-rust-programmer-f4fd1074c410)

## 更接近金属（Close to the metal）

计算机编程的历史一直是一个越来越复杂的抽象的故事，它使程序员能够解决问题而不必担心底层机器的实际工作原理。这使程序更易于编写，并且可能更具移植性。但是对于许多程序而言，访问硬件以及精确控制程序执行方式更为重要。 Rust 的目标是让程序员拥有更多的控制权，使其“更接近金属”，但是 Go 提取了体系结构的详细信息，以使程序员更加接近问题。

> 两种语言有不同的使用范围。 Golang 对于编写微服务和典型的 “DevOps” 任务很有用，但它不是系统编程语言。对于并发性，安全性和/或性能很重要的任务，Rust 更强。但是它的学习曲线比 Go 更陡。*—*[Matthias Endler](https://endler.dev/2017/go-vs-rust/)

### Go 发展更快

我在其他地方写过，对于大多数程序而言，[性能并不如可读性重要](https://bitfieldconsulting.com/golang/slower)。但是，当性能确实很重要时，它真的很重要。 Rust 进行了许多设计折衷，以实现最佳的执行速度。相比之下，Go 更加关注简单性，并且愿意为此牺牲一些（运行时）性能。但是 Go 的构建速度是无与伦比的，这对于大型代码库而言非常重要。

> Rust 比 Go 快。在上述基准测试中，Rust 速度更快，在某些情况下还快一个数量级。但是在选择使用 Rust 编写所有内容之前，请考虑一下 Go 在许多基准测试中并没有落后很多，并且它仍然比 Java，C#，JavaScript，Python 等同类工具快得多。
>
> 如果你需要一流的性能，那么你可以选择这两种语言中的任一种。如果你要构建一个处理高负载的 Web 服务，并且希望能够在垂直和水平方向上进行伸缩，则两种语言都将非常适合你。*—*[Andrew Lader](https://codeburst.io/should-i-rust-or-should-i-go-59a298e00ea9)

### 正确性

另一方面，如果程序没有正常运行，则可以任意快。大多数代码不是长期编写的，但通常令人惊讶的是某些程序可以在生产环境中运行多长时间：在某些情况下需要数十年。在这种情况下，需要花一些额外的时间来开发程序，以确保程序正确，可靠并且将来不需要进行大量维护。

> 我的看法：明天将要发布的代码选择 Go，在未来五年内保持不变的代码选择 Rust。*—Grzegorz Nosek*

尽管 Go 和 Rust 对于任何严肃的项目都是不错的选择，但最好使自己对每种语言及其特征都尽可能了解。最终，其他人的想法无关紧要：只有你可以决定哪种对你和你的团队是合适的。

> 如果你想加快开发速度，也许是因为你要编写许多不同的服务，或者你有庞大的开发团队，那么 Go 是你选择的语言。 Go 为你提供了一流的并发性，并且不容许不安全的内存访问（Rust 也不容忍），但不会强迫你管理每个最后的细节。 Go 是快速而强大的工具，但是它避免了使开发人员陷入困境，而专注于简单性和统一性。另一方面，如果需要拧紧块性能，那么 Rust 应该是你的选择。*—*[Andrew Lader](https://codeburst.io/should-i-rust-or-should-i-go-59a298e00ea9)

## 结论

我希望本文使你相信，Rust 和 Go 都值得你认真考虑。如果可能的话，你应该力求获得至少两种语言的某种程度的经验，因为它们对你在任何技术职业中都是非常有用的，即使你喜欢将编程作为业余爱好也是如此。如果你只有时间投入精力来学习一种语言，那么请在将 Go 和 Rust 都用于各种大小不同的程序之前，不要做出最终决定。

而且，对编程语言的了解实际上只是成为一名成功的软件工程师的一小部分。到目前为止，您将需要的最重要的技能是设计，工程，体系结构，沟通和协作。如果您擅长这些，那么无论您选择哪种语言，您都将是一名出色的软件工程师。学习愉快！

> 原文链接：<https://bitfieldconsulting.com/golang/rust-vs-go>
>
> 原文作者：John Arundel
>
> 编译：polarisxu