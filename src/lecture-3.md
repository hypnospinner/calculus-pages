### Дифференцируемость функций

> Для того чтобы выкладки не были слишком большие будем писать все для 3-мерного случая. Для n-мерного аналогично

---

**Частное приращение функции**

$$
    f(x,y,z) \\
    (x,y,z) - \text{ внутренняя точка } D \subset \R^3 \\
    \text{} \\
    \Delta x - \text{приращение $x$ не выводящее за $D$ при фиксированных $z,y$} \\
    \Delta_xf = f(x + \Delta x, y,z) - \text{частное приращение функции по переменной $x$}
$$

---

> Аналогично вводится для остальных осей координат (при частном приращении мы как бы двигаемся вдоль только одной оси координат)

---

**Частный придел функции**

$$
    \text{Если } \exist \ \lim_{\Delta x \to 0} \frac{\Delta_x f}{\Delta x} = \frac{\delta f}{\delta x} = f_x'
$$

---

*Пример*:

$$
    f(x,y,z) = xe^{x^2y + z} \Rightarrow 
    \begin{array}{l}
        f_x' = e^{x^2y + z} + xe^{x^2y + z}2xy \\
        f_y' = xe^{x^2y + z} x^2 \\
        f_z' = xe^{x^2y + z}
    \end{array}
$$

Положим теперь, что нам одновременно задано приращение всех координат, т.е. мы будем двигать не вдоль некоторой оси, а в пространстве в целом сразу по всем или нескольким осям. Как от этого изменится функция?

---

**Полное приращение функции**

$$
    \Delta f = f(x + \Delta x, y + \Delta y,z + \Delta z)  - f(x,y,z)
$$

---

**Дифференцируемая функция**

$$
    \text{Функция называется дифференцируемой в точке, если $(x,y,z)$ если } \\
    \Delta f = A\Delta x + B\Delta y + C\Delta z + o(\rho) \\
    \text{Где }\rho = \sqrt{\Delta x^2 + \Delta y^2 + \Delta z^2}
$$

> Константы $A,B,C$ зависят от выбора точки, но не от приращения функции

---

Как проверить дифференцируема функция или нет? Расммотрим необходимые и достаточные условия дифференцируемости

---

**Теорема: Необходимое условие дифференцируемости** 

$$
    f(x,y,z) - \text{дифференцируема в } (x,y,z) \Rightarrow \exists f_x', f_y', f_z'
$$

*Доказательство*:
1. Пусть $f$ - дифференцируема, что по определению значит:
   $$
    \Delta f = A\Delta x + B\Delta y + C\Delta z + o(\rho) \\
   $$
2. Так как мы можем брать произвольные приращения, давайте рассмотрим случай, когда $\Delta f$ будет равно частным приращениям ($\Delta x = 0, \Delta y = 0, \Delta z \neq 0, ...$), тогда:
   $$
    \Delta f = \Delta_x f  = A\Delta x + o(\rho) \\
    \frac{\Delta_x f}{\Delta x} = A + \frac{o(\rho)}{\Delta x}, \Delta x \to 0\Rightarrow \exists \ f_x' 
   $$

Аналогично для остальных частных производных

$$
    \blacksquare
$$

---

> При этом мы видим, что $A = f_x', ...$, а формулу из определения дифференцируемой фнукции можно переписать как:

$$
    \Delta f = f_x'\Delta x + f_y'\Delta y + f_z'\Delta z + o(\rho) \\
$$

> Существование частных производных - только **необходимое** условие дифференцируемости

---

**Теорема: Достаточное условие дифференцируемости**

$$
        \exists\  \text{непрерывные} f_x', f_y', f_z' \Rightarrow f(x,y,z) - \text{дифференцируема в } (x,y,z)
$$

*Доказательство*

1. Даны непрерывные частные производные и распишем полное приращение фукнции:

$$
    \Delta f = f(x + \Delta x, y + \Delta y,z + \Delta z) - f(x,y,z)= \\
    = \left[f(x + \Delta x, y + \Delta y,z + \Delta z) - f(x , y + \Delta y,z + \Delta z)\right]\frac{\Delta x}{\Delta x} + \\
    + \left[f(x , y + \Delta y,z + \Delta z) - f(x , y,z + \Delta z)\right]\frac{\Delta y}{\Delta y} + \left[ f(x , y,z + \Delta z) - f(x , y,z)\right]\frac{\Delta z}{\Delta z}
$$

2. По Теорема Лагранжа найдутся такие приращения $\Theta_1, \Theta_2, \Theta_3 \in (0,1)$ такие что:

$$
    \frac{\delta f}{\delta x}(x + \Theta_1\Delta x, y + \Theta_2\Delta y, z + \Theta_3\Delta z) \Delta x + \\
    + \frac{\delta f}{\delta y}(x, y + \Theta_2\Delta y, z + \Theta_3\Delta z)\Delta y + \\
    + \frac{\delta f}{\delta z}(x,y,z + \Theta_3\Delta z)\Delta z
$$

3. Тогда все это можно представить как:

$$
    (\frac{\delta f}{\delta x}(x,y,z) + \alpha)\Delta x + (\frac{\delta f}{\delta x}(x,y,z) + \beta)\Delta y + (\frac{\delta f}{\delta x}(x,y,z) + \gamma)\Delta z \Rightarrow \\
    \text{из} \frac{\delta f}{\delta x}, \frac{\delta f}{\delta y}, \frac{\delta f}{\delta z} \Rightarrow \alpha, \beta, \gamma \to 0 \text{ при } \Delta x, \Delta y, \Delta z \to 0 \\ \text{} \\

    \frac{\delta f}{\delta x}\Delta x + \frac{\delta f}{\delta y}\Delta y + \frac{\delta f}{\delta z}\Delta z + (\alpha\Delta x + \beta\Delta y + \gamma\Delta z)
$$

1. Последняя часть имеет меньший порядок малости, что и доказывает теорему

$$
\blacksquare
$$

---

> Непрерывность частных производных явялется лишь **достаточным** условием дифференцируемости, но не явялется необходимым. **Критерия дифференцируемости в многомерном случае не сущствует**

---
**Теорема**

Если функция в точке явялется дифференцируемой, то в это же точке она явялется непрерывной

*Докзаательство*:
1. Воспользуемся определением дифференцируемой функции

$$
    \Delta f = f_x'\Delta x + f_y'\Delta y + f_z'\Delta z + o(\rho) \Rightarrow \lim_{\Delta x,y,z \to 0} \Delta f = 0 \Rightarrow f - \text{непрерывна}

$$

$$
\blacksquare
$$

---

**Первый Дифференциал**

Линейная часть прирощения функции

$$
    df = f_x'\Delta x + f_y'\Delta y + f_z'\Delta z
$$

---

Переобозначим

$$
    \Delta x = dx \\
    \Delta y = dy \\
    \Delta z = dz

$$

**Свойства дифференциала**

$$
    d(f \pm g) = df \pm dg \\
    d(fg) = gdf + f dg \\
    d(\frac{f}{g}) = \frac{gdf - fdg}{g^2}
$$

### Производные и дифференциалы сложной функции

Для определенности будем рассматривать функцию трех меременных. На n переменных все распространяется аналогично.

Пусть $f(x,y,z)$ - дифференцируемая, а так же дифференцируемые функции 

$$
    \begin{cases}
        x = \varphi(u,v) \\
        y = \psi (u,v) \\
        z = \varkappa (u,v)
    \end{cases}
$$

$$
    F(u,v) = f(x(u,v), y(u,v), z(u,v)) \\

    \frac{\delta F}{\delta u} - ?
    \frac{\delta F}{\delta v} - ?
$$

Очевидно, что приращению $\Delta u$ будет соответствовать некоторое приращение $\Delta x, \Delta y, \Delta z$:

$$
    \begin{cases}
        \Delta x = \varphi(u + \Delta  u, v) - \varphi(u,v) \\
        \Delta y = \psi(u + \Delta  u, v) - \psi(u,v)\\
        \Delta z = \varkappa(u + \Delta  u, v) - \varkappa(u,v)
    \end{cases}
$$

Тогда

$$
    \frac{\delta F}{\delta u} = \lim_{\Delta u \to 0}\frac{\Delta_u F}{\Delta u} = \lim_{\Delta u \to 0}\frac{\Delta f}{\Delta u}
$$