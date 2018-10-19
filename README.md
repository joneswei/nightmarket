 概述
哲學

Markdown的目標是實現「易讀易寫」。

不過最需要強調的便是它的可讀性。一份使用Markdown格式撰寫的文件應該可以直接以純文字發佈，並且看起來不會像是由許多標籤或是格式指令所構成。Markdown語法受到一些既有text-to-HTML格式的影響，包括Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，然而最大靈感來源其實是純文字的電子郵件格式。

因此Markdown的語法全由標點符號所組成，並經過嚴謹慎選，是為了讓它們看起來就像所要表達的意思。像是在文字兩旁加上星號，看起來就像*強調*。Markdown的清單看起來，嗯，就是清單。假如你有使用過電子郵件，區塊引言看起來就真的像是引用一段文字。
行內HTML

Markdown的語法有個主要的目的：用來作為一種網路內容的寫作用語言。

Markdown不是要來取代HTML，甚至也沒有要和它相似，它的語法種類不多，只和HTML的一部分有關係，重點不是要創造一種更容易寫作HTML文件的語法，我認為HTML已經很容易寫了，Markdow的重點在於，它能讓文件更容易閱讀、編寫。HTML 是一種發佈的格式，Markdown是一種編寫的格式，因此，Markdown的格式語法只涵蓋純文字可以涵蓋的範圍。

不在Markdown涵蓋範圍之外的標籤，都可以直接在文件裡面用HTML撰寫。不需要額外標註這是HTML或是Markdown；只要直接加標籤就可以了。

只有區塊元素──比如<div>、<table>、<pre>、<p>等標籤，必需在前後加上空行，以利與內容區隔。而且這些（元素）的開始與結尾標籤，不可以用tab或是空白來縮排。Markdown的產生器有智慧型判斷，可以避免在區塊標籤前後加上沒有必要的<p>標籤。

舉例來說，在Markdown文件裡加上一段HTML表格：

This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.

請注意，Markdown語法在HTML區塊標籤中將不會被進行處理。例如，你無法在HTML區塊內使用Markdown形式的*強調*。

HTML的區段標籤如<span>、<cite>、<del>則不受限制，可以在Markdown的段落、清單或是標題裡任意使用。依照個人習慣，甚至可以不用Markdown格式，而採用HTML標籤來格式化。舉例說明：如果比較喜歡HTML的 <a>或<img>標籤，可以直接使用這些標籤，而不用Markdown提供的連結或是影像標示語法。

HTML區段標籤和區塊標籤不同，在區段標籤的範圍內，Markdown的語法是有效的。
特殊字元自動轉換

在HTML文件中，有兩個字元需要特殊處理：<和&。<符號用於起始標籤&符號則用於標記HTML實體，如果你只是想要使用這些符號，你必須要使用實體的形式，像是&lt;和&amp;。

& 符號其實很容易讓寫作網路文件的人感到困擾，如果你要打「AT&T」 ，你必須要寫成「AT&amp;T」 ，還得轉換網址內的 & 符號，如果你要連結到：

http://images.google.com/images?num=30&q=larry+bird

你必須要把網址轉成：

http://images.google.com/images?num=30&amp;q=larry+bird

才能放到連結標籤的href屬性裡。不用說也知道這很容易忘記，這也可能是HTML標準檢查所檢查到的錯誤中，數量最多的。

Markdown允許你直接使用這些符號，但是你要小心跳脫字元的使用，如果你是在HTML實體中使用&符號的話，它不會被轉換，而在其他情形下，它則會被轉換成&amp;。所以你如果要在文件中插入一個著作權的符號，你可以這樣寫：

&copy;

Markdown將不會對這段文字做修改，但是如果你這樣寫：

AT&T

Markdown就會將它轉為：

AT&amp;T

類似的狀況也會發生在<符號上，因為Markdown支援行內 HTML ，如果你是使用<符號作為HTML標籤使用，那Markdown也不會對它做任何轉換，但是如果你是寫：

4 < 5

Markdown將會把它轉換為：

4 &lt; 5

不過需要注意的是，code範圍內，不論是行內還是區塊，<和&兩個符號都一定會被轉換成HTML實體，這項特性讓你可以很容易地用Markdown寫HTML code（和HTML相對而言。在HTML語法中，你要把所有的<和&都轉換為 HTML實體，才能在HTML文件裡面寫出HTML code。）



















| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---------:|:------|:------|:------|:------| :------| :------| :------|
| 中山 | Kitty |          | 0907492259 | 17/22 | .7  | .3*2 / +1 |  |
| 永和 | 小月  |  		  | 0965177471 | 15    | 70  | .3        | https://www.jkforum.net/thread-5775095-5-1.html |
| 永和 | 霜霜  | tart6688 |            | 25    | 70  | .3        | https://www.jkforum.net/thread-7572766-1-1.html |
| 西門 | 小梅  |          | 0903850862 | 15    | 120 | Na        |  |
