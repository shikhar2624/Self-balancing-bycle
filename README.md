# Self-balancing-bycle
Self balancing cycle is balance using a fly wheel. The direction of flywheel rotation produces the the required torque to balance out the tilting mass of the bycycle. The bike comes with an IMU, so we can use it to extract the position quaternion, which can be converted to Euler angles using the tf library. Then, we simply need to use PID to control the angular velocity of the flywheel. Two PID controllers are used. The first PID controller is to setup to drive angular velocity to zero, with the same mechanic that you have now - PID output drives speed by ω=ω+P+I+D. In tuning it you'll probably notice that you have a scenario where your bike starts to lay down and the flywheel slows that rate by continually accelerating, up to some infinite speed.
###
![Screenshot from 2022-05-23 00-22-20](https://user-images.githubusercontent.com/77221967/169711479-28eeb721-40df-436c-a3ea-c310326d27f9.png)
```
ω(k)=ω(k−1) + (PID)rate + (PID)position
```
