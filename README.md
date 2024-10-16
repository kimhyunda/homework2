# homework3_2022732045_김현준
---

## 3.1  
<img width="415" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/4887de54-5ac5-4b54-9d2c-b107d430888d">  

(a)  

$$  
x_1(t) = y(t), x_2(t) = \frac{dy(t)}{dt}  
$$  

(b)  

운동의 방정식을 사용하여 이 그림의 미분방정식을 먼저 구한다  

$$
M\frac{d^2y(t)}{dt^2} + b\frac{dy(t)}{dt} + ky(t) = F(t)
$$

이 식을 각각의 상태변수에 대입하여 두 개의 식을 도출해낼 수 있다  

$$
\frac{dx_1(t)}{dt} = x_2(t)
$$

$$
\frac{dx_2(t)}{dt} = -\frac{b}{M}x_2(t) -\frac{k}{M}x_1(t) + \frac{1}{M}F(t)
$$  

(c)  
위에서 구한 식들을 행렬 형식으로 표현하면  

$$
\dot{x}(t) = \begin{bmatrix} 0 & 1\\
-\frac{k}{M} & -\frac{b}{M} \end{bmatrix}x(t) + \begin{bmatrix} 0 \\
\frac{1}{M} \end{bmatrix}F(t)
$$

$$
y(t) = \begin{bmatrix} 1 & 0\end{bmatrix}x(t)
$$

가 도출된다  

## 3.3  
<img width="260" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/bf2d1576-7228-4a06-b11d-3e7d7999a8a1">  

먼저 주어진 회로에서 KVL을 적용한 결과  

$$
L\frac{di_L(t)}{dt} - v_c(t) + v_2(t) - v_1(t) = 0
$$

이러한 식이 나오고  
두 번째로 KCL을 적용하면  

$$
C\frac{dv_c(t)}{dt} = -i_L(t) + i_R
$$  

이러한 식이 도출된다  다음으로 다른 변수인 I_R을 구해줘야한다  

$$
i_R = \frac{v_2(t)}{R} - \frac{v_1(t)}{R}
$$

$$
C\frac{dv_c(t)}{dt} = -i_L(t) + \frac{v_2(t)}{R} - \frac{v_1(t)}{R}
$$

가 된다

위의 식을 정리해 각각의 상태변수에 대해 정리한다  

$$
x(t) = \begin{bmatrix} i_L(t) \\
v_c(t)\end{bmatrix}
$$

$$
v(t) = \begin{bmatrix} v_1(t) \\
v_2(t)\end{bmatrix}
$$

따라서 행렬식으로 다시 표현해준다  

$$
\dot{x}(t)= \begin{bmatrix} 0 & 1/L \\
-1/C & -1/RC
\end{bmatrix}x(t) + \begin{bmatrix} 1/L & -1/L \\
0 & 1/RC
\end{bmatrix}v(t)
$$  

## 3.5  
<img width="309" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/53b71c9f-adc0-4c00-91e5-15dca0e96dea">  

(a)  
폐루프의 전달함수는 $G(s)/1+G(s)$ 로 정의 된다 따라서  

$$
T(s) = \frac{Y(s)}{R(s)} = \frac{G(s)}{1+G(s)} = \frac{\frac{s+2}{s^3+5s^2-24s}}{1+\frac{s+2}{s^3+5s^2-24s}} = \frac{s+2}{s^3 + 5s^2 - 23s +2}
$$

라는 식이 도출된다  

(b)  
위의 식 분자,분모에 각각 $Z(s)$를 곱해준다  

$$
\frac{Y(S)}{R(S)} = \frac{(S + 2)Z(S)}{(S^3 + 5S^2 -23S + 2)Z(S)}
$$

그 다음 역라플라스를 해준다  

$$
y(t) = \dot{z}(t) + 2z(t) , r(t) = \dddot{z}(t) + 5\ddot{z}(t) -23\dot{z}(t) +2z(t)
$$

이를 행력식인 상태미분방정식으로 표현해주면  

$$
\{x}(t) = \begin{bmatrix} x_1(t) \\
x_2(t) \\
x_3(t)\end{bmatrix} = \begin{bmatrix} z(t)\\
\dot{z}(t) \\
\ddot{z}(t) \end{bmatrix}
$$

$$
\dot{x}(t) = \begin{bmatrix} 0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5 \end{bmatrix}x(t) + \begin{bmatrix} 0 \\
0 \\
1 \end{bmatrix}r(t)
$$

$$
y(t) = \begin{bmatrix} 2 & 1 & 0\end{bmatrix}x(t)
$$

이렇게 된다  

## 3.12  

<img width="317" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/03adb89a-efef-4f3a-a181-91ad79490050">  

(a)  
전달함수 각 분자, 분모에 $Z(S)$를 곱해주고 역라플라스 변환을 해준다  

$$
\frac{Y(S)}{R(S)} = \frac{(8S + 15)Z(S)}{(S^3 + 12S^2 + 44S + 48)Z(S)}
$$  

$$
\{x}(t) = \begin{bmatrix} x_1(t) \\
x_2(t) \\
x_3(t)\end{bmatrix} = \begin{bmatrix} z(t)\\
\dot{z}(t) \\
\ddot{z}(t) \end{bmatrix}
$$

그리고 $$\dddot{z}(t)$$는 r(t)의 식을 이용해서 구한다  

$$
r(t)= \dddot{z}(t) + 12\ddot{z}(t) + 44\dot{z}(t)+48z(t)
$$

이를 $$\dddot{z}(t)$$에 대해 정리해준다

$$
r(t) - 12\ddot{z}(t) - 44\dot{z}(t) - 48z(t)= \dddot{z}(t)
$$

위의 식을 바탕으로 상태미분 방정식을 행렬식으로 표현한다  

$$
\dot{x} = \begin{bmatrix} 0 & 1 & 0 \\
0 & 0 & 1\\
-48 & -44 & -12 \end{bmatrix}x + \begin{bmatrix} 0 \\
0 \\
1 \end{bmatrix}r
$$

$$
y = \begin{bmatrix} 40 & 8 & 0\end{bmatrix}x
$$

(b)  
상태천이행렬을 구하기 위해  $\Phi(S) = [sI-A]^-$이 식을 통해 라플라스를 구하고 역라플라스를 통해 상태천이행렬을 구한다  
계산이 너무 복잡하기 때문에 이는 Matlab으로 진행한다  


```matlab
A=[0,1,0;0,0,1;-48,-44,-12];
>> syms s
>> Phi_s=inv(s*eye(3)-A);
>> ilaplace(Phi_s)
```

결과  
<img width="837" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/892b9064-bb92-4856-be3d-6c9bd9ac07e2">  

## 3.17  
<img width="271" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/8159185e-0a68-4413-ab0d-cd6756b71693">  

위의 식은 Matlab을 이용하여 풀 수 있다  

```matlab
syms s
A = [1, 1, -1; 4, 3, 0; -2, 1, 10];
B = [0; 0; 4];
C = [1, 0, 0];
D = 0;
Phi = inv(s*eye(3) - A);
G = C*Phi*B+D;
[n,d] = numden(G)
```

결과  

<img width="194" alt="image" src="https://github.com/ces0o/matlab/assets/127365253/69fedb05-02a2-41a3-83aa-184c261851c8">















