**2014-01-15更新：** 加入Gwill的文章连接。
<hr>

cocos2dx script binding: lua or javascript?

这篇文章是我在之乎的一个回答： <http://www.zhihu.com/question/21130385/answer/18827858> ，有修改。

**强调：这篇文章有极强的时效性，在1年时间内应该有一定指导意义。本文成文日期是2013年9月11日。**

目前 Javascript 风头似乎超越一切，所以我一直在纠结，到底是使用Lua Binding还是 Javascript Binding。

我找了一些资料。如果把下面的资料看完，相信每个人心里都会自有分辨。<!--more-->

* [Why I switched from Lua to Javascript][u1]
* [Lua is simple and fast][u2]
* [Lua vs. Javascript][u3]
* [A discussion on JIT compilers by Brendan Eich][u4]
* [Learning Lua Form JS][u5]
* [Why Lua?][u6]
* [Cocos2dx+lua合适还是Cocos2dx+js合适][u7]
* [Lua 语言有哪些不足？][u8]
* [LUA程序设计(第2版)豆瓣书评中云风的评论][u9]
* [subtle differences between javascript and Lua][u10]
* [乐元素CTO凌聪-基于cocos2d-x二次开发的自有引擎方案分享][u11]
* [Cocos2d-x 2013春季新功能发布和发展规划][u12]
* [Architecture and Directory Structure][u13]
* [cocos2d-x changelog][u14]
* [cocos2d-x官方论坛，请比较lua binding和js binding帖数][u15]
* [cocos2d JavaScript tests and games][u16]

下面说说我的分析，不一定正确。

再说一遍， **把上面的资料全部认真看完，你一定会有一个对你来说正确的选择。**

就我的感觉，虽然王哲说 [Javascript Binding 和 Lua Binding 会并重发展][u12]，但我认为对于cocos2d-x团队来说，应该是偏向于Javascript。从现在cocos2d-html5的频繁更新就能看出来了。不过cocos2d-x是开源的引擎，即使官方团队不重视（或者相比JS而言不够重视），也依然有[优秀的实现][s1] 。

Javascript 和 Lua 语言本身的优势（性能、语法、特性、 学习曲线、熟练程度），上面已经说了很多，我提供的资料中也有许多深入的讨论。我个人认为这两种语言性能上的差异并不是我选择的主要原因，学习曲线也不是。我没用过Lua，JS能写点东西。但我并不在意学习Lua **“浪费”** 的那两天时间。

从 [cocos2d-x官方论坛][u15] 比较，Lua Binding 和 Javascript Binding帖数差别不大，JS略多，毕竟现在JS在流行程度上更强一些。

比较最近的 [cocos2d-x changelog][u14]，会发现JS的相关修改更多一些。而且比较有趣的是，JS的修改有许多是Bug fix，而Lua的修改就只是feature。这是不是从侧面说明了，Lua Binding目前更加稳定呢？ **稳定是多重要的特性啊！**

Javascript Binding最大的优势，我认为就是游戏可以直接通过cocos2d-x html5移植到网页。但我看过 [cocos2d JavaScript tests and games][u16] 之后，真的感觉到是无法接受那种性能。即使抛开 **手游是否需要开发一个网页版本** 这种运营问题不谈，运营的同学也一定不希望开放一个这样的HTML5玩家吐槽专版。

我的选择，已经很明确了，就是Lua。各位提到的IDE问题、调试问题等等，我只能再想办法去解决。我相信即使我选了JS，碰到的此类问题也不会比Lua更少。上面提到的资料中有人讲到了cocos2d-x lua的IDE和调试，应该是个正确的思路。

这个游戏完成之后，Javascript Binding应该成熟了（以现在的速度，应该会很快），到下一款游戏考虑也不迟。

**强调：这篇文章有极强的时效性，在1年时间内应该有一定指导意义。本文成文日期是2013年9月11日。**

发现 G\_will 也写了一篇类似的文章： [Cocos2d-x 绑定脚本究竟选择 Lua 还是 JS ？][s2]

[u1]: http://www.reddit.com/r/javascript/comments/ft7zn/why_i_switched_from_lua_to_javascript/
[u2]: http://wiki.interfaceware.com/241.html
[u3]: http://wiki.interfaceware.com/242.html
[u4]: http://lambda-the-ultimate.org/node/3851#comment-57671
[u5]: http://phrogz.net/lua/LearningLua_FromJS.html
[u6]: http://www.altdevblogaday.com/2013/02/19/why-lua/
[u7]: http://www.zhihu.com/question/21130385
[u8]: http://www.zhihu.com/question/20534004
[u9]: http://book.douban.com/review/1076302/
[u10]: http://stackoverflow.com/questions/1022560/subtle-differences-between-javascript-and-lua
[u11]: http://www.91shouce.com/4788.html
[u12]: http://mobile.163.com/13/0413/11/8SBAE6PT0011671M.html
[u13]: http://www.cocos2d-x.org/projects/cocos2d-x/wiki/Architecture_and_Directory_Structure#3-Javascript-Binding
[u14]: https://github.com/cocos2d/cocos2d-x/blob/cocos2d-x-3.0alpha0-pre/CHANGELOG
[u15]: http://www.cocos2d-x.org/projects/cocos2d-x/boards
[u16]: https://github.com/cocos2d/cocos2d-js-tests

[s1]: http://cn.quick-x.com/
[s2]: http://ieqi.net/2013/12/02/cocos2d-x-%E7%BB%91%E5%AE%9A%E8%84%9A%E6%9C%AC%E7%A9%B6%E7%AB%9F%E9%80%89%E6%8B%A9-lua-%E8%BF%98%E6%98%AF-js-%EF%BC%9F/
