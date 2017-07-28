```
# -
Made by C 
···
JavaScript中的正则表达式
字符	描述
\	将下一个字符标记为一个特殊字符、或一个原义字符、或一个后向引用、或一个八进制转义符。例如，'n'匹配字符"n"。'\n'匹配一个换行符。序列'\\'匹配"\"而"\("则匹配"("。
^	匹配输入字符串的开始位置。如果设置了RegExp对象的Multiline属性，^也匹配'\n'或'\r'之后的位置。
$	匹配输入字符串的结束位置。如果设置了RegExp对象的Multiline属性，$也匹配'\n'或'\r'之前的位置。
*	匹配前面的子表达式零次或多次。例如，zo*能匹配"z"以及"zoo"。*等价于{0,}。
+	匹配前面的子表达式一次或多次。例如，'zo+'能匹配"zo"以及"zoo"，但不能匹配"z"。+等价于{1,}。
?	匹配前面的子表达式零次或一次。例如，"do(es)?"可以匹配"do"或"does"中的"do"。?等价于{0,1}。
{n}	n是一个非负整数。匹配确定的n次。例如，'o{2}'不能匹配"Bob"中的'o'，但是能匹配"food"中的两个o。
{n,}	n是一个非负整数。至少匹配n次。例如，'o{2,}'不能匹配"Bob"中的'o'，但能匹配"foooood"中的所有o。'o{1,}'等价于'o+'。'o{0,}'则等价于'o*'。
{n,m}	m和n均为非负整数，其中n<=m。最少匹配n次且最多匹配m次。刘，"o{1,3}"将匹配"fooooood"中的前三个o。'o{0,1}'等价于'o?'。请注意在逗号和两个数之间不能有空格。
?	当该字符紧跟在任何一个其他限制符(*,+,?,{n},{n,},{n,m})后面时，匹配模式是非贪婪的。非贪婪模式尽可能少的匹配所搜索的字符串，而默认的贪婪模式则尽可能多的匹配所搜索的字符串。例如，对于字符串"oooo"，'o+?'将匹配单个"o"，而'o+'将匹配所有'o'。
.	匹配除"\n"之外的任何单个字符。要匹配包括'\n'在内的任何字符，请使用象'[.\n]'的模式。
(pattern)	匹配pattern并获取这一匹配。所获取的匹配可以从产生的Matches集合得到，在VBScript中使用SubMatches集合，在JScript中则使用$0…$9属性。要匹配圆括号字符，请使用'\('或'\)'。
(?:pattern)	匹配pattern但不获取匹配结果，也就是说这是一个非获取匹配，不进行存储供以后使用。这在使用"或"字符(|)来组合一个模式的各个部分是很有用。例如，'industr(?:y|ies)就是一个比'industry|industries'更简略的表达式。
(?=pattern)	正向预查，在任何匹配pattern的字符串开始处匹配查找字符串。这是一个非获取匹配，也就是说，该匹配不需要获取供以后使用。例如，'Windows(?=95|98|NT|2000)'能匹配"Windows2000"中的"Windows"，但不能匹配"Windows3.1"中的"Windows"。预查不消耗字符，也就是说，在一个匹配发生后，在最后一次匹配之后立即开始下一次匹配的搜索，而不是从包含预查的字符之后开始。
(?!pattern)	负向预查，在任何不匹配pattern的字符串开始处匹配查找字符串。这是一个非获取匹配，也就是说，该匹配不需要获取供以后使用。例如'Windows(?!95|98|NT|2000)'能匹配"Windows3.1"中的"Windows"，但不能匹配"Windows2000"中的"Windows"。预查不消耗字符，也就是说，在一个匹配发生后，在最后一次匹配之后立即开始下一次匹配的搜索，而不是从包含预查的字符之后开始
x|y	匹配x或y。例如，'z|food'能匹配"z"或"food"。'(z|f)ood'则匹配"zood"或"food"。
[xyz]	字符集合。匹配所包含的任意一个字符。例如，'[abc]'可以匹配"plain"中的'a'。
[^xyz]	负值字符集合。匹配未包含的任意字符。例如，'[^abc]'可以匹配"plain"中的'p'。
[a-z]	字符范围。匹配指定范围内的任意字符。例如，'[a-z]'可以匹配'a'到'z'范围内的任意小写字母字符。
[^a-z]	负值字符范围。匹配任何不在指定范围内的任意字符。例如，'[^a-z]'可以匹配任何不在'a'到'z'范围内的任意字符。
\b	匹配一个单词边界，也就是指单词和空格间的位置。例如，'er\b'可以匹配"never"中的'er'，但不能匹配"verb"中的'er'。
\B	匹配非单词边界。'er\B'能匹配"verb"中的'er'，但不能匹配"never"中的'er'。
\cx	匹配由x指明的控制字符。例如，\cM匹配一个Control-M或回车符。x的值必须为A-Z或a-z之一。否则，将c视为一个原义的'c'字符。
\d	匹配一个数字字符。等价于[0-9]。
\D	匹配一个非数字字符。等价于[^0-9]。
\f	匹配一个换页符。等价于\x0c和\cL。
\n	匹配一个换行符。等价于\x0a和\cJ。
\r	匹配一个回车符。等价于\x0d和\cM。
\s	匹配任何空白字符，包括空格、制表符、换页符等等。等价于[\f\n\r\t\v]。
\S	匹配任何非空白字符。等价于[^\f\n\r\t\v]。
\t	匹配一个制表符。等价于\x09和\cI。
\v	匹配一个垂直制表符。等价于\x0b和\cK。
\w	匹配包括下划线的任何单词字符。等价于'[A-Za-z0-9_]'。
\W	匹配任何非单词字符。等价于'[^A-Za-z0-9_]'。
\xXX	匹配十六进制XX转义值。十六进制转义值必须为确定的两个数字长。例如，'\x41'匹配"A"。'\x041'则等价于'\x04'&"1"。正则表达式中可以使用ASCII编码。.
\num	匹配num，其中num是一个正整数。对所获取的匹配的引用。例如，'(.)\1'匹配两个连续的相同字符。
\n	标识一个八进制转义值或一个后向引用。如果\n之前至少n个获取的子表达式，则n为后向引用。否则，如果n为八进制数字(0-7)，则n为一个八进制转义值。
\nm	标识一个八进制转义值或一个后向引用。如果\nm之前至少有nm个获取得子表达式，则nm为后向引用。如果\nm之前至少有n个获取，则n为一个后跟文字m的后向引用。如果前面的条件都不满足，若n和m均为八进制数字(0-7)，则\nm将匹配八进制转义值nm。
\nml	如果n为八进制数字(0-3)，且m和l均为八进制数字(0-7)，则匹配八进制转义值nml。
\uXXXX	匹配Unicode字符，其中XXXX是一个用四个十六进制数字表示的Unicode字符。例如，\u00A9匹配版权符号‘©’


下表中列出的字符转义在正则表达式和替换模式中都会被识别。
转义符	说明
一般字符	除 . $ ^ { [ ( | ) * + ? \ 外，其他字符与自身匹配。
\a	与响铃（警报）\u0007 匹配。
\b	如果在 [] 字符类中，则与退格符 \u0008 匹配；如果不是这种情况，请参见本表后面的“注意”部分。
\t	与 Tab 符 \u0009 匹配。
\r	与回车符 \u000D 匹配。
\v	与垂直 Tab 符 \u000B 匹配。
\f	与换页符 \u000C 匹配。
\n	与换行符 \u000A 匹配。
\e	与 Esc 符 \u001B 匹配。
\040	将 ASCII 字符匹配为八进制数（最多三位）；如果没有前导零的数字只有一位数或者与捕获组号相对应，则该数字为后向引用。（有关详细信息，请参见反向引用。）例如，字符 \040 表示空格。
\x20	使用十六进制表示形式（恰好两位）与 ASCII 字符匹配。
\cC	与 ASCII 控制字符匹配；例如，\cC 为 Ctrl-C。
\u0020	使用十六进制表示形式（恰好四位）与 Unicode 字符匹配。
\	在后面带有不识别为转义符的字符时，与该字符匹配。例如，\* 与 \x2A 相同。
注意   转义字符 \b 是一个特例。在正则表达式中，\b 表示单词边界（\w 和 \W 之间的字符）；不过，在 [] 字符类中，\b 表示退格符。在替换模式中，\b 始终表示退格符。


只在替换模式中允许替换。对于正则表达式中的类似功能，使用后向引用（如 \1）。有关后向引用的详细信息，请参见反向引用和反向引用构造。
字符转义和替换是在替换模式中识别的唯一的特殊构造。下面几部分描述的所有语法构造只允许出现在正则表达式中；替换模式中不识别它们。例如，替换模式 a*${txt}b 插入字符串“a*”，后跟由 txt 捕获组匹配的子字符串（如果有的话），再后跟字符串“b”。在替换模式中，* 字符不会识别为元字符。与此类似，在正则表达式匹配模式中不识别 $ 模式。在正则表达式中，$ 指定字符串的结尾。
下表显示如何定义命名并编号的替换模式。
字符	说明
$number	替换由组号 number（十进制）匹配的最后一个子字符串。
${name}	替换由 (?<name> ) 组匹配的最后一个子字符串。
$$	替换单个“$”字符。
$&	替换完全匹配本身的一个副本。
$`	替换匹配前的输入字符串的所有文本。
$'	替换匹配后的输入字符串的所有文本。
$+	替换最后捕获的组。
$_	替换整个输入字符串。




字符类是一个字符集，如果字符集中的任何一个字符有匹配，它就会找到该匹配项。下表总结了字符匹配语法。
字符类	说明
.	与除 \n 之外的任何字符匹配。如果已用 Singleline 选项做过修改，则句点字符将与任何字符匹配。有关详细信息，请参见正则表达式选项。
[aeiou]	与指定字符集中包含的任何单个字符匹配。
[^aeiou]	与不在指定字符集中的任何单个字符匹配。
[0-9a-fA-F]	使用连字号 (–) 允许指定连续字符范围。
\p{name}	与 {name} 指定的命名字符类中的任何字符匹配。支持的名称为 Unicode 组和块范围。例如，Ll、Nd、Z、IsGreek、IsBoxDrawing。
\P{name}	与在 {name} 中指定的组和块范围中未包含的文本匹配。
\w	与任何单词字符匹配。等效于 Unicode 字符类别 [\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}]。如果用 ECMAScript 选项指定了符合 ECMAScript 的行为，则 \w 等效于 [a-zA-Z_0-9]。
\W	与任何非单词字符匹配。等效于 Unicode 类别 [^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}]。如果用 ECMAScript 选项指定了符合 ECMAScript 的行为，则 \W 等效于 [^a-zA-Z_0-9]。
\s	与任何空白字符匹配。等效于 Unicode 字符类别 [\f\n\r\t\v\x85\p{Z}]。如果用 ECMAScript 选项指定了符合 ECMAScript 的行为，则 \s 等效于 [ \f\n\r\t\v]。
\S	与任何非空白字符匹配。等效于 Unicode 字符类别 [^\f\n\r\t\v\x85\p{Z}]。如果用 ECMAScript 选项指定了符合 ECMAScript 的行为，则 \S 等效于 [^ \f\n\r\t\v]。
\d	与任何十进制数字匹配。等效于 \p{Nd}（对于 Unicode 类别）和 [0-9]（对于非 Unicode 类别）ECMAScript 行为。
\D	与任何非数字匹配。等效于 \P{Nd}（对于 Unicode 类别）和 [^0-9]（对于非 Unicode 类别）ECMAScript 行为。


原子零宽度断言
下表中描述的元字符不会使引擎在字符串中前进或使用字符。它们只是根据字符串中的当前位置使匹配成功或失败。
断言	说明
^	指定匹配必须出现在字符串的开头或行的开头。有关详细信息，请参见正则表达式选项中的 Multiline 选项。
$	指定匹配必须出现在以下位置：字符串结尾、字符串结尾的 \n 之前或行的结尾。有关详细信息，请参见正则表达式选项中的 Multiline 选项。
\A	指定匹配必须出现在字符串的开头（忽略 Multiline 选项）。
\Z	指定匹配必须出现在字符串的结尾或字符串结尾的 \n 之前（忽略 Multiline 选项）。
\z	指定匹配必须出现在字符串的结尾（忽略 Multiline 选项）。
\G	指定匹配必须出现在上一个匹配结束的地方。与 Match.NextMatch() 一起使用时，此断言确保所有匹配都是连续的。
\b	指定匹配必须出现在 \w（字母数字）和 \W（非字母数字）字符之间的边界上。匹配必须出现在单词边界上，即出现在由任何非字母数字字符分隔的单词中第一个或最后一个字符上。
\B	指定匹配不得出现在 \b 边界上。

下表描述了影响匹配数量的元字符。
限定符	说明
*	指定零个或更多个匹配；例如 \w* 或 (abc)*。等效于 {0,}。
+	指定一个或多个匹配；例如 \w+ 或 (abc)+。等效于 {1,}。
?	指定零个或一个匹配；例如 \w? 或 (abc)?。等效于 {0,1}。
{n}	指定恰好 n 个匹配；例如 (pizza){2}。
{n,}	指定至少 n 个匹配；例如 (abc){2,}。
{n,m}	指定至少 n 个但不多于 m 个匹配。
*?	指定尽可能少地使用重复的第一个匹配（等效于 lazy *）。
+?	指定尽可能少地使用重复但至少使用一次（等效于 lazy +）。
??	指定使用零次重复（如有可能）或一次重复 (lazy ?)。
{n}?	等效于 {n} (lazy {n})。
{n,}?	指定尽可能少地使用重复但至少使用 n 次 (lazy {n,})。
{n,m}?	指定介于 n 次和 m 次之间、尽可能少地使用重复 (lazy {n,m})。


分组构造使您可以捕获子表达式组并提高具有非捕获预测先行和回顾后发修饰符的正则表达式的效率。下表描述了正则表达式分组构造。
分组构造	说明
(   )	捕获匹配的子字符串（或非捕获组；有关详细信息，请参见正则表达式选项中的 ExplicitCapture 选项）。使用 () 的捕获根据左括号的顺序从 1 开始自动编号。捕获元素编号为零的第一个捕获是由整个正则表达式模式匹配的文本。
(?<name>   )	将匹配的子字符串捕获到一个组名称或编号名称中。用于 name 的字符串不能包含任何标点符号，并且不能以数字开头。可以使用单引号替代尖括号，例如 (?'name')。
(?<name1-name2> )	平衡组定义。删除先前定义的 name2 组的定义并在 name1 组中存储先前定义的 name2 组和当前组之间的间隔。如果未定义 name2 组，则匹配将回溯。由于删除 name2 的最后一个定义会显示 name2 的先前定义，因此该构造允许将 name2 组的捕获堆栈用作计数器以跟踪嵌套构造（如括号）。在此构造中，name1 是可选的。可以使用单引号替代尖括号，例如 (?'name1-name2')。
(?:   )	非捕获组。
(?imnsx-imnsx:   )	应用或禁用子表达式中指定的选项。例如，(?i-s: ) 将打开不区分大小写并禁用单行模式。有关详细信息，请参见正则表达式选项。
(?=   )	零宽度正预测先行断言。仅当子表达式在此位置的右侧匹配时才继续匹配。例如，\w+(?=\d) 与后跟数字的单词匹配，而不与该数字匹配。此构造不会回溯。
(?!   )	零宽度负预测先行断言。仅当子表达式不在此位置的右侧匹配时才继续匹配。例如，\b(?!un)\w+\b 与不以 un 开头的单词匹配。
(?<=   )	零宽度正回顾后发断言。仅当子表达式在此位置的左侧匹配时才继续匹配。例如，(?<=19)99 与跟在 19 后面的 99 的实例匹配。此构造不会回溯。
(?<!   )	零宽度负回顾后发断言。仅当子表达式不在此位置的左侧匹配时才继续匹配。
(?>   )	非回溯子表达式（也称为“贪婪”子表达式）。该子表达式仅完全匹配一次，然后就不会逐段参与回溯了。（也就是说，该子表达式仅与可由该子表达式单独匹配的字符串匹配。）
命名捕获根据左括号的从左到右的顺序按顺序编号（与非命名捕获类似），但在对所有非命名捕获进行计数之后才开始对命名捕获进行编号。例如，模式 ((?<One>abc)/d+)?(?<Two>xyz)(.*) 按编号和名称产生下列捕获组。（编号为 0 的第一个捕获总是指整个模式）。
编号	名称	模式
0	0（默认名称）	((?<One>abc)/d+)?(?<Two>xyz)(.*)
1	1（默认名称）	((?<One>abc)/d+)
2	2（默认名称）	(.*)
3	1	(?<One>abc)
4	2	(?<Two>xyz)

下表列出了用于将后向引用修饰符添加到正则表达式中的可选参数。
后向引用构造	定义
\number	后向引用。例如，(\w)\1 查找双写的单词字符。
\k<name>	命名后向引用。例如，(?<char>\w)\k<char> 查找双写的单词字符。表达式 (?<43>\w)\43 执行同样的操作。可以使用单引号替代尖括号，例如 \k'char'。

下表列出了用于修改正则表达式以允许进行二者之一/或匹配的特殊字符。
替换构造	定义
|	与用 | （垂直条）字符分隔的任何一个术语匹配；例如，cat|dog|tiger。使用最左侧的成功匹配。
(?(expression)yes|no)	如果表达式在此位置匹配，则与“yes”部分匹配；否则，与“no”部分匹配。“no”部分可省略。表达式可以是任何有效的子表达式，但它将变为零宽度断言，因此该语法等效于 (?(?=expression)yes|no)。请注意，如果表达式是命名组的名称或捕获组编号，则替换构造将解释为捕获测试（在本表的下一行对此进行了描述）。若要避免在这些情况下产生混淆，则可以显式拼出内部 (?=expression)。
(?(name)yes|no)	如果命名捕获字符串有匹配，则与“yes”部分匹配；否则，与“no”部分匹配。“no”部分可省略。如果给定的名称不与此表达式中使用的捕获组的名称或编号对应，则替换构造将解释为表达式测试（在本表的上一行进行了描述）。

下表列出了用于修改正则表达式的子表达式。
构造	定义
(?imnsx-imnsx)	对诸如不区分大小写这样的选项进行设置或禁用以使其在模式中间打开或关闭。有关特定选项的信息，请参见正则表达式选项。在封闭组结束之前，选项更改将一直有效。请参见有关分组构造 (?imnsx-imnsx: ) 的信息，它是一个更为巧妙的形式。
(?#   )	插入到正则表达式内部的内联注释。该注释在第一个右括号字符处终止。
···
# [至行尾]	X 模式注释。该注释以非转义的 # 开头，并继续到行的结尾。（请注意，必须激活 x 选项或 RegexOptions.IgnorePatternWhitespace 枚举选项才能识别此类注释。）


```
