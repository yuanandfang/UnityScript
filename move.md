# 如何让物体匀速运动

## Time.deltaTime：是一个时间增量，我想应该是这一帧的时间。像flash中的一秒30帧，每帧多少秒之类的。



在脚本中输入
```
Vector3 fwd = transform.TransformDirection(Vector3.forward);

if (Physics.Raycast(transform.position, fwd,out hit,1))

Debug.DrawLine(transform.position,hit.point,Color.red);


```
Physics.Raycast(transform.position, fwd,out hit,1)为发射射线函数，transform.position为射线原点，fwd为发射方向，1为距离。

如果前方有碰撞体，则发射射线。


