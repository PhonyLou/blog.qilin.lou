+++
title = "结对编程的一些经验"
Description = "分享一些关于结对编程的经验"
+++

当听到“结对编程”一词时，你的第一印象是什么？

这是否意味着一种时尚的代码编写方式，还是一种浮夸的方法？

我想分享过去6个月的经验。在这段时间里，我和我的同事一直结对以编写生产代码。

# 实践和好处

加入新团队之前，我在职业生涯中没有任何结对编程经验。 一切的开头就是口号-_我们总是结对_。 你可以在任何地方找到结对编程的文化，例如git commit消息-“实现xxx函数，与xxx结对”


### 如何找到结对伙伴

当开发人员想要拿起卡片时，无论是故事卡片还是任务，她都举手说：“嘿，我想这张卡片，谁可以和我结对？”。 然后团队中的另一位开发人员可以回复她并开始一起工作。

### 结对姿势

在结对中，有两个角色 - driver 和 navigator。一对 pair 在一台机器上编写代码，因此他们必须决定谁来用键盘。通常，driver 负责编写代码，同时 navigator 观察 driver 的行动，并给出建议。

完成部分功能后，他们将交换角色。现在，原来的 navigator 控制设备。角色交换的规则可以 pair 自行商议，有时可以是完成功能的一部分就交换，有时可以是时间（比如 20 分钟）到了就交换。

### 好处

在结对编程中，一对 pair 彼此会进行很多讨论，因此他们可以做出良好的设计和决策。 尤其是对某些敏感操作，一个专注的 navigator 可以阻止一些愚蠢的操作 —— 例如 *rm -rf /*

另一种好处是把 code review 结合在了平时的工作中。 一对 pair 可以保证代码至少经过两个开发人员。 这种做法可以提高代码质量。

还有一个明显的好处是知识共享。在结对编程中，领域知识，编程技能，快捷键使用等技能都是非常受欢迎的。

# 代价

然而，即使我们只是处于结对编程的初始阶段，我们依然为此付出了很多代价。

### 批评别人

是的，你需要根据自己的感觉指出错误和有坏味道的代码。 发现错误时，你需要勇敢地说“不”。

并且要小心，避免陷入责备他人的陷阱。这对人的软技能是有要求的。

### 容易疲惫

始终保持专注是非常耗精力的行为。 即使 pair 了很短的实践（可能是1个小时），我都会感到非常疲惫。 因此设置时间框来强制打断工作是一个不错的选择。

### 交付速度

这导致了很多关于结对编程的争论。 支持者认为，如果采用结对编程，那么最终会在软件质量，代码审查，知识共享以及快速加入新成员将带来长期利益。

但是其他人则认为不可能1 + 1>2。他们（通常是管理团队）认为结对编程的好处无法超过对交付速度的影响。

对于我们来说，速度的问题直到现在都无关紧要，因此我们将继续结对。

你会尝试结对吗？