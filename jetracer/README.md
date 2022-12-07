## JetRacer Basic Motion

`notebook/basic_motion.ipynb` 코드를 통해 web browser로 JetRacer 조작을 익힌다. 

1. `http://<jetson_ip_address>:8888` 를 browser address bar에 입력해 jetracer에 원격 접속한다.

`<jetson_ip_address>` 는 jetson nano의 piOLED 에서 확인할 수 있다.

2. Sign in with the default password `jetracer`
3. Browse to the folder `~/jetracer/notebooks` in the Jupyter Lab file browser
4. Run through the notebook `basic_motion.ipynb`

### [Basic_motion.ipynb]

* This section mainly learns how to control the movement of the car. The car is divided into two parts to control, one part is steering steering to control the car turning, and the other part is the throttle to control the speed of the rear wheels.


### car.steering (방향 조절)

<img src="https://user-images.githubusercontent.com/108324590/206144894-e8e1cc9f-8ab2-4fcf-b5b7-e2a1573af7ac.jpg" width="60%" height="60%">

* When running the statement car.steering = 0, the car steering will turn. __0 means forward, 1 means the wheel goes to the far left, -1 means the wheel goes to the far right.__ Change the wheel to different directions to different values, the value range is [-1,1]

* After running this program, the steering gain car.steering_gain and the steering initial displacement car.steering_offset will be output.

* The steering gain __car.steering_gain can represent the maximum angle the wheel can turn.__

* The initial steering displacement __car.steering_offset can represent the initial offset of the wheels.__ When car.steering = 0, when the car does not run in a straight line, you can adjust the length of the steering rod or modify the value of the initial steering displacement to make the car go straight.


### car.throttle (속도 조절)

<img src="https://user-images.githubusercontent.com/108324590/206145667-7c0420c9-75ce-4a92-9743-c0cdd474aec2.jpg" width="60%" height="60%">

* car.throttle is the throttle size, the range is [-1,1], __0 means stop, 1 means forward at maximum speed, -1 means backward at maximum speed.__ 

* car.throttle_gain is __the throttle gain__, which can __indicate the maximum speed at which the car can move.__ When car.throttle_gain = 1 and car.throttle = 1, the car can run to the maximum speed.

* The steering gain __car.steering_gain controls the maximum rotation range of the wheel,__ and the initial steering displacement car.steering_offset can compensate for the steering error caused by mechanical assembly.

* The throttle gain car.throttle_gain controls the maximum speed range of the rear wheels.


