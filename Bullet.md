# Bullet.cs
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Bullet : MonoBehaviour
{
    public float speed = 100;
    private Rigidbody rb;//获取子弹刚体



    // Use this for initialization
    void Start()
    {
        rb = GetComponent<Rigidbody>();//获得刚体
    }

    // Update is called once per frame
    void Update()
    {
        //子弹飞行
        rb.velocity = transform.forward * Time.deltaTime * speed;
    }

    //子弹碰撞
    void OnCollisionEnter(Collision collision)
    {
        GameObject hit = collision.gameObject;//获取碰撞对象的游戏对象赋给hit
        Hp hp = hit.GetComponent<Hp>();//定义hit的血量对象
        if (hp != null)
        {
            hp.Die(30);//如何hp不为0，调用hp的die方法，传入30的常量
        }
        Destroy(gameObject);//毁灭子弹对象
    }
}

```
