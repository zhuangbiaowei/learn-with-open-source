# 6. 修改开源项目

经过挑选，我决定拿最近比较火爆的开源游戏2048来练手，因为这个项目的规模不大，改起来应该不难。

## 6.1 从需求出发，修改代码

众多的2048改编版，都非常类似，就是将数字的加法，变成某种等级序列的递进。比如：两个夏合在一起，变成商；两个商合在一起，变成西周。

确立了目标之后，我们需要找到在哪里修改代码，当然，前提是我们得把代码搞到本地来。

    首先访问：https://github.com/gabrielecirulli/2048 然后fork出一个自己的版本
    例如：https://github.com/zhuangbiaowei/2048
      
    然后，在自己的机器上，执行：
    git clone git@github.com:zhuangbiaowei/2048.git
  
随后，挑选自己的喜欢的编辑器，打开2048的目录，开始查找可以下手的地方。

在js目录下的game_manager.js，我们发现了一个函数，叫做：addRandomTile。在这个函数里，有一行是这么写的：`var value = Math.random() < 0.9 ? 2 : 4;` 这种搞法，真的非常粗暴，随机加入一个方块，有90%的概率是2，有10%的概率是4。

所以，我也选择了比较粗暴的搞法，在这个js的第一行，加了一句：`NameArray = ['夏','商','西周','春秋','战国','秦','汉','三国','两晋','南北朝','隋','唐','五代十国','宋','元','明','清','民国','新中国'];` 然后把刚才的那句改成：`var value = Math.random() < 0.9 ? NameArray[0] : NameArray[1];`

这是唯一的修改，我们可以在浏览器里打开index.html，看看效果。
![](images/2048-1.png)
每次出来的方块，的确是朝代名称了，但是加在一起之后，却全都变成了2。

还是在game_manager.js，我们发现了如下一段代码：

    var merged = new Tile(positions.next, tile.value * 2);
    merged.mergedFrom = [tile, next];
    
    self.grid.insertTile(merged);
    self.grid.removeTile(tile);
    
    // Converge the two tiles' positions
    tile.updatePosition(positions.next);
    
    // Update the score
    self.score += merged.value;
    
    // The mighty 2048 tile
    if (merged.value === 2048) self.won = true;
    
看来这就是我们要修改的关键所在了。`tile.value`的值现在是一个字符串，所以不能简单的乘以2，我们可以先找到它在NameArray里的位置，然后取他的下一个值。

    var pos =NameArray.indexOf(tile.value);
    var merged = new Tile(positions.next, NameArray[pos+1]);

另外，`merged.value`也不能直接加到`self.score`里去了，要改成:

    now_value=Math.pow(2,pos+2);
    self.score += now_value;
    if (now_value === 2048) self.won = true;
    
再运行一下看看，发现了一些丑陋的bug。
![](images/2048-2.png)

1. 颜色不对，不同的朝代应该有不同的颜色
2. 字体大小不对，两个字的朝代，有一个字就到下面去了

打开Firefox里的Firebug，我们可以查看到问题所在：
![](images/2048-3.png)

原版的2048，相当粗暴的直接将方块里的内容，当成css的class的内容。因为现在的方块里都变成了汉字，所以我们得将汉字换算成实际的数字。

在html_actuator.js中，我们找到了这样一句： `var classes = ["tile", "tile-" + tile.value, positionClass];`

我们可以在这一行的前面，补上两句：

    var pos =NameArray.indexOf(tile.value);
    var tile_value=Math.pow(2,pos+1);
    //再修改一下刚才的那句：
    var classes = ["tile", "tile-" + tile_value, positionClass];
    
于是，正常的颜色就会出现了。至于字体大小的问题，我们得回到main.css中去找答案。

    .tile .tile-inner {
      border-radius: 3px;
      background: #eee4da;
      text-align: center;
      font-weight: bold;
      z-index: 10;
      font-size: 55px; }

我们可以简单粗暴将`font-size: 55px;`，改成`font-size: 35px;`。我们看一下现在的效果：
![](images/2048-4.png)

OK，打完收工!
