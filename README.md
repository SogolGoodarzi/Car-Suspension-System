# Car-Suspension-System
<p align="justify"> In a car, the wheel is connected to the car body through the suspension system. The suspension system is designed to reduce cabin vibrations when crossing bumps. The suspension system consists of a spring and a damper, both of which are compressed when passing the bump, and as a result, the sudden movement of the wheel is not transferred directly to the car cabin. The spring produces a force to keep the height of the car cabin at a desired distance above the road surface, and the damper creates frictional damping. The focus of this exercise is on the importance of having a suspension system. You can see the block diagram of the system in the following figure:</p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/e3ab4acb-c4ce-491c-ae18-4ba23488f034)

<p align="justify"> In this model, M shows the mass of the car that is transferred to the wheels through the suspension system. The vertical displacement of the wheel from the balance point is considered as the input $x(t)$ and the vertical displacement of the mass M from the balance point is also considered as the output $x(t)$. In fact, $y(t)$ is the oscillation of the car cabin. Using dynamic laws, it can be shown that the relationship between $x(t)$ and $y(t)$ is as follows: </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/e8439e5c-39eb-414b-865c-2abb2ad2e210)

### Part a.
Assuming, 𝑀=𝐾=1, we rewrite the above relationship in the form of a differential equation.

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/85d4a095-f00a-4313-9c74-49b856623f6c)

### Part b.
By taking the Laplace transform from the above relation, we find the transformation function.

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/22de327c-7a18-497b-9db4-944c3886a726)

To draw the block diagram, we have the following relationship:

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/b53a47cd-ca70-4446-bbea-4e97a25b7ccf)

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/dfd79b9b-17ac-46f9-a634-0214c47d7965)

The implementation of this block diagram in Simulink is as follows:

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/217bfec1-4595-4bfc-b967-adffa0e38ed9)

Of course, we have to put a value instead of the B parameter so that the simulation takes place.

### Part c.
<p align="justify"> We obtained and plotted the impulse response of the system for (𝐵 = 0 in the absence of suspension system). In order to find the impulse response, we put delta in the input and take the Laplace transform. </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/03d44d00-7d9c-4a48-b1c6-e7ed83fe1dbe)

According to the following point, we can obtain the output signal by inverting Laplace. 

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/c7d7b99c-9b5a-40b8-b32f-5bf94ef4cd8b)

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/1be9f9e8-ae45-48bc-851e-9d04cb11174c)

<p align="justify"> As it is known, for the pulse input, the output signal is sinusoidal. This phenomenon can be analyzed and felt in reality. As mentioned, the impact input is equivalent to the car going over the bump, which is observed when the car goes over the bump, after that we feel the oscillating movements in the car cabin. You can see the simulations done in MATLAB: </p>
 
![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/cdb11da8-25ac-4f39-a483-20ec7d3c621f)

The output is as follows, which is a sinusoidal signal as we expected from the manual analysis.

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/fdee2577-d22c-443c-8fd4-e910b22ebbe5)

### Part d.
<p align="justify"> Find the smallest value of 𝐵 (𝐵 > 0) that makes the poles of the transformation function real. So, the poles of the transformation function are obtained as follows: </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/658347f9-1775-4ef8-803f-52cff3eca39d)

<p align="justify"> For the above two poles to be true, the delta value must be positive or zero. So, according to the form of the problem, we find that the smallest value for B is when delta is zero. </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/8f59ee9b-b138-41c7-bb0d-0292320102c7)

Since it has been said that 𝐵 > 0, as a result, the smallest value for B is 2. In this case, the output signal is as follows:

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/05168995-14a1-4c1f-89c0-e63b977d7d40)

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/0a859e77-55f0-4866-9f2a-7907e911658f)

<p align="justify"> The impact response in this case was raised. Here, the oscillations of the car are such that after a period of time these oscillations are lost and damped. So, when the car passes over the bump, the cabin does not feel the swinging movements that take a long time, and it reaches a steady state after about 5 seconds. 
We also simulate this analysis in the MATLAB environment.  </p>
  
![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/ca2491b8-2b04-412b-bbdd-0fb91ae06719)

The output signal is as follows:

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/a76591a6-2732-43d4-9235-fb2c65393c87)

<p align="justify"> The output in this case was the same as the output we obtained in the manual solution. In the manual solution, we also have an exponential signal that tends to a finite value in infinite time, which is also clear in the output form. </p>

### Part e.
<p align="justify"> Now we want to examine the case where 𝐵 is very large. Obtain the impulse response of the system for 𝐵 = 100 and plot it. In this case, let's assume that the denominator of the transfer function is roughly decomposed as (𝑠 + 100) (𝑠 + 0.01). </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/6f00b98c-e5cb-44c3-8642-b38be8018d4b)

<p align="justify"> In this case, the output signal is an exponential signal, the time constant of this signal is very high. If we plot the shape of this signal with Simulink in the next section, it can be seen that it closes to zero very quickly and has more damping than the previous two cases. In terms of physical interpretation, it can also be said that when we increase the damping coefficient, which is B, it can be said that the amount of damping of the suspension system increases, as a result, when the car passes through a collision, then only during passing from the bump, the cabin will slip and very quickly after that, no movement will be observed in the cabin. Now we get the output in MATLAB:</p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/1000b9a8-5bb7-4a0b-bf3f-94b3d584c5dc)

<p align="justify"> The output is as we'd expect, a highly damped view. If we increase the time to draw the graph, it can be seen that we will have an impact function, which means that in this case, for high Bs, the output signal will be close to an impact at the moment of crossing the bump. </p>

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/a3d592b0-58df-499e-96d9-bc7d6bddbdbd)

![image](https://github.com/SogolGoodarzi/Car-Suspension-System/assets/125180530/41166a82-70dd-4e3a-900e-a5b7ae94ac7b)

### Part f.
<p align="justify"> In part(c) where B=0, it means that the coefficient of the suspension system was very low and there was practically no suspension, and it was observed that physically, when the car passes through a bump, it will undergo sinusoidal oscillations and the attenuation of the output signal in this mode is low and zero, so this suspension system is not suitable. </p>

<p align="justify"> In part(d), the suspension coefficient was equal to 2, and in this case, it was observed that the output has damping, but it damps slowly, and it may take some time for the car cabin to completely achieve a stable and non-slip condition. (This duration is approximately 5 seconds.) But if you pay close attention, the amplitude of the cabin oscillation is low and is around 0.1, so you will not feel much slip at the moment of passing. </p>

<p align="justify"> In part(f) where we increased the suspension coefficient, it was observed that in this case the damping of the output signal is much faster than the previous state and immediately after the car passes over the bump, the car cabin returns to its original state and no longer swings or slides. It will not be felt. But if you pay attention, the amplitude of oscillation in this mode is very high, so a lot of shock or slip will be felt in a short period of time. </p>

#### Conclusion:
<p align="justify"> In general and by comparing the above three modes, it can be seen that the higher the coefficient of the suspension system is, the sooner the system is damped to a stable state, but the amount of impact on the cabin may increase. So the best situation is in part(d) where B=2. </p>
