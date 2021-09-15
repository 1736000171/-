# -
基于C++实现的猜拳小游戏

## 1、	将电脑构造成类
电脑有3个public类型的函数(void SetCompetitor(int who); string HitOut(); string GetComputerName(); )，2个私有变量（string mComputerName、string mComputerMethod），以及1个static变量static int stWinTimes。
void SetCompetitor(int who) 功能：用来选择电脑（曹操、刘备或孙权）（who为对应的1、2、3。）
string HitOut() 功能：每个不同的电脑，用来出拳的策略也是不一样的，此函数可用随机数选择不同的出拳方法。注意，对每个不同的电脑，其方法不一样。
string GetComputerName() 功能：获取电脑名称。
mComputerName：电脑名称。
mComputerMethod：电脑出拳方法。
## 2、	将玩家构造成类
玩家类包含3个函数（void SetPlayerName(const string & pName); string GetPlayerName(); string HitOut(int num);），2个私有变量（string mPlayerName、string mPlayerMethod;），以及1个static变量static int stWinTimes。
void SetPlayerName(const string & pName) 功能：设置玩家姓名。
string GetPlayerName() 功能：获取玩家姓名。
string HitOut(int num) 功能：玩家出拳法则。
string mPlayerName：玩家姓名。
string mPlayerMethod：玩家出拳方法。
## 3、	构造游戏算法类
游戏算法类包含4个私有类型的函数（void BeginningShow();void GameStart();void GameProceed();void GameEnd();）和一个公有类型的函数（void AlgorithmProceed();），以及2个私有类型的指针变量（Computer *mpComputer; Player *mpPlayer;）。
void BeginningShow() 功能：游戏初始界面显示。
void GameStart() 功能：游戏开始工作，里面要求输入玩家姓名、选择电脑对手等操作。
void GameProceed() 功能：游戏进行中的代码编写，玩家输入某个数字（1，2，3中的一个），然后计算电脑和玩家划拳谁赢了，并显示出来。
void GameEnd() 功能：游戏结束，统计玩家和电脑赢的次数，比较大小，得出玩家的输赢状态，并且要通过某个小界面显示出来。
void AlgorithmProceed() 功能：游戏算法进行运行。这个是此类外部唯一接口函数。Main函数只需要调用这一个函数就可以实现整个游戏功能。
Computer *mpComputer：Computer电脑类的指针，需要在游戏算法类的构造函数中单独去new一段内存空间，并且在游戏算法类的析构函数中去释放掉这段空间。
Player *mpPlayer：Player玩家类的指针，需要在游戏算法类的构造函数中单独去new一段内存空间，并且在游戏算法类的析构函数中去释放掉这段空间。
