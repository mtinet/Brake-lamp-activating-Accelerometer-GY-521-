
 
***
     아두이노 나노, GY-521(가속도 센서), Common Anode RGB LED를 사용한 가속도 센서 반응형 브레이크등입니다. 
***

1. 자전거와 자동차, 오토바이 등에 활용이 가능할 것 같구요. 차량의 종류에 따라서 감도 조정을 하면 됩니다. 자동차의 실내에서 가속도나 감속도를 파악하는 용도로 사용해도 될 것 같군요. 

2. 감도 조정은 882~960 사이의 if문의 state 조건에서 하시면 되구요. 

3. 현재 세팅은 gy-521의 x축을 기준으로 중력가속도를 16이라 했을 때, 다음과 같이 세팅되어 있습니다. 

 - 15보다 크면 급감속(빨간LED 3개 빠르게 깜빡임)
 - 10보다 크면 중감속(빨간LED 2개 느리게 깜빡임)
 - 5보다 크면 저감속(빨간LED 1개 켜짐)
 - -3보다 크면 등속(녹색LED 1개 켜짐)
 - -7보다 크면 가속(녹색LED 2개 느리게 깜빡임)
 - -7보다 작으면 급가속(녹색LED 3개 빠르게 깜빡임)

4. 테스트
~~~
[![테스트 영상 링크](https://i.ytimg.com/vi_webp/LDO5WssF9eo/mqdefault.webp )](https://www.youtube.com/watch?v=LDO5WssF9eo)
~~~

5. 핀배치는 다음과 같습니다. 
~~~
- 아두이노 나노와 가속도 센서 연결
~~~   
| 아두이노 나노  | GY-521 |
| :------------: | :-----------: |
| vcc           |   vcc       |
| gnd           |   gnd       |
| sda           |   A4        |
| scl           |   A5        |

~~~
- 아두이노 나노와 가속도 센서 연결    
~~~
| 아두이노 나노  | GY-521 |
| :------------: | :-----------: |
| 3           |   red 1       |
|  2          |   5V       |
|   5         |   green 1        |
|    6        |   red 2        |
|   9         |   green 2        |
|    10        |   red 3        |
|    11        |   green 3        |
  
 - 아두이노 나노에 5V핀이 하나뿐이어서 2번 핀을 항상 5V가 출력되도록 설정했습니다. 
