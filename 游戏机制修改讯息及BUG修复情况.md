# 游戏机制修改讯息及BUG修复情况

## 目录

- [最新BUG修复情况](#最新BUG修复情况)
- [最新游戏机制修改讯息](#最新游戏机制修改讯息)
- [汉化的更新日志备份](#汉化的更新日志备份)

## BUG定义

**定义**：程序或系统中的缺陷，或未按预期运行的行为。

这里主要收集《开拓者：正义之怒》以下类型的BUG，优先按照游戏内的描述文本，如果游戏里没有，则按照规则书的文本（两者文本冲突以游戏内文本为准）。

- **功能性 BUG**： 某个功能 **完全无法按预期使用**，或者 **触发逻辑错误**，导致它的 **效果不正确**、**失效** 或 **过强/过弱**。
- **逻辑 BUG**：**规则文本** 与 **游戏内数值计算** 或 **交互方式** 不符，导致 **某些数值异常**，但**功能仍然可以使用**。
- **UI 交互 BUG**：主要涉及 **界面显示错误、玩家操作错误、提示信息不符** 等，影响玩家体验但不影响实际计算逻辑。

## 最新BUG修复情况

整理的内容截止到2025年2月27号

### 未修复的BUG分类

#### 法术

- 迷幻图纹：法术效果没有总HD限制
- 视如仇寇：全队会共享视如仇寇的效果
- 圣剑术和魔化武器：与之类似类似的，作用在武器的附魔而不是作为人物BUFF的法术，无法被持久法术影响。
- 阴影塑能和阴影咒法系列法术：无法主动在法术书里进行超魔
- 天堂千翼鸣：错误添加到魔战士的3环
- 高等狂乱之歌：错误添加到魔战士的3环
- 净化谢幕曲：某些分支比如 净化谢幕曲（力竭）对敌人释放时，会解除敌人身上的全部BUFF。
- 战法转换：可以分享给队友的战法转换（比如棕毛变化师和炼金术士的），在计算BAB加成时按照自身的BAB计算而非受术者本身，比如20级棕毛变化师给队友分享战法转换，会**给队友直接+10BAB而不是把队友的BAB补到队友的角色等级**。
- 秘法窃取：目前解除魔法的数量没有上限（而不是一个），且每个BUFF单独进行一次掷骰，检定够高的话可以把敌人的BUFF全部转移到自己身上。
- 闪电链：无法正常触发超魔（法术加剧）的增加伤害骰上限的效果。
- 圣战之刃：改版后可以切换武器生效，先切空手或者近战武器吃圣战之刃，然后切换成远程武器，让远程武器也受到圣战之刃的加成。
- 祈祷术：用任何手段都无法使用超魔（法术延时），持续时间跟法术书的施法者等级无关（合书以后也是20CL的持续时间--2分钟，甚至只有5CL但是角色等级为20的人释放的祈祷术也是2分钟），也不受装备CL加成，反而只跟人物的等级有关（比如后期爱乌的祈祷术，传奇道途的祈祷术，持续时间就非常久）。
- 回声定位：不能正常无视敌人的镜影术效果。
- 真知术：就算敌人有心灵屏障，也可以无视敌人的镜影术。
- 寒冰之躯：更新日志中提到，新增了免疫疲劳和力竭的效果，但是法术描述中并没有具体列出来（关于免疫影响生理机能的部分，钢铁之躯也有，但钢铁之躯不免疫疲劳和力竭---也可能是钢铁之躯有BUG）。
- 凛冬之握：
  - 在一个位置释放多个凛冬之握，其效果会叠加，敌人会遭受多次豁免检定而非一次。【注：以前油腻术也是这种效果，后面作为BUG修复了】
  - 无视行动自如造成俯卧（这个不一定算BUG，也许设计师就喜欢做超模法术）。【注：游戏里的凛冬之握是桌面里三个法术的合体，俯卧效果源于冰滑术（Ice Slick），理应为跟油腻术一样的移动受限效应，会被行动自如所免疫。】
- 所有的地形法术：
  - 均没有增效、强效和极效的超魔孔位，只能靠魔战士法术超魔能力、法术大师的法术超魔能力、癫狂灾瘟的强效极效超魔等临时BUFF类超魔效果进行强效极效。【也不清楚是设定还是BUG】
  - 焦油池，剑刃障璧等地形法术，释放瞬间只要敌人在法术范围内，就会进行两次豁免检定（受到两次伤害）。


#### 职业

- 博学士
  - 游荡者秘闻：可以选择诡计大师察觉2阶的专长
  - 法师专长：即使你已经有了法术专精，也可以再次选择法术专精，双专精效果可以叠加
  - 法术扩表：可以反复选择同一个职业的法术书进行扩表，而非描述中的不能选相同的秘闻两次【切换到英文文本来看，其他只能选一次的能力都注明了作为秘闻，所以只能选一次；而扩表的部分描述并没有作为秘闻的描述，**因此不限制次数并不算BUG---符合文本描述**】。
- 歌者
  - 兼职歌者以后，受到歌者的狂暴战歌影响下，不会禁止施法（甚至战法转换以后还能施法）
  - 奋不顾身：队友无法使用歌者分享的【奋不顾身】能力，歌者学了神话激励以后自身的【奋不顾身】会失效。
  - 滋事者
    - 歌者天赋的UI错误，让玩家容易误认为可以选择所有的进阶天赋比如机会主义者，实际上滋事者并没有'进阶天赋'，有的是'偷袭技巧'，后者只允许让滋事者选择那些调整了偷袭的进阶天赋。
- 魔战士
  - 法术打击
    - 回合制下，使用法术打击（远程法术打击不行）可以通过恶魔道途空奢魔相/御衡者高等破敌/拉兹米尔的面具，实现额外一次整轮攻击（比如空奢魔相+拉兹米尔的面具，相当于用自由动作、移动动作、标准动作，分别进行了一次整轮攻击，一个回合内打三个整轮攻击）
    - 【规则不清之处】法术打击会将近战接触攻击的法术转换为一次武器攻击（远程法术打击则是将远程接触攻击转换为一次武器攻击），攻击命中时法术生效，该攻击采用武器的重击范围，但是重击以后法术只能造成两倍伤害。**因此有如下推理**：
      - 因为变成了武器攻击，这些接触攻击的法术不会再受到精通精通精通重击精通（射线/接触）和精通重击（射线/接触）的加成，事实也是如此。
      - 同理，因为变成了武器攻击，所以受到部分武器攻击的增伤加成（详情看附伤BUG的B类附伤，这该算附伤BUG的一部分吗？）。
      - 武器攻击的增伤加成在法术打击的法术中，被算作法术伤害，因此这部分增伤的额外骰子（比如神圣2d6伤害），会受到部分法术伤害加成（比如<最后的阿兹兰特的传承>---具有元素描述符的法术每个伤害骰额外+2伤害，会将这次神圣的2d6伤害变成2d6+4；或者金龙道途会将2d6变成2d10）。
  - 奥法后继者
    - 奥法后继者版本的远见打击，只持续1轮而非2轮。
    - 奥法后继者版本的奥法精准，AB加值还是根据智力计算而非魅力。
  - 魔能射手
    - 开启远程法术打击以后，瞬发射线法术并不消耗瞬发权杖
    - 开启远程法术打击以后，射线法术的射程变成跟武器一致（与不提升法术的射程的描述不符）。
- 刺客
  - 刺客能力中所有的可以无视条件造成偷袭的效果：实际上是视敌人为措手不及状态，比描述的效果强很多
- 诗人
  - 切利亚克斯歌后
    - 【炽热回旋曲】：不能正确触发专长【不协之音】；此能力导致的疲劳状态可以通过暂停来消除。---未修复
    - 【夺命颤音】：只有对敌人生效的吟游演绎才能触发，用勇气颂歌之类的盟友加成类演绎则无法触发。---未修复
  - 驯兽师
    - UI界面没有显示职业能力，实际上会扩表以下法术：一环魔牙、二环熊之型、三环高等魔牙、四环狼之型、五环动物异变、六环原始退行
    - 10级能力提供的魔牙不生效
- 魔法欺诈师
  - 伪名流
    - 【孱弱颂歌】降低敌人4强韧豁免，而游戏中效果是+4强韧豁免。
  - 弄时者
    - 1级能力【时间跳跃】无效
  - 融合法术
    - 融合法术可以绕过敌人的免疫（约等于宗师之杖的无视法术免疫的效果）。---未修复
    - 融合法术可以吃到法术专攻和元素专攻的加成，但是不受到装备的有关“元素描述符”相关的加成，比如<最后的阿兹兰特人的传承>护符。---未修复
    - 融合法术可以通过宗师之杖（不能是融合法术）、癫狂灾瘟（强极效）、适时援助（延时）、反应施术（瞬发）、奥法维持之靴（瞬发）和魔法旋风之靴（瞬发）进行超魔。---未修复
    - 融合法术中，鬼影迷雾等地形法术融合，无法触发另一个被融合法术的效果【地形法术没有触发目标，所以无法造成效果；解决办法是不用地形法术的法术范围，而是选择非地形法术的范围，比如雪球术/鬼影迷雾，法术范围选择单体目标，这样会在被选择目标的位置造成地形效果（法术指示器有提示）】。---未修复
- 战士
  - 双手武器战士：11级的【大力士】会自动在整轮攻击中触发，导致敌人被撞飞从而打断自己的整轮攻击。
  - 泰坦战士
    - 高等魔化武器（副手）、磨锋砺刃（副手）对双持双手武器的副武器无效
    - 重臂护腕对双持双手武器的副武器，效果翻倍了，+6伤害
    - 
- 法师
  - 奥法爆破师
    - 奥法爆破师兼职掷弹兵后，伤害骰成长会相加
    - 兼职情况下，奥法爆破师的炸弹在吃到精准掷弹混合物的1倍额外智力调整时能保持原来的AOE泼贱特性
    - 和很多带延迟伤害的酸系法术一样，掷弹连续的酸炸弹可以每次都触发一个额外伤害
    - （炼金术士）定向爆破对单个敌人有一个等于智调的基础值伤害，不知道来源，随手投掷+精准混合物+基础值=3倍智力调整；对群时，是其中一个3倍，其余没有智力调整值

- 武僧
  - 两仪回风：用双武器战斗（比如双持十手）和快速射击的同时还能获得两仪回风的额外攻击次数效果（不符合描述）【测试版的时候只改了禅宗射手的两仪回风的BUG】
  - 僧兵
    - 两仪回风：11级额外两次满BAB攻击的效果在读档存档后失效（只保留6级的额外1次），需要切换武器刷新状态才能恢复。
- 战斗祭司
  - 祝福（破坏）：1级能力【破坏打击】的增伤效果是人物等级的一半的士气加值（这符合规则书和游戏内的描述，**不属于BUG**）
- 操念使
  - UI界面没有显示职业能力【注能熟稔】：5、8、11、14、17、20级分别可以降低一点注能的超载。最多减少6点注能的超载。
  - 死地和云形，释放瞬间只要敌人在法术范围内，就会造成两次伤害。
  - 龙形态不能凝聚
  - 手持念刃后，通过变形-保存并退出到主菜单-读取存档-副手念刃
  - 要害打击等可以跳过凝聚
  - 即时制手动操作可以跳过凝聚，或者通过切换凝聚选项来用移动动作白嫖更好的凝聚效果。
- 炼金术士
  - 活体解剖师
    - 20级额外多出一个研究发现而UI界面显示为“×”。
    - 复用了进阶天赋图标，导致玩家容易误认为活体解剖师可以通过医学发现来点出“机会主义者”等高级游荡者天赋（实际上能选的列表是跟医学发现一致的）。
  - 熏香师
    - 崇圣烟雾可以通过移动让敌人反复进出范围的方式实现一回合内多次强韧检定，
- 术士
  - 地卜师
    - 【地相术】的DC不正确，不与法术实际DC一致，而是仅计算基础DC（10+环位+属性调整值）。
- 牧师
  - 异见先驱
    - 【禁忌典仪】：选动物时，仍按-3等级而非-5等级算，即6级拿3级动物。【注：不是BUG。这个符合动物领域的描述，你的有效德鲁伊等级等于赋予你领域的职业等级-3】


- 化形师
  - 化形师利爪的副手攻击，会跟主手一样受到酒僧、加速术、杰作之锤、道途能力等加成，同时吃打数增益；且和化形师狂怒交互有问题，可以实现狂怒咬/顶，同时主、副手是啊同时吃打数增益，且加速术应该是作用于爪子而非狂怒选择的武器。特殊情况下，还可以凭空卡出1打。
- 骑将
  - 挑战和护符伤害可能被永久添加到面板，大概是被终劈斩引起。
  - 宝剑骑士团的骑乘大师伤害计算错误，会多次累加骑乘大师的伤害加成，原因未知。
- 德鲁伊
  - 凛冬之子的暴风雪元素在回合制触发借机攻击时可能会一直进行借机直到敌人死亡，哪怕敌人已经离开攻击范围。**不知道是否修复。**
- 杀手
  - 处刑者：【刺杀专攻】（对类人生物研究目标+1，非类人生物研究目标-1），这里“类人生物”的判定范围异常（测试结果包括：对元素生物--异界，龙，恶魔，人形怪物，植物，不死生物，动物），几乎所有敌人生效。
- 萨满

  - 用游荡精魂可以学习其他魂域的巫术，且切换游荡精魂以后也不会让获得的其他魂域巫术失效。

- 兼职
  - 神卫猎师/圣职杀手可以通过兼职一级圣裁猎手，来补回替换掉的审判能力（审判只有一次，但是加值受到审判官等级影响）
  - 步武客可以通过兼职圣职杀手/圣系学识补回替换掉的研究目标（且研究目标等级随步武客职业等级成长--研究目标加值是独立的，关联的是杀手、圣杀、圣系学士的等级）。
  - 荒野塑像虽然替换掉了感上防，但兼职一级武僧获得感上防以后，还是能拿到每4级加1的ac。
- 武器训练
  - 双手武器战士的双手武训和僧兵/利矛从者的武训加值可以叠加，而且同时受到决斗手套之类装备的加成。
- 弱化创伤：只计算了游荡者和杀手等级而不是人物等级（目前测试的圣杀和滋事者的弱化创伤都无效---因为只减少0dr），削弱dr效果同时还不符合描述地等值削弱了所有能量抗性。
- 领域：荣耀领域的光辉之触，不能正常加成沟通相关的技能检定（目前只能加成使用魔法装置的检定）。
- 启示
  - 动物之友
    - 有两个单位都有动物之友的时候，动物获得的豁免加成只取决于后触发的一个（触发时机是进入光环范围的时候，所以待在光环里的队友受到的豁免加成效果不会动态变化，所有光环系BUG同理），其中一个（称为A）离开，动物会失去加值；离开的那个回来时动物获得A的魅力加值豁免，哪怕B比A高。魅力值改变也会发生类似的情况。【嘛，正常也不会有两个动物之友】

  - 降祸
    - 双咒先知的降祸不会给部分敌人上（通常是原本可交互的中立单位，如市集广场的胡尔伦、混种人）。【触发时机是进入光环范围的时候，所以待在光环里的人受到的豁免加成效果不会动态变化，所有光环系BUG同理】
- 动物伙伴

  - 野猪：七级的+2AC无法触发
  - 



#### 装备

- 癫狂之灾：可以强行将本不能强效和极效的法术进行强极效超魔 - **未修复**，也可能原来的法术不能强效和极效才是BUG？
- 高奏凯歌之戒：对先攻和法穿的士气加值，无法翻倍
- 阴影宽恕（戒指）：触发效果召唤出来的蜘蛛死了会继续触发效果，相当于只要有一只蜘蛛就可以无限刷蜘蛛。
- 嗅血斗篷：对先觉斗士的凝神狂暴无效
- 超魔权杖：
  - 瞬发超魔权杖系列和德莱文的帽子：即时制通过某些操作，可以不消耗次数使用瞬发效果。
  - 噬心浪欲、夺命暴雪权杖等转换伤害的附属效果只要激活后就可以生效，只要不使用超魔效果就不会消耗次数（比如酷热之风，施法后再激活噬心浪欲/夺命暴雪；或者魔法欺诈师融合法术+噬心浪欲白嫖转伤害效果）。
  - 洞穿超魔权杖系列无法正常生效，敌人的法术抗力并不会-5
- 动物之怒（护腕）：原本效果为变形以后攻击的伤害和AB+3【增强加值】；目前伤害变成了【其他加值】（显示在面板），AB变成了隐藏的其他加值（不在日志中显示，但是实际上总值+3AB）。
- 拉兹米尔的面具：每轮一次自由动作施法，会被非法术的其他能力消耗掉，比如恶魔狂怒（本身就是自由动作）。
- 女继承人之指：用灵魂之灾等任意能力给队友加状态的时候，也可以额外给队友+2AC、2AB和2伤害，甚至用武器攻击、法术和任意能力影响敌人的时候也可以给敌人加成。
- 佐恩库松的窒爱：效果为受到电系伤害以后，下一轮内的电系法术可以瞬发，这里电系法术不包括通过转伤害手段改变元素描述符的法术（比如转电的地狱烈焰射线就不能瞬发）。
- 位面引航（戒指）：不止6环内的召唤法术，而是所有召唤法术都会被极效（描述符里有召唤的即可）。【注：新版本操纵亡者系列法术也有召唤描述符了，因此会受到梦境之书和高等召唤的影响】
- 临危之戒：与描述不符，伤害加值是其他，而非表现。
- 杰作之锤：BUFF效果仅考虑接受buff瞬间的状态，也就是说切换装备栏并不会让BUFF效果变化。而且三个类型的BUFF效果叠加，切换装备的话可以实现额外+3次满BAB攻击。
- 札欧瑞丝的美丽（戒指）：对夹击的敌人，额外伤害和额外AB均无效
- 恶意倒钩链甲：BUFF持续时间为永久而不是一轮

#### 神话道途

- 巫妖
  - 巫妖之力 - 污染偷袭：武器易伤目前为止还没实装，只有元素易伤效果
  - 巫妖之力 - 元素之死：可以把全部伤害转换为负能量，而不只是元素伤害
- 灵使
  - 法术 - 不破链接：免疫心智等一系列免疫只对10尺范围内盟友有效（跟描述不符）
  - 惊世神力：目前变成了双倍效果，有两个士气加值，其中一个会被高奏凯歌之戒翻倍
  - 灵动魔法：魔战士法术超魔能力、法术大师的法术超魔能力、癫狂灾瘟的强效极效超魔等临时BUFF类超魔效果，对分裂出去的另一个法术无效
- 天使
  - 法术 - 烈阳之眼：没有超魔孔位（无法在法术书界面超魔），可以通过宗师之杖进行强效极效超魔。
  - 法术 - 净化烈焰：没有超魔孔位（无法在法术书界面超魔）且无法通过超魔权杖超魔，只能靠魔战士法术超魔能力、法术大师的法术超魔能力、癫狂灾瘟的强效极效超魔等临时BUFF类超魔效果进行强效极效。
- 恶魔
  - 法术 - **深渊风暴**：不能受到爆燃魔相的伤害骰加成。
  - 法术 - **吞噬**：没有增效、强效极效的超魔孔位且无法通过超魔权杖超魔。只能靠魔战士法术超魔能力、法术大师的法术超魔能力、癫狂灾瘟的强效极效超魔等临时BUFF类超魔效果进行强效极效。
  - 爆燃魔相：无法加成一些法术的伤害骰，比如吞噬、深渊风暴、力场爆发等法术。
  - 空奢魔相：即时制使用移动动作施法时，如果同时下达过多指令，容易把这个移动动作法术卡掉。【注：尽量在回合制的时候使用】
  - 擒奴魔相：额外攻击的触发距离无限制（这个比较反常识，但是也没有明确说明不能这样触发）
  - 法术变形为恶魔：读档后变形自带的天生武器消失（据说），比如可以卡整轮攻击的每次攻击都附带电爪（配合法术打击）
- 金龙
  - 龙族专长：可以通过额外游荡者特技、额外杀手特技和额外科研发现（活体解剖师），来点出诡计大师的精通精通重击系列专长。【归于BUG的依据在于设计师对于博学士的BUG修复的尝试---让博学士不能在没有察觉2阶的情况下，选择察觉2阶专长】

#### 特殊机制

- 骑乘
  - 坐骑和骑者的触及范围不一致时，回合制容易导致丢失整轮动作的攻击。【所以建议拿斩矛等长触及武器的骑乘就不出突刺，坐骑出突刺；拿非长触及武器的骑乘，则两者都出突刺】

- 免疫能力的交互错误
  - 免疫毒素可以错误的免疫非毒素效应的反胃效果（比如恶魔有毒素免疫，从而免疫圣战之人/杂音灌耳之类的反胃）
  - 不死生物无法免疫炼金炸弹造成的恶心和反胃。
- 法术书的施法者等级提升（传奇道途相关）
  - 先知20级后进阶职业不涨cl
- 法术的隐匿加值叠加，以及跟真知术/识破隐形的效果交互错误。
  - 不同隐形法术可堆叠隐匿加值，而真知术/识破隐形的实现效果似乎只是对抗隐形法术时+20察觉而不是无视隐形法术的隐匿加值。
- 远程武器冲锋
  - 刺尾师之子，点出精通徒手击打以后，可以原地冲锋然后打出远程攻击（第一次攻击还会额外附带一次徒手击打伤害），以及可以触发部分箭筒的特效（比如圣化复仇箭筒和玫瑰刺弹药箭筒）且不消耗次数。
- 回合制和即时制切换（战斗中）
  - 可以无限次白嫖五尺快步
  - 每次切换等于重新开战，回合制后续行动的敌人都视为措手不及。
  - 切换后会打断敌人和我方动作，卡掉敌人输出，甚至还能实现无限“我的回合，还是我的回合”。
- 飞翔攻击：
  - 无法触发猪突猛进护腕的效果（冲锋发动天生武器攻击时，第一次伤害骰提高3级）。
  - 骑手使用飞翔攻击，有概率会卡掉整轮攻击。
- 飞行、飞空和地面效应交互没有规律
  - 飞空飞翼可以被缝隙系法术（比如次元坑）影响；飞翼会吃到凛冬之握的伤害然而不会俯卧（估计是因为凛冬之握和狮鹫之心一起出，所以特意做的），飞空则免疫。
- 骑乘
  - 奋力冲刺和长矛冲锋额外1倍的效果，有时候会消失，需要上下马来解决。
- 破敌：
  - 活物破敌可以跟任意非万物破敌叠加，也可以跟武器原有的活物破敌叠加（比如圣战之刃+死亡武器+除患者，有6d6伤害）
- 奥术失败率
  - 兼职那些自带穿甲施法的奥术职业时，其效果会作用于全部法术书，而不是描述的仅限本职业的法术书（比如兼职1级歌者可以穿中甲和持盾，使用法师法术书也不会有奥术失败率）
- 卷轴
  - 使用变形效应的法术卷轴，存档读档后会失去相关的变化自如和天生防御的加成。
  - 无法制作带有分支的卷轴，比如高等解除魔法（分支-目标型和范围型）。
  - 玩家制作的卷轴，其DC和施法者等级不受到卷轴专家的能力影响。
- 法术甄选
  - 与描述不符，可以对持续时间不为立即的法术生效，比如甄选油腻术、甄选热风术、甄选剑刃障壁（这个敌人也会用）等
- 无视法术免疫
  - 宗师之杖/夺命魔法，这类无视法术免疫的效果，基本上只对诡影杀手生效。比如对免疫惑控的敌人使用神威如岳，敌人还是会直接免疫。
- 变形
  - 装备某些武器，变形以后还能享受到武器的附魔效果，比如灰烬制造者（变形以后也能+2AB），传奇英雄长枪（冲锋攻击额外造成8d6伤害），~~残缺天使~~（对邪恶敌人+5AB），滑溜木棍（+1AC【表现】），女继承人之指等
  - 变形以后不享受任何额外增加天生武器攻击的增益（不清楚是BUG还是设定）
- 额外增加天生武器攻击
  - 动物伙伴 靠装备和兽类冲动等，获得了额外的天生武器攻击，这部分攻击因为动画缺失，会在一次攻击中全部打出去（以前的擒奴魔和六臂蛇魔之类的也是同样，一刀打出6次伤害）。
- 副手武器
  - 武器自带的追击、高等追击效果，在副手时可以加成副手攻击次数，同时主手武器还能受到加速术之类的加成。
- 武器的元素爆击
  - 焰爆、霜爆、电爆、鸣爆和酸爆附魔无法吃到非武器本身的由专长、能力带来的重击倍率加成。
- 法术伤害计算
  - 同时造成两种类型伤害的法术（地狱烈焰射线，烈阳之眼，炽炎击，深渊风暴等）的第二段法术伤害，会受到某些增伤的二次加成（天命所归和铲奸除恶类型的额外N倍神力伤害，以及正义烙印和辟邪斩类型的增伤）。
    - 具体举例，比如炽焰击20d6（加剧强效极效增效），游戏内存在四舍五入
      - 第一段伤害为120+12【120×0.1】+66【（120+12）×0.5】=198【120×1.1×1.5】
      - 第二段伤害为120+（12+66）×0.5+17【（120+（12+66）×0.5）×0.1】+88【（120+（12+66）×0.5+17）×0.5】=264【（120+120×0.65/2）×1.65】
      - 总伤害变成120×1.65+（120+120×0.65/2）×1.65
      - 加成之前的总伤为240，加成之后的总伤为240×1.65×（1+0.65/4）=460，（1+0.65/4）这部分就是二次加成，这部分只有在增伤数值足够大的时候才明显。
- 加值叠加（其中部分能叠加的加值有一定的合理性，否则会完全否定某些职业能力的价值）
  - 以下均为同类取高，不同类叠加
  - 表现加值叠加
    - 表现加值A类：烛台守卫、为了吾王、勇气颂歌
    - 表现加值B类：猛掷戒指、隼之型、临危之戒、神射护腕、次级神射护腕、夺命姿态
    - 表现加值C类（条件类加值）：迫降护腕
  - 天生防御加值叠加
    - 天生防御加值同类取高部分：法术里的巨灵化身、伟岸雄姿、战法转换和可怖外表，以及所有的变形效应的天防加值（比如化形师的变形）
    - 天生防御加值无条件叠加：骨拳术、动物异变、职业的天防和装备的天防等其他全部天生防御加值
  - 士气加值叠加
    - 不体现在面板的条件类加值：惊世神力（分享），惊世神力（不分享），盛气凌人（鸡蛇骑士团2级能力），旗帜和高等旗帜（骑将）
    - 面板加值：惊世神力面板加值，其他所有体现在面板的士气加值
- 武器骰变化
  - 武器骰升型时计算BUG，重压之刃对特殊武器骰的武器，效果不能和变巨/伟岸叠加（穿甲剑、巨斧、锯齿刀、弯刃大刀）；
- 触及范围变化引起借机攻击
  - 变巨术之类改变体型的法术到期/被解除，导致触及范围发生变化的时候。如果敌人因此脱离了触及范围，会被借机攻击。
- 附伤BUG（具体看队友BD的最后，有详细整理）


#### 专长

- 寓守于攻
  - 远程武器攻击时，可以不正常地触发寓守于攻的AC加成且不会降低AB。
- 不绝连击：“持续直到战斗结束”，然而战斗前的攻击（打动物伙伴等）可以被继承到战斗中。【推测是只有战斗结束才会触发消除计数器的功能，战前攻击不存在战斗结束阶段，不会消除计数器】
- 神话盔甲（中甲耐受 / 重甲强攻）：'盔甲防御等级’的一半，会计算全部不能叠加的加值。
- 神话盔甲（轻甲强攻）：描述中说的娴熟武器，仅限面板本身就有的武器，不包括用战士娴熟或者优雅系列而实现敏上AB的武器。
- 佯攻
  - 杀手佯攻：让敌人进行灵巧检定，失败了则佯攻无效，成功了则佯攻触发（但是面板上有佯攻图标但是无效）；而不是自己用灵巧检定替代哄骗检定
  - 双武器佯攻：不需要牺牲第一次攻击，也不需要使用双武器战斗就能触发（激活能力以后，只要是近战攻击即可）。【也就是说博学士拿了终结佯攻+双武器佯攻，这样整轮攻击第一次攻击会自带终结佯攻效果】
- 连锁施法
  - 目前的实际效果是 **全队** 都需要有这个专长，这样在法术穿透检定中双骰取高，第一次法术也可以；而不是描述中的效果。
- 神话激励（原因推测是神话激励以后会替换掉原来的狂暴战歌，而某些能力和装备并没有关联这个新的狂暴战歌）
  - 歌者学了神话激励以后，自身的【奋不顾身】会失效。
  - 歌者学了神话激励以后，狂暴战歌无法触发狂暴系装备的加成。
- 优雅挥砍和优雅刺击：与描述不符，在单手武器的双手握持模式下也能触发，只不过敏上伤不会变成1.5倍，但是可以触发1.5倍猛力攻击（只需要双手握持或者1.5倍上伤的主要天武）
- 武器娴熟（神话）：有优雅挥砍或优雅刺击，再出【神话娴熟】，优雅挥砍或优雅刺击的所选武器依然会被锁在1倍敏上伤。
- 终势斩：会错误继承上一次攻击的效果，比如奋力冲刺和长矛骑乘的第一次攻击翻倍伤害、要害打击等。
- 所有用AB换伤害的专长
  - 在上次改版之后，都不考虑副手武器和次要天生武器的额外减值。
  - 猛力攻击：在使用空间斩的时候（变成了接触攻击），依旧能使用猛力攻击的伤害加成。【从字面上理解是BUG，但是我感觉是跟猛力攻击描述有关系，猛力攻击这种应该是对能量攻击这种天生是接触攻击的攻击无效】
- 阿尔多瑞决斗精通
  - 与描述不符，需要单手握持决斗剑才可触发（描述中仅需要不持盾、不用副手武器）。
  - 解决办法：把决斗剑切换成单手握持，然后重新装备决斗剑或者来回切换一次武器栏。因为这个能力要单手握持才能触发，然后需要切换武器/存档读档等操作才能刷新。
- 额外真气：只能生效一次
- 破敌施法：高等破敌无法触发【破敌施法】的+2DC效果。
- 骑乘盾牌：数值错误，目前只能计算盾牌的基础AC，而不计算盾牌增强加值。

#### 洗点

以下洗点BUG有部分是因为百宝袋洗点导致的，有部分是原版就有。

- 武僧
  - 鳞甲之拳：洗点以后魅上防还在，而且穿甲和持盾也有效
- 萨满
  - 精魂的11级效果武器附魔，洗点后能保留
- 先知
  - 降祸似乎有洗点BUG，点了降祸然后洗点后不点，仍然有降祸光环效果
- 术士
  - 使用15级亡者血脉的虚体能力，BUFF期间内，效果在洗点后永久保留
- 奥能师
  - 使用坚木躯体，BUFF期间内洗点，效果在洗点后永久保留
- 装备
  - 有武器训练的职业，穿决斗手套/剑师之赐之类的洗点，有机会保留武训或者变成负武训
  - 戴着决斗手套洗点然后点了武器专攻的话会不生效
  - 穿严厉之手洗点，会保留严厉之手的BUFF
  - 穿迫降护腕洗点，有机会保留迫降护腕的效果（且跟本身叠加变成+4）
- 

#### 主线相关

- dlc6的死亡之主战，诈欺师用目标型融合法术不管一轮杀多少都只算一个人头
- 战斗结束后还存在伤害地形法术，然后主角或者队友站在上面对话，最后死亡。又由于没有锁1血系统保护对话被卡掉。
- 御衡的黑洞（神话法术）杀死部分敌人（通常是对话发生前的敌人），会导致不跳出任务对话，任务无法进行
- DLC4的最终BOSS，刺尾狮之力是豁免三骰取高而不是描述里的双骰取高，且与灵使的卓越魔法一起作用时会变成四骰取高。

### BUG修复和改版记录

1. 高等隐形术不能正常生效 - **已修复**
2. **★★★** 迷幻图纹的法术效果没有总HD限制 - **未修复**
3. 天使道途的惑然之缚使用的是御衡者斗篷的效果，对天堂宝剑无效 - **已修复**
4. 荣耀领域的光辉之触，给魅力不正常加值 - **已修复**
5. 回声定位不能正确地无视镜影术效果 - **已修复**，只修复了回声定位法术，类似“回声定位嘉奖”这种BUFF没修。因为这次修复以后出了很多BUG，后续又修了很多次，结果现在又改成最初版，不能无视镜影术了。。。
6. 受诅巫师和先知的诅咒在后期获得时会失去前期加值的问题 - **已修复**
7. 恶魔道途**燃爆魔相**对法术的伤害骰加成未生效 - **已部分修复，个别法术还是不吃加成**
8. 灵使道途的自信之心的加值不正确 - **已修复**
9. 共享宿敌加值跟职业本身宿敌不正常叠加（本来不应该叠加） - **已修复**
10. **★★★** 全队会共享视如仇寇的效果 - 未修复
11. 生命秘示域的启示-灵魂补溢的临时血量效果不是先知等级 - **已修复**
12. 地狱烈焰射线的污邪伤害不正常翻倍 - **已修复**
13. 炽焰击和正义焚炎风暴/~~深渊风暴~~ 的 神圣/污染伤害吃双倍的增效加成 - **未修复**
14. 狐狸种族在使用变形法术后再通过灵狐变形变为人形，变形属性不再保留。
15. 部分商人（如军需官、骷髅商人、牧师）在推进剧情以后会刷新物品，导致玩家可以重复购买相同装备和武器（如扫荡、书呆子头冠和迫降护腕等） - **已修复**
16. 恶魔道途的披风<惑然之缚>，计算恶魔狂暴和魔相的等级+3的效果无效 - **已修复**
17. **护命会让重击变为普通攻击，可以正常防止被抓准时机、包抄导致的借机攻击了，而且也不能触发基于重击的其他专长。---==关键==**
18. **抓准时机不能使让未被确认的重击触发借机攻击。---==关键==**，一直都不行，但是一直有人说某某贴子测试说有，我6.3号实测没有这种机制。
19. 解除魔法和高等解除魔法等解法的d20检定，现在能正确享受幸运领域的双骰取高和诡计大师的捉弄命运锁20
20. 解除魔法和高等解除魔法等解法的施法者等级检定现在只会进行一次。
21. 锐击戒指自带精准射击效果，但是不会显示在专长面板 - **已修复**
22. **★★★** 癫狂之灾可以强行将本不能强效和极效的法术进行强极效超魔 - **未修复**，也可能原来的法术不能强效和极效才是BUG？
23. 心灵控制护目镜增加全法术学派2CL【天赋加值】未生效 - **已修复，修改了描述：CL仅对心智法术生效**
24. **★★★** 所有效果体现在面板的临时武器附魔法术，比如~~祝福武器和圣战之刃~~（修复了）、圣剑术和魔化武器等法术不能被正常双持久 - 未修复
25. 灵使的灵动魔法现版本作为一种施法增强能力对“类法术能力”有效（尽管之前补丁说砍掉了作用于能力）- **已修复**
26. 游荡者进阶天赋-【解除】，在解除魔法的施法者等级检定中必定取20，且DC为0；辉光和神圣驱逐给与的解除魔法CL固定为1，不随等级成长。-**2.10完全修复**
27. 善念僧袍对邪恶敌人获得+2AC【闪避】和+2AB【表现】，其中AB加值无效 - **已修复，AC的闪避加值实际为其他加值**
28. 针对某类目标的AC加值【偏斜/崇圣】，与常驻的AC加值【偏斜/崇圣】叠加，比如辟邪斩/天堂面纱的AC加值【崇圣】可以跟金鹰之魂/忠诚祝福的AC加值【崇圣】叠加，伟岸雄姿/可怖外表和变形的天生防御AC叠加 - **已修复，都不叠加了**
29. 神眷猎人选择战争领域的扩表无效 - **已修复**
30. 流风秘示域不能选择正常选择启示：无影无踪 - **已修复**
31. 《咒法与召唤的二元性》不能刷出充足怒火卷轴 - **2.10修复** 
32. **魔化防具BUG修复，目前只作用于盔甲，而且与盔甲本身增强加值取高而非叠加**
33. **★★★** 巫妖道途的污染偷袭，武器易伤目前为止还没实装，只有元素易伤效果 - 未修复 
34. **★★★** 活物破敌可以跟任意非万物破敌叠加，也可以跟武器原有的活物破敌叠加（比如圣战之刃+死亡武器+除患者，有6d6伤害） - 未修复 
35. 战士的双武训BUG，比如飞斧同时吃斧和投掷武器的武器训练加成，这个武器训练又分别受到决斗手套的加成。-**已修复**
36. 免疫俯卧的敌人现在不免疫狂笑效果了
37. “专长列表范围修复“，目前战士战斗专长、魔战士的魔战士专长等都能学到察觉2阶的精通精通重击系列专长。
38. ~~禅宗射手的武僧专长不能选择精准射击等一系列远程专长，预计很多替换了职业可选专长列表的职业都有这个BUG~~。-**已修复**
39. 不同来源获得的啮咬攻击次数叠加。 -**已修复**
40. 没有诡计大师的察觉2阶，博学士的战士专长、游荡者秘闻的战斗特技可以无视察觉2阶限制选择“精通精通重击”系列专长。 -2.1.0U版修复一半，目前游荡者秘闻还可以选
41. **装备**：高尚裁决、贾西各斯、自然之怒巨木棒、带钉木棒、暗蚀巨镰、狂奔之靴和恶毒附魔的额外伤害修复。
42. **能力**：天使之击、神话冲锋、引领打击的额外伤害修复。
43. **法术**：轰鸣击、火焰烙印、酸液之啮、巨灵化身、吸血鬼之刃、元素评估、太阳印记、吸血鬼之刃的额外伤害修复。
44. 动物之怒护腕、圣兽之爪和永饥寿衣的增强加值不正常叠加 - **已修复**（2.11版本完全修复）
45. 希望使者不朽的爱，盾击时有双倍+5增强加值 - **已修复**
46. **★★★** 高奏凯歌之戒没有让属性和先攻的士气加值翻倍 - **修复了一半，先攻和法穿的部分还是不能翻倍**
47. 神圣之触戒指在空间斩/接触攻击时没有提供伤害加成 - **已修复**
48. 几乎全部变形相关法术都将获得变形标签（比如龙型123、可怖外表、寒冰之躯、火焰之躯、钢铁之躯、狼之型、隼之型、动物之型等），且变形效应只能存在一个，后面的变形效应会消除前面的变形效应。
49. 念刃旋风无超载且用超魔也无额外超载 - **已修复**
50. 闪现术对AOE法术也有失手效果 -**已修复**
51. 辉煌启言可以额外投2次而非1次 -**已修复**
52. 行动自如添加免疫恍惚的描述
53. 猎人动物之力的加成错误（估计是加成不跟职业等级有关而是动物伙伴等级有关的BUG）-**已修复**
54. 步武客的各种姿态加成错误（估计是加成不跟职业等级有关而是角色等级有关的BUG） -**已修复**
55. 勇士赐福可以被延时超魔了
56. 神眷猎人给动物伙伴的天界模板，会让动物伙伴有无限次的辟邪斩-**已修复**
57. 疾病免疫或者维生气泡可以完全免疫孢子
58. 可控火球对盟友造成最小伤害
59. 油腻术只对坐骑生效，不影响骑乘中的骑手了
60. 圣职杀手7级将获得迅捷研究
61. （高等）阴影咒法可以用延时超魔了；（高等）阴影塑能可以用极效、增效和及远超魔了 -**现在阴影塑能又不能主动超魔增效强效极效了**
62. 巨嗣杀手的研究大型生物特性正确生效了
63. 不同队友的研究目标可以作用于同一个敌人了
64. 花豹4级体型奖励变成+2敏和2体，而不是+4体4力-2敏了。---DLC6版本又改回去了，无语
65. 寒冰之躯现在赋予目标对力竭和疲劳状态的免疫；
66. 怒涛碎击专长不需要过攻击和豁免检定 -**已修复**
67. 火焰之躯没给徒手攻击而是爪击 -**已修复**
68. 强力冲锋（奋力冲刺）的伤害计算错误 - **已修复**
69. 魔化武器和高等武器（至少为+2的时候）叠加，且跟武器本身加值叠加 - **已修复**（目前只取最高值）
70. 要害打击、要害打击（神话）造成的伤害可以被重击翻倍 - **已修复**，要害打击算是入土了
71. **装备**：衰弱折磨头盔、缜密步履、以眼还眼、圣兽之爪、部族斥候革甲、精准手套、快速应敌护符的额外伤害修复【2023/3/22】。
72. 武器的加成只作用于该武器，比如拿速杀变形不再能吃到速杀的特效了。-部分描述为持用者加成的武器，变形以后还能使用武器效果
73. **能力**：神之敌、揭示弱点的额外伤害修复【2023/3/22】。
74. 刺尾狮的天生投掷武器不再能用灵巧之拳护符实现敏上伤。
75. 潮汐奔涌也会解除非火焰法术 - **已修复**
76. 棕毛变化师的分享变化可以作用于敌人 -**已修复**
77. 可以通过超魔界面将魔法从一个角色转移到另一个角色 -**已修复**
78. 分裂射击会击杀盟友 -**已修复**
79. 魔战士的法术打击应用的是武器重击倍率  -**已修复**，目前法术打击的重击倍率与武器无关
80. 飞镖是轻型武器而不再是单手武器。
81. 鳞甲之拳的魅上防，不再能跟先觉斗士/化形师的感上防叠加（二选一）。
82. 要害打击可以受益于冲锋攻击 -**已修复**
83. 圣徽的寒铁和善良附魔可以对次要天生武器生效了。
84. 迅猛龙的攻击次数受到BAB加成两次，而非不吃BAB加成。-**已修复**
85. 由于代码限制，光环效果无法在超过37英尺的距离外生效 -**已修复**
86. 升级时如果专长列表里的专长都不可选，就不能升级。-**已修复**
87. 使用快速投掷和快速射击的时候，攻击次数和攻击加值惩罚不正确。-**已修复**
88. **★★★** 巫妖道途的元素之死，可以把全部伤害转换为负能量，而不只是元素伤害。-未修复
89. **★★★** 灵使道途的不破链接，免疫心智等一系列免疫只对10尺范围内盟友有效（跟描述不符）。-未修复
90. **★★★** ”灵狐猛扑“专长任意形态都可以提供猛扑能力，而不是描述里的灵狐形态才行。-未修复
91. 狐人变形为人类以后也有啮咬攻击，而不是描述里的灵狐形态才行。-**已修复**
92. 匕首吃双倍的夺命姿态加值，以及双倍的猛力姿态加值。-未修复？？？，待测试
93. 阴影宽恕戒指，目前只会对昏迷的队友触发，而非盟友。-但是触发效果召唤出来的蜘蛛死了会继续触发效果
94. 念袭不再受益于天武护符
95. 银隼修复，现在重击后会正确造成2d4的AOE力场伤害；轰烈的伤害修复（即不吃难度调整了）
96. 圣触、纵火狂之戒的附伤BUG修复【附伤BUG在队友BD部分有单独总结】
97. 厄运的伤害修复，<马兰德的耻辱>短剑的污邪附魔伤害修复（意义不明）
98. **★★★** 先觉斗士：暴力呼召斗篷可以对凝神狂暴（Focused Rage）生效【注：对嗅血斗篷还是无效】，可以选择额外狂暴特技了
99. 光能附魔现在可以正确运用在要害打击的攻击中
100. 神使灵光可以延时超魔了
101. 融血师给召唤出来的不死生物的加成从4体质改成4魅力
102. 祝福武器和圣战之刃可以双持久了，且变成BUFF形式，更换武器也会对主手武器附魔（也就是说不能切换武器附魔副手了）
103. 反应施术不会对戏法生效了
104. 强力冲锋在冲锋中没有将任何武器的威胁范围扩大一倍 -**已修复**
105. Serenity effect no longer allows critical hits（宁静效果不再允许暴击？）
106. Skill points were not increasing from Intelligence if the Inherent modifier was used to increase the characteristic — fixed;（天赋加值可以正确增加技能点了）
107. Skald now grants their allies passive "Inspire Ferocity" effect;（歌者现在赋予他们的盟友被动的“激励狂暴”效果？）
108. Some bosses didn't have the immunity for the Mythic Persuasion as they should — fixed;（部分BOSS会获得 神话说服 的免疫？）
109. 战争学徒可以正确无视敌人的免疫重击了
110. 法术专精可以对神话法术生效
111. Student of War ability Mind Over Metal， Oracle's ability Nature's Whispers， and biographies Acolyte and Healer now add the highest characteristic bonus to the armor class;
112. 野蛮人可能会在愤怒之后变得疲惫，即使他们有“无尽的愤怒”的能力。--修复
113. 蛮力变体的动物伙伴，猛兽声威+2AB和伤害，现在变为士气加值而非其他加值。
114. The Heroic Invocation spell did not suppress the fear effects — fixed;（英雄祈神获得了正确的恐惧免疫）
115. 提取某些血统的要求已经被修改了——例如，你不能再选取两个不同的龙血血统
116. 战法转换法术允许角色激活魔法物品 -**已修复**
117. 当变形时，玩家角色不能使用任何物品 -**已修复**
118. 当恶魔之怒时，角色没有获得对眩晕、麻痹、石化、恐惧、眩晕、困惑和其他条件的免疫力——已修复
119. 可以正确选择偏好法术（法术顽强）
120. Oracle's Nature's Whisper and AC Bonus of the Scaled Fist Monk simultaneously gave a bonus to defense — fixed（鳞甲之拳和先知的自然低语，不能叠加了）
121. Successful saving throw against the Drone ability， provides a character with immunity for 24 hours — now works correctly;
122. 太阳形态法术现在通过将天使的神话等级添加到施法者等级来正确计算射线的伤害
123. 心灵迷雾不再叠加两次减值
124. 毁灭域的毁灭灵光的伤害加成现在正确工作
125. 袍泽头盔现在可以正确计算盟友的奖励，而不计算佩戴者
126. 免疫绊摔现在也免疫绊摔战技 -**已修复**
127. 真正的奥术血怒现在根据描述工作（原怒者的奥术血怒？）
128. 各种来源的加速术，加值叠加 -**已修复**
129. Warpriest's Destructive Attacks ability now has the correct type of bonus and correct description of the damage source;
130. Warpriest's Soaring Assault ability is now working correctly with winged characters;
131. 指挥官在游戏结束前的复活超时时间已增加到2轮（12秒）
132. 灵使超音速、天堂宝剑的迅疾流光不再与加速术叠加（就是加速术加值部分）
133. “坚木躯体”不再赋予你植物免疫
134. 大法师护甲不由物品触发，必须自己施法
135. 血怒者血脉的元素打击的附伤BUG修复
136. 超度武器法术将运用正确的DC（Disrupting weapon spell now has a correct DC for saving throw）
137. 例如颂圣之语、混乱之语等全部法术，都不再对施法者造成效果，但是会对全部生物生效。
138. 亡灵血脉的16级虚体血怒，在选择无限狂暴以后，可以无限次使用（Incorporeal Bloodrager effects could be used infinitely if character picked mythic feat Limitless Rage） —已修复
139. 僧兵的两仪回风对武训武器的额外攻击，只在僧兵6级拿到自己的武器训练以后有效
140. 白鹤亮翅现在必须空一只手
141. The Hex Shaman's Chant ability mistakenly extended the effect of the Protective Luck spell — fixed
142. 魅影蛛网的反胃效果，现在对免疫毒素的人正常生效了。
143. 扩充战法BUG修复，现在效果为（法术专攻+高等专攻+神话专攻）×N，N为扩充战法的选择次数。多个学派的法术专攻和高等专攻只会计算一次，~~且不计算神话法术专攻。就是说扩充战法第一次最多让被扩充学派+2DC，第二次扩充战法会让两个被扩充的学派+4DC，以此类推~~。你不能学被扩充学派的法术专攻，否则会导致扩充战法在本学派的加成失效。
144. 僧兵两仪回风在存档时会失效 -**已修复**
145. 金龙道途神话10现在会正确增加8感知【应该是BUG修复】
146. **★★★** 新发现的双武训BUG，双手武器战士的武训和僧兵/利矛从者的武训叠加。
147. 游侠流派专长在升级时不能选取，原怒者血脉能力换狂暴特技的在升级时不能选取，地狱骑士的五誓不能选取。---修复
148. 射线多段偷袭的BUG修复，现在多段射线只能吃到一次偷袭骰的加成。
149. 枕戈待旦、动若脱兔等跟武器训练等级相关的能力，在存档和读档后会失效，得切换武器才能恢复。---**已修复**
150. **★★★** 兼职歌者以后，受到歌者的狂暴战歌影响下，不会禁止施法（甚至战法转换以后还能施法）。-未修复
151. **★★★** 高奏凯歌之戒没有让改版后的惊世神力的士气加值翻倍，但是惊世神力的士气加值~~现在跟其他士气加值叠加~~<ins>   新版本变成惊世神力双倍效果，有两个士气加值，其中一个会被高奏凯歌之戒翻倍</ins>。-未修复
152. **★★★** ~~圣战之刃改版后，圣战之刃的邪恶异界生物破敌效果，可以跟武器的邪恶异界破敌效果叠加，额外伤害变成4d6~~，且可以切换武器生效，让远程武器也受到圣战之刃的加成。
153. 现在秘银重甲除了需要重甲擅长以外，其他都是吃中甲的效果（比如神话中甲专攻、中甲专攻）。秘银中甲也同理，吃轻甲的效果（比如神话轻甲专攻、轻甲专攻）。
154. 武器娴熟+战士娴熟+神话武器娴熟可以让弩拥有1.5倍敏上伤---**已修复**
155. 利矛从者可以使用长柄武器训练（即斩矛、大砍刀和新月战斧）。
156. 寒冷领域和冰子域的2环领域法术变为灼热射线（寒冷）而不是强酸箭。---妈的只改了描述，实际上还是强酸箭
157. 魔源使的魔源汹涌可以同时加成法术的DC和CL了。注：图标还是两个，但是使用**难度等级（魔源汹涌）**同时也会增加法术的施法者等级。
158. 萨满的巫术避灾，目前不吃诵咒的延长时间。---已修复
159. 恶魔道途擒奴魔相配合变狼等啮咬带绊摔的生物，可以无限连击【修改方式为免疫俯卧的敌人免疫绊摔战技】。-**已修复**
160. **★★★** 即时制可以通过操作来无限次使用瞬发权杖。---未修复
161. **★★★** 魔能射手开启法术打击以后，瞬发射线法术并不消耗瞬发权杖。合理怀疑是因为瞬发射线法打也有一段动画，并不是瞬发了（但是回合制还是用的迅捷动作）。---未修复
162. **★★★** 博学士可以额外学习一次法术专精，同时专精两个法术或者专精一个法术两次。
163. 烈阳之眼在敌人豁免成功以后伤害减半而非变成d12，但是用噬心浪欲转污邪以后，伤害就正常了。---**已修复**
164. **★★★** **深渊风暴**：~~敌人豁免成功后，伤害只会降低25%（这是把灵使的卓越魔法偷了？）；用噬心浪欲转污邪以后，敌人豁免成功也不会降低所受伤害~~；深渊风暴不能受到爆燃魔相的伤害骰加成---未修复
165. **★★★** 刺客的”可以无视条件造成偷袭“的效果，实际上是视敌人为措手不及状态，比描述的效果强很多。---未修复
166. **★★★** 神卫猎师可以通过兼职一级圣裁猎手，来补回替换掉的审判能力；同理步武客可以通过兼职圣职杀手/圣系学识补回替换掉的研究目标。---未修复
167. **★★★** 金龙道途的龙族专长，可以通过额外游荡者特技、额外杀手特技和额外科研发现（活体解剖师），来点出诡计大师的精通精通重击系列专长。---未修复？
168. **★★★** DLC3单独开档的时候，巫妖转传奇会额外送3级施法者等级，导致传奇的法术书施法者等级上限从28变成31。---未修复
169. **★★★** 兼职那些自带穿甲施法的奥术职业时，其效果会作用于全部法术书，而不是描述的仅限本职业的法术书（比如兼职1级歌者可以穿中甲和持盾，使用法师法术书也不会有奥术失败率）。---未修复
170. **★★★** 兼职歌者以后开启战法转换，在受到队友歌者的狂暴战歌 或者 自己使用狂暴战歌以后，战法转换以后依旧可以施法。---未修复
171. **★★★** 新增的神话盔甲和神话盾牌系列神话专长，但凡有描述 ‘盔甲防御等级’的一半或者全额加成的部分，都有BUG：会计算全部不能叠加的加值。比如神话轻甲强攻，效果是持用娴熟武器可以将1/2的盔甲加值加成到AB上（现在神话轻甲强攻还有个BUG，还附带AB等值的伤害加成），这里1/2的盔甲加值会计算本不能叠加的防御护腕、法师护甲、大法师护甲和盔甲的全部加值。---2.3版本修复（仅剩下中甲耐受和重甲强攻）
172. 爱乌体型变为大体型以后，模型的鼠标选取范围将变得非常大，跟爱乌的攻击距离一致。---2.3版本修复
173. 魔能射手的远程法术战斗无法开启 ---已修复
174. **★★★** 杀手佯攻是让敌人进行灵巧检定，失败了则佯攻无效，成功了则佯攻有效；而不是自己用灵巧检定替代哄骗检定。~~终结佯攻无效，听说得至少两个人点出来才能生效，变成团队专长~~。---部分修复
175. 游荡者的错乱之创无效、石化打击无效。---已修复
176. 游荡者的巧记训练中没有锯齿刀。---已修复
177. 欺诈者的融合法术没有正确从所有描述符中受益——已修复
178. 修复了某些原型的宠物进度滞后于角色1级的问题。现在你可以从3级升到4级；
179. 修复了圣战者之刃法术的恶心/反胃效果不仅在暴击时生效，而是也在普通攻击时生效的问题；
180. 修复了与深黯军团骑士相关的错误：
     - 飞行攻击能力的远程攻击导致敌人产生了借机攻击——已修复；
     - 飞行攻击能力中的攻击未被视为冲锋攻击——已修复；
       - **坐骑的飞行攻击，目前也会正确触发骑手的冲锋攻击，也就是说以前坐骑飞行攻击，骑手白嫖整轮攻击的效果不存在了，必须搭配猛扑**。
     - 风卷残云能力现在不仅可以由鷲马使用，还可以由坐在鷲马的骑士使用（显示为自由动作释放---应用该能力仍然使用鷲马的标准动作）。现在不需要在战斗中每次都切换到鷲马（这在主机的回合制模式中是不可能的）。
     - 鷲马伙伴未获得宿敌加成---2.4.0x修复
     - 飞行攻击无法正确运用于集群敌人 ---2.4.0x修复
     - 现在深黯军团骑士在快速访问栏上具有鷲马伙伴的“飞行攻击能力”
     - 骑手的飞行攻击，目前可以正确触发猛扑和奋力冲刺等能力
181. 修复了导致坐骑在“冲锋攻击”中未总是进行攻击以及其他冲锋攻击问题的错误。现在，无论是坐骑还是骑士使用冲锋攻击，都会始终进行一次攻击并获得相应的加成。如果骑士在使用冲锋攻击时手持远程武器，骑士会进行完整攻击而没有冲锋加成。
182. 寒冰子域和流水领域的法术表现在正确显示
183. **★★★** 切利亚克斯歌后：
     1. 【炽热回旋曲】：不能正确触发专长【不协之音】；此能力导致的疲劳状态可以通过暂停来消除。---未修复
     2. 【夺命颤音】：只有对敌人生效的吟游演绎才能触发，用勇气颂歌之类的盟友加成类演绎则无法触发。---未修复
184. 现在在竞技场战斗中，角色将出现在他们的坐骑上；
185. 【化形师之爪】专长现在正确工作---待测试。
186. 奥法契约无法恢复术士之类的自发法术位【注：即修复到最初版本，奥法契约分为自发施法版和准备施法版本，分别可以恢复对应的法术位】 ---已修复
187. 博学士可以选择 审判官--宣典官 的法术书。
188. 豪勇念力可以当作寓守于攻来作为佯攻的先决专长。
189. 塔西伦专精法师现在可以从 DLC 中选择法术。
190. 宣诏英烈的职业能力在19级消失而非升级。---修复
191. 念刃现在可以进行借机攻击了。（Fixed an issue with kinetic blade,  which prevented characters from making an attack of opportunity;）
192. 天使道途的高等天堂宝剑【迅捷流光】现在会额外提供两次攻击，而不是一次。
193. 如果乌布里格在第5章加入并且玩家角色是传奇，乌布里格将获得8个神话等级。【也就是说传奇道途队友保持8神话阶层是设计师本意？】
194. 萨满--灾厄先驱，灾厄精魂现在获得20级能力【显化】（达到20级后，萨满成为疫病精魂，将奈落瘟疫全方面化为己用。她免疫属性伤害、负向等级、精准伤害，也免疫困惑、力竭、疲劳、战栗和恍愡状态此外，她的最大生命值提高体质调整值的两倍。）
195. 重新设计了刃缚魔战士的能力。 20级能力【魔战士真义】已被全新的【战刃真义】能力所取代。当刃缚魔战士手持黑刃或者展示独立自我能力，现在提供 AC 加值（1/4魔战士等级的AC【环境】）；以前19级的击杀恢复奥法点的能力现在在12级可获得，中期续航完美。（Reworked the progression of Bladebound magus archetype. True Magus feat has been replaced with a brand new True Bond feat. Independent Ego ability now provides an AC bonus, when the bladehound is holding their black blade;）
196. 澄清了战斗祭司额外专长的先决条件描述，添加了有关 BAB 的信息
197. 念力射手或者新能力【重击解限】：念力射手的远程武器与念袭变得极为致命。在运用上述攻击时，念力射手的重击威胁范围扩大2点，重击伤害倍率提高2倍，同时用于确认重击的攻击检定也会获得+2加值。
198. 法术破敌专长不适用于宣典官的破敌特殊能力 - 已修复
199. 法术大师的能力“法术集中”现在可以正常运行。？？？
200. 螳螂狂信徒的【红幕】，在13级时通过迅捷动作而不是自由动作使用 - 已修复；
201. 烛台守卫现在是表现加值【应该是实锤了，就是强行把烛台守卫改成表现加值，不是误改】。（Guarded Hearth ability has returned to the previous version of bonus types - fixed;）
     1. 表现加值A类：烛台守卫、为了吾王、勇气颂歌
     2. 表现加值B类：猛掷戒指、隼之型、临危之戒、夺命姿态、神射护腕/次级神射护腕
202. 修复了圣骑士的坐骑进度
203. 修复了魔躯化形师9级不能正常使用恶魔/魔鬼拟态的问题。（Fixed Devil/Demon aspects not working for fiendflesh shifter on level 9;）
204. 修复了玩家在灵使庭院中休息时缺少buff的问题
205. 魔鬼道途的永无休止的战争法令不起作用——已修复（Devil's decree of Never-ending War didn't work - fixed;）
206. 步武客的20级大招【杀戮大师】已重新设计，以使其正常工作
207. 觅血者已经过重新设计，并获得了许多新能力：
     1. 所有需要豁免的血液能力都得到了DC提升。现在的公式是10+觅血者等级+智力调整值。
     2. 血液喷射能力 - 每觅血者等级伤害增加至 1d8。 
     3. 鲜血之锥能力 - 每觅血者等级伤害增加至 1d6。 
     4. 腐肉形态能力 - 现在拥有不死族专长。 
     5. 鲜血之主：达到20级后，觅血者的血统令其血池能力变得更强。他的鲜血喷射、鲜血之锥、弱能术、吸血影障、吸血鬼之触、剧痛射线能力被强效、增效,如同运用了专长“法术强效”和“法术增效”。此外，觅血者的血池点数提高5点,力量、敏捷、智力获得+6天赋加值。还将描述符类型从 亵渎 更改为 直接。
     6. 新增技能——渴求增长（在4、8、12、16级）——增加觅血者撕咬攻击的重击范围1。
208. **★★★** 法术的BUG
     1. 【天堂千翼鸣】：
        1. 现在添加到法师7环和诗人5环；
        2. 魔战士法表里有3环的天堂千翼鸣---未修复
     2. 【高等狂乱之歌】：
        1. 现在添加到诗人6环。
        2. 错误添加到魔战士3环法表---未修复，这个太离谱了，约等于魔战士7级能拿到相当于比正经9环神威如岳还强的法术。
     3. 【净化谢幕曲】：
        1. 某些分支比如 净化谢幕曲（力竭）对敌人释放时，会解除敌人身上的全部法术效果（相当于御衡者归零）。
209. **★★★** 连锁施法：目前的实际效果是 **全队** 都需要有这个专长，这样在法术穿透检定中双骰取高，第一次法术也可以；而不是描述中的效果。
210. 歌者变体-滋事者：12级能力【偷袭技巧】可以正常分享倦惰打击、削弱、石化打击等能力。
211. **★★★** 魔法欺诈师（伪名流）的大招【孱弱颂歌】降低敌人4强韧豁免，而游戏中效果是+4强韧豁免。---未修复？
212. **★★★** 弱化创伤：只计算了游荡者和杀手等级而不是人物等级（目前测试的圣杀和滋事者的弱化创伤都无效---因为只减少0dr），削弱dr效果同时还不正常地等值削弱了全部的能量抗性。---未修复
213. **★★★** 神话激励、狂暴战歌和狂暴特技【奋不顾身】：
     1. 队友无法使用歌者分享的【奋不顾身】能力。
     2. 歌者学了神话激励以后，自身的【奋不顾身】会失效。原因推测是神话激励以后会替换掉原来的狂暴战歌，而奋不顾身并没有关联这个新的狂暴战歌。
     3. 歌者学了神话激励以后，狂暴战歌无法触发狂暴系装备的加成。
214. 斩首附魔修复，目前骰20可以秒杀敌人。
215. 灵使道途-卓越魔法效果修复（豁免减半的法术豁免成功后只减少25%）。
216. **★★★** 灵动魔法：魔战士法术超魔能力、法术大师的法术超魔能力、癫狂灾瘟的强效极效超魔等临时BUFF类超魔效果，对分裂出去的另一个法术无效。-未修复
217. **★★★** 超魔权杖：
     1. 噬心浪欲、夺命暴雪权杖等转换伤害的附属效果只要激活后就可以生效，只要不使用超魔效果就不会消耗次数（比如酷热之风，施法后再激活噬心浪欲/夺命暴雪）---未修复
     2. 瞬发超魔权杖等开关型超魔能力，在即时制可以通过一定手段无限次使用。
218. **★★★** 洞穿超魔权杖系列无法正常生效，敌人的法术抗力并不会-5。---未修复
219. 新版本下，第一次点出法术专攻的同级，不能学法术专精。获得新法术的同级，不能专精这些新获得的法术。
220. **★★★** 魔战士的法术打击：
     1. 回合制下，使用法术打击（远程法术打击不行）可以通过恶魔道途空奢魔相/御衡者高等破敌/拉兹米尔的面具，实现额外一次整轮攻击（比如空奢魔相+拉兹米尔的面具，相当于用自由动作、移动动作、标准动作，分别进行了一次整轮攻击，一个回合内打三个整轮攻击）。---未修复
     2. 魔能射手的远程法术打击，在使用各类瞬发权杖超魔的时候，并不会消耗超魔权杖次数。应该是由于法术打击的动画效果，导致这个施法动作并不是瞬发的所以不消耗（虽然回合制中只消耗了迅捷动作）。
221. **★★★** 可以分享给队友的战法转换（比如棕毛变化师的），在计算BAB加成时按照自身的BAB计算而非受术者本身，比如20级棕毛变化师给队友分享战法转换，会给队友直接+10BAB而不是把队友的BAB补到队友的角色等级。---未修复
222. **★★★** 魔法欺诈师：
     1. 融合法术可以绕过敌人的免疫（约等于宗师之杖的无视法术免疫的效果）。---未修复
     2. 融合法术可以吃到法术专攻和元素专攻的加成，但是不受到装备的有关“元素描述符”相关的加成，比如<最后的阿兹兰特人的传承>护符。---未修复
     3. 融合法术可以通过宗师之杖（不能是融合法术）、癫狂灾瘟（强极效）、适时援助（延时）、反应施术（瞬发）、奥法维持之靴（瞬发）和魔法旋风之靴（瞬发）进行超魔。---未修复
     3. 融合法术中，鬼影迷雾等地形法术融合，无法触发另一个被融合法术的效果。---未修复
223. **★★★** 动物之怒 护腕，效果为变形以后攻击的伤害和AB+3【增强加值】；目前伤害变成了【其他加值】（显示在面板），AB变成了隐藏的其他加值（不在日志中显示，但是实际上总值+3AB）。---未修复
224. **★★★** 用卷轴使用变形效应的法术，存档读档后会失去相关的变化自如和天生防御的加成。
225. **★★★** 佯攻系列：
     1. 杀手佯攻是让敌人进行灵巧检定，失败了则佯攻无效，成功了则佯攻有效；而不是自己用灵巧检定替代哄骗检定。---未修复
     2. 双武器佯攻，不需要牺牲第一次攻击，也不需要使用双武器战斗就能触发（激活能力以后，只要是近战攻击即可）。【也就是说博学士拿了终结佯攻+双武器佯攻，这样整轮攻击第一次攻击会自带终结佯攻效果】---未修复
226. **★★★** 卷轴制作：
     1. 无法制作带有分支的卷轴，比如高等解除魔法（分支-目标型和范围型）。---未修复
     2. 玩家制作的卷轴，其DC和施法者等级不受到卷轴专家的能力影响。---未修复
227. ★★★ 双手武器战士：11级的大力士会自动在整轮攻击中触发，导致敌人被撞飞从而打断自己的整轮攻击。---未修复
228. ★★★ 武器单双手切换：
     1. 优雅挥砍和优雅刺击：与描述不符，敏上伤也可以作用于单手武器的双手握持，只不过敏上伤不会变成1.5倍，但是可以触发1.5倍猛力攻击（只需要双手握持或者1.5倍上伤的主要天武）---未修复
     2. 细剑：目前已经修改成与桌面规则一致，无法属于特殊的双手握持的单手武器。
229. ★★★ 秘法窃取：目前解除魔法的数量没有上限（而不是一个），且每个BUFF单独进行一次掷骰，检定够高的话可以把敌人的BUFF全部转移到自己身上。---未修复
229. ★★★ 天使法术：净化烈焰，现在可以超魔了，只是法术书里没有超魔孔位。---未修复
229. 宗师之杖：现在可以正确超魔十环法术且正常消耗充能次数。
229. ★★★ 恶魔法术：吞噬，没有增效、强效极效的超魔孔位，无法通过权杖超魔。只能靠癫狂灾瘟进行超魔。---未修复
229. 射线法术：地狱烈焰射线和重挫冲击等多段攻击检定的法术，现在只有一次射线攻击会附带攻击的伤害加成（跟射线偷袭的改动类似，比如近程射击、正义烙印、辟邪斩、召唤戒指、祈祷术等全部攻击的伤害加成。记得以前是不附带其他攻击特效但是可以触发多次正义烙印）。



## 最新游戏机制修改讯息

### 截止到2024-9-6号

1. 冰牢的挣脱DC现在变成强韧豁免检定，而且跟挣脱检定跟法术DC一致，目前又很强了；

2. 双持久不再对能力和卷轴生效 --- 诡计大师第四章强度惨遭史诗级削弱，天使道途的大宝剑也不能24H了。

3. 现在**合书**的**自发施法者**升级的时候，神话等级提升以后给的职业法术是固定的，还是可以根据合书总CL获得神话道途法术，但是不能提前获得职业的高环法术了，影响还是很大的，巫妖术士尤其遭重（但是靠博学士扩表/奥术新知还是可以提前拿高环）。

4. **诡计大师道途**：

   1. **察觉2阶新增“数值强化”系列专长**（大部分都是整活专长，只有专长溢出的职业才会选）；

   2. **沟通3阶实装**，现在神话7点出沟通3阶基本上就是无敌了，沟通3阶难度越高越厉害，因为致命一击的DC是{10+BAB+近战伤害属性调整值+武器重击倍率+难度加成}，难度调整的时候，敌人的力量调整值和强韧豁免（体质调整值）是同步增长的，而且高难度下敌人的DC还会有额外难度加成，而且敌人自己打自己的致命一击还会受到不公平难度下伤害翻倍的效果；【2.2版本改为第一轮战斗开始时生效，而非战斗开始时】

   3. 新增魔法亲和权杖，分类为魔杖，可以配合诡计大师UMD2无限次使用。诡计法系逆天加强。

      ![魔法亲和权杖](https://aaathl.oss-cn-hangzhou.aliyuncs.com/img/%E9%AD%94%E6%B3%95%E4%BA%B2%E5%92%8C%E6%9D%83%E6%9D%96.png)

5. **御衡者道途**：新增一系列御衡者凝视和完美形态，后期强度一流，成长曲线也变得平滑了。但是御衡者破敌改动，以前开着御衡者破敌用祈祷术都能AOE解除魔法的效果已经无了。2.10版本以后完美形态只计算基础属性，不考虑加成，也就是最多能把全属性的基础变成22（其实也蛮强了），不影响正常BD后期乱杀。

6. **恶魔道途**：神话9现在会正确获得恶魔领主之相

7. **灵使道途**：同生共死次数现在按照魅力调整值来计算（基本上没啥优先级了）；爱乌的施法者等级被削弱，但是可以穿甲了，而且龙威可以自行选择开关；但是自信之心等一系列灵使法术实装/修复，灵使道途整体强度也没降，**灵使道途依旧是非合书九环职业的成长曲线最平滑的道途（如果主角是9环，别去点垃圾同生共死，神话4卓越魔法，神话6灵动魔法，已经通关了好吧），而且给全队施法者的增益极高**。11月15日再次实装一堆道途法术，秋风扫叶实装，目前灵使卓越魔法+秋风扫叶+顽强，是敌人豁免检定6骰取低。不破链接和友善之拥的一堆免疫实装。生命欢愉的转神圣伤害效果实装。

   1. 道途法术区分，根据灵使道途神话任务的剧情阵营选项，灵使会进入善良（good feature）、”混乱“（collateral feature）和邪恶（devil feature）线，会获得对应的道途法术，具体机制暂不清楚（估计是到第四章、第五章的时候分别进行一次flag检定，跟道途对话的善良/混乱次数有关，都达成了可能有双线法术---目前有人试过先混乱转善良线），但是邪恶线什么都不给。
   2. 善良线：3自信之心、4玄妙自然、5心灵支柱，这三个法术都是灵使道途的核心法术。
   3. 混乱线：3水流击退、4烦扰植被、5音能迸发，这三个法术都是垃圾中的垃圾。

8. **巫妖道途**：墓穴之主能力不再对巫妖自身有效（这个属于BUG修复，因为发售的时候就说了是BUG会改），巫妖术士惨遭削弱（虽然影响的也是后期摆拍）。

9. 新增“说书人的知识”，获得全部精灵书页并交给说书人以后，可以获得说书人的知识，主角的施法者等级+2。【可惜目前这个BUFF经常无缘无故消失，原因就是设置错误，导致触发一次双骰取高以后就会消散】

   ![说书人的知识](images\BUFF\说书人的知识.PNG)

10. 猎人的动物之力修改，从牛虎熊的属性增强加值变为天赋加值，起飞。

11. 专长可以选择突刺了（自由动作，-2AC但是加5近战触及范围），利好全部物理近战菜刀。

12. 击败萨瓦梅勒克后，兰恩或雯朵格可能会从其脊椎上打出一个独特的弓；

13. 爱露莎蕾做完转化任务以后可以获得1/2神话等级的豁免加成【运气】。

14. 兰恩剧情任务会给与自身+2力量【种族】和+2体质【种族】，且对抗毒素效应增加4豁免。

15. 沃尔吉夫接受恶魔力量会获得恶魔起源，+2敏智【亵渎】，免疫电击和毒素，获得10寒冷、10酸蚀和10火焰抗性，且获得异界生物模板，获得11+角色等级的法术抗力。代价是异界生物不能吃缩小和伟岸雄姿的加成（虽然用可怖外表卷轴也行），对于肉搏来说属于有部分削弱的，要谨慎。

16. 从2.1.0版本DLC4开始新增9个法术，1命运丝缕、2凛冬之握（这就是超级无敌版油腻术）、2惧死术、2骨拳术（全队免费1AC）、3燃烧纠缠术（酒馆保卫战的神）、4渴血纠缠术、5腐爆术、5潮汐奔涌，4次元锚（这个好像是做成NPC的法术了）；且萨满法表在此之外还新增（高等）魔化武器、迟缓污泥等法术；法师/术士/奥能师的法表现在新增复仇旋风；这次改动利好德鲁伊、巫师和萨满，可惜科米丽雅16感知购点有点残疾，不然前期会是巨腿。小烬前期强度也提高了不少。

17. 所有的变形效应都可以触发变化自如的加成，且变化自如的加成变成独立加值。**强度上**：变化自如＞神话武器专攻、神话武器专精、神话致命瞄准、神话双武器战斗和神话快速射击等绝大部分物理系神话专长（除了双手的神话猛力和神话精通重击），反正之前出这些神话专长的职业，只要方便常驻变形效应就可以把这些专长优先替换为变化自如。

18. 原怒者可以自由选择血脉能力是否替换狂暴特技，所以现在最多可以替换为20个狂暴特技，而不是双血脉以前一起换了，史诗级加强。

19. 从2.2.0版本DLC5开始新增N个法术，包括1环凶兆（超级好用的法术）、2环食尸鬼之触（对抗类人生物、强韧豁免失败会麻痹且造成AOE恶心）、次等操纵亡者（法师3环、牧师2环）、2环先知重负、3环复仇彗星、3环真菌感染（类似巫妖的腐化之血，需要敌人强韧豁免失败才能附加上，可以造成连环尸爆的效果）、6环排斥术（光环效果，可以双持久，敌人意志豁免失败就不能移动）、7环虚弱徽记、8环高等唤起死灵（可以召唤幽影）、9环流星爆（40尺范围基础32d6，无视法术抗力，可以甄选）、9环易伤徽记（30尺范围法抗和豁免-4，抑制全部能量抗性和10伤害减免，可以甄选）、9环内爆术等，对于施法者属于巨大增强。【新增职业变体的独有法术没有统计】

20. 巫妖道途的骷髅伙伴重做、斯坦顿build初始专长改动、新增十环死域术和白骨利矛（据说这两个法术效果都没做好），取消了骷髅法师+5智力加成和骷髅牧师+5感知加成

21. 刺客重做

22. 梦境之书可以随章节进行而解锁（未测试，根据代码来说是第二章眷泽城神话3以后不久，第五章眷泽城神话8以后分别升级一次）。

23. 身体、灵魂和心灵的不可思议的转变的魔药变为炼金加值，现在可以跟天赋书叠加了。

24. 惊世神力目前伤害加值还能运用到非武器的伤害上。现在变成独立的士气加值（跟其他的士气加值叠加），不吃DLC3的高奏凯歌之戒的双倍士气加成。【总体来说算是大幅度加强了，不吃双倍也就是相较于之前，神话9少1AB和1伤害，神话10少2AB和2伤害；但是神话4的时候多了4AB和4伤害】

25. 偏好超魔可以选择偏好顽强超魔了。

26. 自动确认重击的骰子变成21而非20，这样辉煌启言的效果不会被祝福武器等自动确认重击的能力而快速消耗了。同时也相当于官宣了：重击确认检定中骰20，不视为大成功。

27. DLC6新增一系列专长：加剧超魔和洞穿超魔、解法专攻和高等解法专攻、

28. 元素狂潮修改了描述，但是实际效果只是原来的元素狂潮（酸、火、冰、电的法术伤害可以触发），只是新增了音波可以触发且消除标记以后也会新增一个标记（标记只能存在一个），比如火-冰-电、这样会触发两次元素狂潮。

29. 酷热之风的判定时间改变为施法的回合开始，敌人在自己回合可以用移动动作起身了，连续控制的效果减弱，对施法者的控制效果几乎没有了。目前造成倒地的法术，只有酷热之风修改为这个版本。有可能后期会把油腻术和凛冬之握也修复成这种。

26. 念刃现在可以进行借机攻击了

# 汉化的更新日志备份

### 以下为2.10u正式版更新日志部分摘要

- Eye of Truth has been reworked;
- Fixed issues with damage for the following Honorable Judgment Gnome Hooked Hammer（高尚裁决）， Nature's Wrath Greatclub（自然之怒巨木棒）， Bellowing Howl Shortspear， Jharsygax pet（贾西各斯）， Club with Nails（带钉木棒）， Dark Glowing Scythe（暗蚀巨镰）， Boots of Stampede（狂奔之靴）， Vicious weapons（恶毒武器）;高尚裁决的独立附伤 - 修复
- Fixed issues with damage for the following abilities: Angelic Attacks Rage Power（天使之击）， Mythic Charge（神话冲锋）， Mythic Leading Strike（引领打击）;
- Fixed issues with damage for the following spells: Resounding Blow（轰鸣击）， Firebrand（火焰烙印）， Acid Maw（酸咬）， Geniekind（巨灵化身）， Vampiric Blade（吸血鬼之刃）， Elemental Assessor（元素评估）;
- 不恕元素护符效果不正常 - 修复
- 《咒法与召唤的二元性》不能刷出充足怒火卷轴 - 修复
- 圣兽之爪加值不正常 - 修复
- 击败萨瓦梅勒克后，兰恩或雯朵格可能会从其脊椎上打出一个独特的弓；
- Now Guardian's Shield increases the competence bonus to attacks of opportunity to +6;
- 神圣之触戒指在空间斩/接触攻击时没有提供伤害加成 - 已修复；
- 高奏凯歌之戒没有让属性的士气加值翻倍 - 修复
- 充足斩击卷轴效果变更（实测结果没图标了，效果倒是没变）
- 希望使者不朽的爱，盾击时有双倍+5增强加值 - 修复
- 酷热之风可以增效
- 战法转换的BAB加成，由施法者赐予，而非受术者。
- 混血术可以通过博学士扩表了
- Aspect of the Wolf， greater Animal Aspect， Aspect of the Falcon， Aspect of the Bear， Aspect of the Stag， Blessing of the Salamander， Frightful Aspect， Geniekind， Fiery Body， Ice Body， and Iron Body spells now benefit from Master Shapeshifter feat and got the polymorph descriptor;
- 念刃旋风修复
- 闪现术对AOE法术也生效 - 修复
- Bonuses to strength， dexterity， and constitution from the Master Shapeshifter mythic ability will be displayed separately now;
- 辉煌启言可以额外投2次而非1次 – fixed;
- 爱露莎蕾做完转化任务以后可以获得1/2神话等级的豁免加成【运气】
- 疾病免疫或者维生气泡可以完全免疫孢子
- 可控火球对盟友造成最小伤害
- 油腻术只对坐骑生效，不影响骑手了
- 可怖外表、龙型123不能同时生效；冰躯、火躯和钢躯视为变形效应，会驱散之前的变形效果。
- 行动自如免疫恍惚
- 猎人动物之力的加成错误（估计是加成不跟职业等级有关而是动物伙伴等级有关的BUG）-修复
- 步武客的各种姿态加成错误（估计是加成不跟职业等级有关而是角色等级有关的BUG） - 修复
- 勇士赐福可以被延时超魔了
- 天界模板给与无限次的辟邪斩-修复
- 圣职杀手7级将获得迅捷研究
- （高等）阴影咒法可以用延时超魔了；（高等）阴影塑能可以用极效、增效和及远超魔了
- 巨嗣杀手的研究大型生物特性正确生效了
- 不同队友的研究目标可以作用于同一个敌人了
- 花豹4级体型奖励变成+4敏（实测是+2敏和2体）而不是+4体4力-2敏了。
- 强力冲锋（奋力冲刺）的伤害计算错误 - 修复
- 寒冰之躯现在赋予目标对力竭和疲劳状态的免疫；
- 解除运用了错误的施法者等级 -修复
- 战争领域不给神眷猎人扩表 - 修复
- 如果没有诡计大师的察觉2阶，诡计大师专长将不再出现在博学士列表
- 怒涛碎击专长工作不正常 -修复
- 修复了天生武器的不正常的增强加值叠加
- ~~动物异变和动物的自带体型增长可以叠加了~~（目前还没实装）
- Alchemical Weapon ability， Alkenstar Alchemist background， and Negative Energy Mastery ability worked together incorrectly – fixed;
- 念刃旋风没有超载，且使用超魔也不增加超载 - 修复
- 火焰之躯没给徒手攻击而是爪击 - 修复
- 修复了天生武器的增强加值叠加
- 实测：轰鸣击、太阳印记、天使之击、火焰烙印变成B类。