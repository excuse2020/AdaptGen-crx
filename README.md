# AdaptGen插件使用手册

## 1. 安装

打开chrome浏览器，点击右上角的<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425145900392.png" alt="image-20250425145900392" style="zoom:50%;" />，在弹出界面中点击拓展程序，继续点击管理拓展程序

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425150038089.png" alt="image-20250425150038089" style="zoom: 25%;" />



先打开开发者模式，然后选择加载已解压的扩展程序，找到chrome-adaptgen所在的位置，点击选择。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425150223024.png" alt="image-20250425150223024" style="zoom: 33%;" />



确保插件状态是开启①，点击插件②把AdaptGen固定③在浏览器状态栏。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425150623305.png" alt="image-20250425150623305" style="zoom: 33%;" />



点击插件图标弹出插件主页面，AdaptGen插件已经安装完成！

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425150834298.png" alt="image-20250425150834298" style="zoom: 33%;" />



## 2. 使用

### 2.1 登录

1. 通过插件主页sites中的网址快速跳转到leetcode的问题集，leetcode.cn是中文网站（建议跳转），leetcode.com是英文网站。你需要登录或注册自己的leetcode账号，用于提交代码。

2. 注册AdaptGen用户信息，用于收集反馈信息。点击右上角的用户图标可跳转到登录界面，可以直接点击关闭图标使用默认用户来使用本插件（不建议）。新用户需要注册账号，点击 <font color=Blue>Register now </font>），只需要提供昵称和密码即可。

3. 注册成功后会自动跳转到用户界面。你可以选择改变头像（随机生成）、填写Email（非必须）、选择leetcode用户等级（根据你的编程经验），分为Beginner（初学者）、Intermediate（有一定经验）、Advanced（有丰富经验）。点击关闭图标或点击空白处可关闭该界面，如果更新了信息，需要选择是否保存。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425152444406.png" alt="image-20250425152444406" style="zoom:33%;" />

### 2.2 使用插件辅助编程

#### 2.2.1 模板生成

只有打开问题描述界面才支持生成模板。你可以选择在插件主界面中点击 **Generate** 来生成模板，也可以选择鼠标右键菜单中的生成模板来完成。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425153552146.png" alt="image-20250425153552146" style="zoom: 25%;" />

你可以设置一些选项来生成模板，各选项的含义为：

**Template Type：模板类型**

- Original为模板直接生成的代码，未经任何处理，并不可以直接用作AC代码。 使用大模型生成的Original可能会包含引导性的注释，如果需要你可以选择。
- FuIl：我们将代码中重要的逻辑判断和赋值运算使用占位符替换，用户需自己思考应如何填充来解决问题。
- Data Structures：在Full的基础上只保留基本的数据定义，提示你可以使用何种数据结构解决问题，具体的算法流程需自己实现。
- Algorithms：在Full的基础上只保留基本的控制流程，提示你解决问题的一般流程，你需要思考选择何种数据结构存储数据，并完成具体的算法流程。

**Language：**编程语言选择，目前只支持 **Java** 语言。

**Model：**我们使用GA（遗传算法）和主流的大模型（GPT、DeekSeek、Qwen）来生成模板。你可以根据需要来选择各类模板，使用GA生成的模板在标识符一致性上存在问题，我们使用大模型进行了优化（**GA-OPT**，如果要选择GA可以优先选择GA-OPT）。**GA（GA-OPT）支持更多的编程问题，大模型生成的模板在复杂问题上的表现更好。**我们更推荐你选择**Random**来筛选所有Model生成的模板，会给为你推荐最优解。

**Example Count：**我们从若干个AC代码中提取模板，Example Count为使用至少N个代码总结出的模板。Examples越多，生成的模板通用性更强。

**TopK：**我们使用自动化指标评估生成的模板，TopK为选择分数最高的K个模板，随后从这K个中随机选择1个返回给你。你可以选择TopK为1来获取得分最高的。

点击Generate Template来生成符合选项的模板。模板显示界面如下：

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425160152061.png" alt="image-20250425160152061" style="zoom: 33%;" />

你可以选择手动复制需要的代码模块或点击复制图标复制全文。

为了收集信息来验证AdaptGen的有效性，我们会记录你的模板生成记录（生成选项）和复制粘贴行为（只监测和模板有关的部分）。

#### 2.2.2 提交信息收集

当监测到提交信息时，我们会向你询问该提交的结果（成功 / 失败），当你查看以往的提交时也会弹出询问弹窗，你可以点击空白地方来拒绝提交。如果是新提交，你需要根据leetcode的判断结果来提交反馈。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425161036319.png" alt="image-20250425161036319" style="zoom:33%;" />

#### 2.2.3 反馈信息收集 

在确认提交为成功后，会弹出确认框提示你是否立即去反馈，如果你选择了 Not Now，也可以通过插件主界面的 Feedback 按钮去完成反馈。

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425161344956.png" alt="image-20250425161344956" style="zoom:33%;" />

反馈界面如下：

<img src="/Users/zz/Library/Application Support/typora-user-images/image-20250425161503677.png" alt="image-20250425161503677" style="zoom: 33%;" />

其中打 * 的为必选项，Suggestions for Improvement可以选择填写（建议填写）

其中，Favorite Module为在使用过程中你喜欢的模板模块，可多选。

Assistance Level：模板在该问题上的辅助程度。分为正向帮助和负向帮助，如果插件生成的模板对你有帮助，你可以提交一个正分；如果你觉得插件生成的模板妨碍你独立思考，你可以提交一个负分。

Matches Coding Habits ：模板中代码的编码风格（如缩进格式、变量名使用、逻辑思路）是否符合你的习惯。

Plugin Experience ：插件的使用体验，包括插件是否方便使用，是否存在bug等。

Suggestions for Improvement：你可以提出针对模板质量的改进方向，你希望模板还应该在哪些方面做出优化，如模板中代码的详略程度是否得当、模板是否需要继续细分、是否需要加入一些引导性的注释等。此外，在插件的使用上，你也可以提出建议，如你希望插件加入哪些功能、存在哪些bug等。

### 3. 反馈注意事项

我们需要进行无插件和有差距的对比实验，在无插件解题时，你只需要在提交代码后提交其运行结果即可。在有插件解题时，你需要先生成模板（可生成多个）、基于模板解题、提交代码结果、进行反馈。