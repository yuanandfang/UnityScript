# UNITY

  * 常用脚本事件：
 
     * Update：每帧调用一次，用于正常更新，多长时间更新一次由系统决定。可以用Time.deltaTime方法来获取两帧相隔时间

     * Start：启动脚本。在第一次Update执行前调用，只在脚本实例被启用时才会执行，总是在Awake函数之后执行，且在脚本的生命周期只执行一次。

     * Awake：唤醒脚本。在所有的游戏对象被初始化完毕之后才会被调用，在脚本的生命周期只执行一次

     * FixedUpdate：固定频率更新

     * LateUpdate：在Update之后 ，每帧更新一次
     * OnGUI：用于绘制用户交互界面，在一帧中会调用多次
     * OnDestroy:当前脚本销毁时调用
 
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

### 通过名称来查找
  * 1.通过名称来查找：
    * 使用函数GameObject.Find，如果场景中存在指定名称的对象，则返回该对象的引用，否则返回null，如果存在多个同名的对象，则返回第一个对象的引用。
GameObject cube = GameObject.Find("MyCube");
 * 2.通过标签来查找：
    * GameObject.FindWithTag，如果场景中存在指定标签的对象，则返回该对象的引用，否则返回null，如果多个对象使用同一个标签，则返回第一个对象的引用。
    
注意：与GetComponent一样，GameObject.Find和GameObject.FindWithTag也是比较耗时的参数，因此不建议在update函数中调用它们，而是在初始化中查找一次后保存在变量中。
上述函数比较耗时。

## 协程
当我们调用一个方法想要让一个物体缓慢消失时，除了在Update中执行相关操作外，Unity还提供了更加便利的方法，这便是协程。 

1.返回值必须是IEnumeraror

2.yield语句就像红绿灯，碰到他就停下等待 当中断结束指令后，才恢复

3.启动协程分别是：

* 1 StartCoroutine(/这里直接调用方法，添加参数/)
    *   优势在于可以调用多个参数的方法
* 2 StartCoroutine(/这里填写”字符串的方法名字”，方法参数/)
    *  只能调用不含参数或只包含一个参数的协程方法。
  
但是第一种方法不能通过StopCoroutine(/这里填写”字符串的方法名”/)来结束协程，只能通过StopAllCoroutines来结束。后一种则可以通过StopCoroutine来结束对正在执行的协程的调用。
