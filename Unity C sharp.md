＃＃ C＃
所有类继承于MonoBehaviour

  * 常用脚本事件：
 
     * Update：每帧调用一次，用于正常更新，多长时间更新一次由系统决定。

     * Start：启动脚本。在第一次Update执行前调用，只在脚本实例被启用时才会执行，总是在Awake函数之后执行，且在脚本的生命周期只执行一次。

     * Awake：唤醒脚本。在所有的游戏对象被初始化完毕之后才会被调用，在脚本的生命周期只执行一次

     * FixedUpdate：固定频率更新

     * LateUpdate：每帧调用一次，在Update之后
     * 
 
 * MonoBehaviour类

      * uniyt中非常重要的类，定义了基本的脚本行为，所有脚本类均需要从它直接或间接继承。
      * OnMouseEnter：鼠标移入GUI控件或碰撞体时调用
      * OnMouseOver：鼠标停留
      * OnMouseExit：鼠标移除
      * OnMouseDown：鼠标按下
      * OnMouseUp：鼠标释放
      * OnTriggerEnter：当其他碰撞体进入触发器时调用
      * OnTriggerExit：离开
      * OnTriggerStay：停留
      * OnCollisionEnter：当碰撞体或者刚体与其他碰撞体或者刚体接触时调用
      * OnCollisionExit：离开时
      * OnCollisionStay：保持接触时
      * OnControllerColliderHit：当控制器移动时与碰撞体发生碰撞时调用
      * OnBecameVisible：对于任意一个相机可见时调用
      * OnBecameInvisible：对于任意一个相机不可见时调用
      * OnEnable：对象启用或者激活时调用
      * OnDisable：对象禁用或者取消激活时调用
      * OnDestory：脚本销毁时调用
      * OnGUI：渲染GUI和处理GUI消息时调用
