# TOC 中的可判定性和不可判定性

> 原文:[https://www . geesforgeks . org/decisibility-in-TOC 和-decisibility-in-TOC/](https://www.geeksforgeeks.org/decidability-and-undecidability-in-toc/)

将语言(或问题*)识别为可判定、不可判定或部分可判定是 GATE 中非常常见的问题。有了正确的知识和丰富的经验，这个问题就很容易解决了。

让我们从一些定义开始

**可判定语言**-如果对 P 的所有 yes 实例的语言 L 都是可判定的，则判定问题 P 被称为是可判定的(即，具有算法)
。
示例-(一)(DFA 的接受问题)给定一个 DFA，它接受给定的
单词吗？

(二)(DFA 的空性问题)给定一个 DFA，它接受什么词吗？

(三)(DFA 的等价问题)给定两个 DFA，它们是否接受
相同的语言？

**不可判定语言**-–如果 P 的所有
yes 实例的语言 L 是不可判定的，则判定问题 P 被认为是不可判定的，或者如果语言是不可判定的，则该语言是不可判定的。不可判定的语言可能是部分可判定的语言，或者是其他不可判定的语言。如果一种语言甚至不可部分判定，那么这种语言就不存在图灵机。

**部分可判定或半可判定语言**-–如果 P 的所有 yes 实例的语言 L 都是 RE，则判定问题 P 被称为是半可判定的(即具有半算法)。如果“L”是 RE 语言而不是 REC 语言，则语言“L”是部分可判定的。

**递归语言(REC)**–如果存在一个图灵机，它会接受‘L’中的所有字符串，并拒绝‘L’中没有的所有字符串，那么语言‘L’被称为递归。图灵机每次都会暂停，并对每一个输入的字符串给出一个答案(接受或拒绝)。如果语言是递归语言，那么它是可判定的。所有可判定的语言都是递归语言，反之亦然。

**递归可枚举语言(RE)**–如果存在图灵机，该图灵机将接受(并因此暂停)所有在“L”中的输入字符串，但可能会也可能不会暂停所有不在“L”中的输入字符串，则语言“L”被称为递归可枚举语言。根据定义，所有的 reC 语言也是 RE 语言，但不是所有的 RE 语言都是 REC 语言。

现在让我们解决一些例子–

解决可判定性问题的一种方法是试图将一个已知的不可判定性问题简化为给定的问题。通过将问题从 P1 简化为 P2，我们意味着我们正试图通过使用用于解决 P2 问题的算法来解决 P1 问题。

如果我们能把一个已知的不可判定的问题 P1 化为一个给定的问题 P2，那么我们肯定能说 P2 也是不可判定的。如果 P2 是可判定的，那么 P1 也是可判定的，但这变成了一个矛盾，因为众所周知，P1 是不可判定的。

例如。

**1。给定一个图灵机“M”，我们需要找出当在“M”中输入字符串“w”时，是否达到了状态“Q”。这个问题也被称为“国家进入问题”。**

现在让我们试着把暂停问题简化为状态输入问题。图灵机只有在转换函数时才会停止？(qi，a)未定义。更改每个未定义的函数？(齐一)要吗？(qi，a) = (Q，a，L 或 R)。请注意，只有在图灵机停止时，才能达到状态 Q。

假设我们有一个解决状态输入问题的算法，它每次都会停止，并告诉我们是否可以达到状态 Q。通过告诉我们我们每次都可以或不能达到状态 Q，它在告诉我们图灵机每次都会或不会停止。但是我们知道这是不可能的，因为犹豫的问题是不可决定的。这意味着，我们假设存在一种算法来解决状态输入问题，并且每次都停止并给我们一个答案，这是错误的。因此，状态输入问题是不可判定的。

**2。给定两种常规语言 L1 和 L2，找到一个字符串“w”是否在 L1 和 L2 都存在的问题是一个可判定的问题。**

首先，我们制作了两个图灵机 TM1 和 TM2，它们分别模拟了 L1 和 L2 的语言。我们知道一个 DFA 总是会停机，所以一个模拟 DFA 的图灵机也会一直停机。我们在 TM1 和 TM2 中输入字符串“w”。两个图灵机都会停下来给我们一个答案。我们可以将图灵机的输出连接到修改后的“与”门，只有当两个图灵机都回答“是”时，该门才会输出“是”。否则，它将输出“否”。

由于这个由两个图灵机和一个修改的与门组成的系统总是会停止，所以这个问题是一个可判定的问题。

这个话题有很多疑问。没有通用的算法来解决它们。大多数问题需要独特而巧妙的证明。这里是需要经验的地方。通过解决许多这样的问题，人们可以很快地在现场找到这些问题的证据。所以，继续练习。

*在计算理论中，“语言”和“问题”可以同义使用。例如，“停止问题”也可以写成“L = { < M，w > |图灵机“M”在输入“W”时停止”。这里的“L”是一种语言。

本文由**尼提什·乔希**供稿。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论