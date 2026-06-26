# Батч 51–53: Симметричные и кососимметричные тензоры, симметризация, внешнее произведение

## Список билетов

**Билет 51.** Симметрические и кососимметрические тензоры типа $(p,0)$ и $(0,q)$. Определение в терминах полилинейных функций и в терминах координат. Тривиальность коэффициентов с совпадающими индексами для кососимметричных тензоров, примеры для типа $(0,2)$.

**Билет 52.** Операции симметризации и альтернирования в терминах координатного представления, свойство быть проектором.

**Билет 53.** Внешнее произведение кососимметричных тензоров, свойства. Структура градуированно-коммутативной ассоциативной алгебры на внешней алгебре векторного пространства. Базис пространства кососимметричных тензоров типа $(0,q)$. Выражение определителя замены как внешней степени системы векторов.

---

## Карта батча

**Общий контекст:** тензоры типа $(0,q)$ (ковариантные). Симметрические/кососимметричные — особые подпространства.

**Самые важные:** 53 (внешнее произведение — основа топологии, геометрии), 52 (симметризация — проектор), 51 (базовые определения).

**Связи:** 51 → 52 → 53 строго по порядку. 53 → 58–60 (разложимые тензоры, Плюккер).

---

## Билет 51. Симметрические и кососимметричные тензоры

### 1. Смысл билета

Симметрические тензоры не меняются при перестановке аргументов; кососимметричные меняют знак. Это позволяет сократить число независимых компонент. Кососимметричные тензоры типа $(0,q)$ — это дифференциальные $q$-формы в геометрии.

### 2. Уровень 1 — минимум для тройки

Далее рассматриваем ковариантные тензоры (тип $(0,q)$), но аналогично для $(p,0)$.

**Определение (геометрическое).**

Тензор $\mathcal{T} \in T^0_q(V)$ (полилинейная функция $V^q \to \mathbb{k}$) называется:

- **симметрическим**, если $\mathcal{T}(\ldots, v_i, \ldots, v_j, \ldots) = \mathcal{T}(\ldots, v_j, \ldots, v_i, \ldots)$ при перестановке любых двух аргументов;
- **кососимметрическим** (или антисимметрическим), если $\mathcal{T}(\ldots, v_i, \ldots, v_j, \ldots) = -\mathcal{T}(\ldots, v_j, \ldots, v_i, \ldots)$.

Эквивалентно: $\mathcal{T}(v_{\sigma(1)}, \ldots, v_{\sigma(q)}) = \mathcal{T}(v_1,\ldots,v_q)$ (симм.) или $= \mathrm{sgn}(\sigma) \cdot \mathcal{T}(v_1,\ldots,v_q)$ (косс.) для любой перестановки $\sigma \in S_q$.

**Обозначения:** $S^q(V)$ — пространство симметрических тензоров типа $(0,q)$, $\Lambda^q(V^*)$ (или $\Lambda^q V^*$) — пространство кососимметрических.

**Определение (координатное).** Для $\mathcal{T}$ с компонентами $T_{j_1\ldots j_q} = \mathcal{T}(e_{j_1},\ldots,e_{j_q})$:

- Симметрический: $T_{j_1\ldots j_q} = T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}$ для всех $\sigma \in S_q$.
- Кососимметрический: $T_{j_1\ldots j_q} = \mathrm{sgn}(\sigma)\, T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}$ для всех $\sigma \in S_q$.

**Тривиальность при совпадающих индексах.** Если $\mathcal{T}$ кососимметрический и $v_i = v_j$ при $i \neq j$, то $\mathcal{T}(\ldots, v_i, \ldots, v_j, \ldots) = 0$.

В координатах: если $j_k = j_l$ при $k \neq l$, то $T_{j_1\ldots j_q} = 0$.

**Пример (тип (0,2)).** Кососимметричная билинейная форма $B$ (кососимметрическая матрица):
$B_{ij} = -B_{ji}$ и $B_{ii} = 0$. Пример: симплектическая форма $\omega = \sum_{k=1}^n dx^k \wedge dy^k$.

Симметрическая форма: $B_{ij} = B_{ji}$. Пример: скалярное произведение.

### 3. Уровень 2 — для четвёрки

**Размерности:**
- $\dim S^q(V) = \binom{n+q-1}{q}$ (мультикомбинации, $n = \dim V$).
- $\dim \Lambda^q(V^*) = \binom{n}{q}$ (при $q > n$: $= 0$).

**Пример: кососимметрические тензоры типа $(0,2)$ при $n=2$.** Компоненты $T_{ij}$ с $T_{ij} = -T_{ji}$, $T_{11} = T_{22} = 0$. Одна независимая компонента: $T_{12}$. $\dim \Lambda^2(\mathbb{R}^2) = 1$.

### 4. Мини-конспект

Симметрический $\mathcal{T}$: $\mathcal{T}(v_{\sigma(1)},\ldots) = \mathcal{T}(v_1,\ldots)$. Кососимметрический: $\mathcal{T}(v_{\sigma(1)},\ldots) = \mathrm{sgn}(\sigma)\mathcal{T}(v_1,\ldots)$. Следствие: если два аргумента равны, то $\mathcal{T} = 0$ (для косс.). В координатах: $T_{j_{\sigma(1)}\ldots} = \mathrm{sgn}(\sigma) T_{j_1\ldots}$, и $T_{\ldots k \ldots k \ldots} = 0$.

---

## Билет 52. Симметризация и альтернирование

### 1. Смысл билета

Из любого тензора можно получить симметрический или кososимметрический, усредняя по всем перестановкам. Эти операции — проекторы.

### 2. Уровень 1 — минимум для тройки

**Операция симметризации** $\mathrm{Sym}: T^0_q(V) \to S^q(V)$:

$$
(\mathrm{Sym}\, T)_{j_1\ldots j_q} = \frac{1}{q!} \sum_{\sigma \in S_q} T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}.
$$

Геометрически: $(\mathrm{Sym}\, \mathcal{T})(v_1,\ldots,v_q) = \frac{1}{q!} \sum_{\sigma \in S_q} \mathcal{T}(v_{\sigma(1)},\ldots,v_{\sigma(q)})$.

**Операция альтернирования (антисимметризации)** $\mathrm{Alt}: T^0_q(V) \to \Lambda^q(V^*)$:

$$
(\mathrm{Alt}\, T)_{j_1\ldots j_q} = \frac{1}{q!} \sum_{\sigma \in S_q} \mathrm{sgn}(\sigma)\, T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}.
$$

Геометрически: $(\mathrm{Alt}\, \mathcal{T})(v_1,\ldots,v_q) = \frac{1}{q!} \sum_{\sigma \in S_q} \mathrm{sgn}(\sigma)\, \mathcal{T}(v_{\sigma(1)},\ldots,v_{\sigma(q)})$.

**Свойство быть проектором.** Оба оператора — проекторы на соответствующие подпространства:

$$
\mathrm{Sym}^2 = \mathrm{Sym}, \quad \mathrm{Alt}^2 = \mathrm{Alt}.
$$

Более того:
- Если $T$ уже симметрический, то $\mathrm{Sym}\, T = T$.
- Если $T$ уже кососимметрический, то $\mathrm{Alt}\, T = T$.

### 3. Уровень 2 — для четвёрки

**Доказательство $\mathrm{Alt}^2 = \mathrm{Alt}$:** Пусть $T' = \mathrm{Alt}\, T$. Нужно показать $\mathrm{Alt}\, T' = T'$.

$$
(\mathrm{Alt}\, T')_{j_1\ldots j_q} = \frac{1}{q!} \sum_\tau \mathrm{sgn}(\tau)\, T'_{j_{\tau(1)}\ldots j_{\tau(q)}}.
$$

Но $T'_{j_{\tau(1)}\ldots j_{\tau(q)}} = \mathrm{sgn}(\tau) T'_{j_1\ldots j_q}$ (т.к. $T'$ кососимметрический). Значит:

$$
(\mathrm{Alt}\, T')_{j_1\ldots j_q} = \frac{1}{q!} \sum_\tau \mathrm{sgn}^2(\tau)\, T'_{j_1\ldots j_q} = \frac{1}{q!} \cdot q! \cdot T'_{j_1\ldots j_q} = T'_{j_1\ldots j_q}.
$$

**Примеры:**

$\mathrm{Sym}\,$ для $q=2$: $(\mathrm{Sym}\, T)_{ij} = \frac{T_{ij}+T_{ji}}{2}$.

$\mathrm{Alt}\,$ для $q=2$: $(\mathrm{Alt}\, T)_{ij} = \frac{T_{ij}-T_{ji}}{2}$.

Любая билинейная форма разлагается: $T = \mathrm{Sym}\, T + \mathrm{Alt}\, T$ (сумма симметрической и кососимметрической).

### 4. Мини-конспект

Симметризация: $(\mathrm{Sym}\, T)_{j_1\ldots j_q} = \frac{1}{q!}\sum_\sigma T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}$.

Альтернирование: $(\mathrm{Alt}\, T)_{j_1\ldots j_q} = \frac{1}{q!}\sum_\sigma \mathrm{sgn}(\sigma) T_{j_{\sigma(1)}\ldots j_{\sigma(q)}}$.

Оба — проекторы (идемпотенты). На симм./косс. тензорах — тождественный.

---

## Билет 53. Внешнее произведение. Внешняя алгебра

### 1. Смысл билета

Внешнее произведение $\wedge$ — кососимметричная версия тензорного произведения. Пространства $\Lambda^q(V^*)$ с этой операцией образуют внешнюю алгебру (алгебру Грасмана). В ней живут $q$-формы, определители, ориентации.

### 2. Уровень 1 — минимум для тройки

**Определение (по Панову).** Внешнее произведение $P \wedge Q$ для $P \in \Lambda^p(V^*)$ и $Q \in \Lambda^q(V^*)$:

$$
P \wedge Q = \frac{(p+q)!}{p!\, q!}\, \mathrm{Alt}(P \otimes Q).
$$

В координатах:

$$
(P \wedge Q)_{j_1\ldots j_{p+q}} = \frac{(p+q)!}{p!\,q!} \cdot \frac{1}{(p+q)!} \sum_{\sigma \in S_{p+q}} \mathrm{sgn}(\sigma)\, P_{j_{\sigma(1)}\ldots j_{\sigma(p)}} Q_{j_{\sigma(p+1)}\ldots j_{\sigma(p+q)}}.
$$

Это эквивалентно:

$$
(P \wedge Q)_{j_1\ldots j_{p+q}} = \frac{1}{p!\,q!} \sum_{\sigma \in S_{p+q}} \mathrm{sgn}(\sigma)\, P_{j_{\sigma(1)}\ldots j_{\sigma(p)}} Q_{j_{\sigma(p+1)}\ldots j_{\sigma(p+q)}}.
$$

**Свойства:**

1. **Антикоммутативность:** $P \wedge Q = (-1)^{pq}\, Q \wedge P$.  
   В частности, $\omega \wedge \omega = 0$ при нечётном $p$.

2. **Ассоциативность:** $(P \wedge Q) \wedge R = P \wedge (Q \wedge R)$.

3. **Бистепенность (bigraded):** $(P \wedge Q) \in \Lambda^{p+q}(V^*)$.

4. Для 1-форм $\alpha, \beta \in V^*$:

$$
(\alpha \wedge \beta)(u, v) = \alpha(u)\beta(v) - \alpha(v)\beta(u).
$$

**Внешняя алгебра (алгебра Грассмана):**

$$
\Lambda^*(V^*) = \bigoplus_{q=0}^n \Lambda^q(V^*),
$$

с операцией $\wedge$. Это **градуированно-коммутативная ассоциативная алгебра**: $\alpha \wedge \beta = (-1)^{|\alpha||\beta|} \beta \wedge \alpha$, где $|\alpha|, |\beta|$ — степени (= $p$ и $q$).

### 3. Уровень 2 — для четвёрки

**Базис $\Lambda^q(V^*)$.**

Пусть $\varepsilon^1, \ldots, \varepsilon^n$ — ОНБ $V^*$. Тогда

$$
\{\varepsilon^{i_1} \wedge \cdots \wedge \varepsilon^{i_q} : 1 \leq i_1 < i_2 < \cdots < i_q \leq n\}
$$

образует базис $\Lambda^q(V^*)$.

$$
\dim \Lambda^q(V^*) = \binom{n}{q}, \quad \dim \Lambda^*(V^*) = 2^n.
$$

**Определитель через внешнее произведение.**

Если $v_1, \ldots, v_n \in V$ и $e_1, \ldots, e_n$ — базис, то

$$
v_1 \wedge \cdots \wedge v_n = \det\!(v_1, \ldots, v_n)\cdot e_1 \wedge \cdots \wedge e_n,
$$

где $\det(v_1,\ldots,v_n)$ — определитель матрицы из координат $v_i$. (Здесь $v_1 \wedge \cdots \wedge v_n$ — элемент $\Lambda^n(V)$, а $e_1 \wedge \cdots \wedge e_n$ — базисный вектор.)

**Следствие.** $v_1, \ldots, v_n$ линейно зависимы $\Leftrightarrow$ $v_1 \wedge \cdots \wedge v_n = 0$.

**Частный случай $q=2$:**

Для $\alpha, \beta \in V^*$:

$$
(\alpha \wedge \beta)(u, v) = \begin{vmatrix} \alpha(u) & \alpha(v) \\ \beta(u) & \beta(v) \end{vmatrix} = \alpha(u)\beta(v) - \alpha(v)\beta(u).
$$

**Пример: стандартный объём.** $e^1 \wedge e^2 \wedge \cdots \wedge e^n (e_1,\ldots,e_n) = 1$.

### 4. Уровень 3 — глубина

**Связь со знаком перестановки.** Для 1-форм $\alpha_1, \ldots, \alpha_q$:

$$
(\alpha_1 \wedge \cdots \wedge \alpha_q)(v_1, \ldots, v_q) = \det\!\big((\alpha_i(v_j))_{i,j=1}^q\big).
$$

**Нормировка Ершова vs Панова.** В учебнике Ершова $P \wedge Q := \mathrm{Alt}(P \otimes Q)$ (без коэффициента $(p+q)!/(p!q!)$). В Панове — с этим коэффициентом. На экзамене использовать соглашение Панова.

**Производная Ли, дифференциальные формы** — приложения внешней алгебры в дифференциальной геометрии.

### 5. Доказательства

**Антикоммутативность (идея):** $P \wedge Q = \frac{(p+q)!}{p!q!}\mathrm{Alt}(P\otimes Q)$, аналогично $Q \wedge P = \frac{(p+q)!}{p!q!}\mathrm{Alt}(Q\otimes P)$. Нужно показать $\mathrm{Alt}(P\otimes Q) = (-1)^{pq}\mathrm{Alt}(Q\otimes P)$.

Перестановка аргументов $(v_1,\ldots,v_p,v_{p+1},\ldots,v_{p+q}) \to (v_{p+1},\ldots,v_{p+q},v_1,\ldots,v_p)$ — это перестановка знака $(-1)^{pq}$ (нужно сделать $pq$ транспозиций).

**Базис $\Lambda^q(V^*)$ (идея):** покажем линейную независимость $\varepsilon^{i_1}\wedge\cdots\wedge\varepsilon^{i_q}$ и то, что они порождают: любой кососимметрический тензор выражается через них.

**Определитель через внешнее произведение:** 
$v_1 \wedge \cdots \wedge v_n = (v_1^{j_1} e_{j_1})\wedge\cdots = v_1^{j_1}\cdots v_n^{j_n}(e_{j_1}\wedge\cdots\wedge e_{j_n})$. Единственный ненулевой член при всех различных $j_1,\ldots,j_n$ даёт $\sum_\sigma \mathrm{sgn}(\sigma)\prod v_i^{\sigma(i)} \cdot e_1\wedge\cdots\wedge e_n = \det(v_1,\ldots,v_n) \cdot e_1\wedge\cdots\wedge e_n$.

### 6. Примеры

**Пример 1.** $n=3$. $\varepsilon^1 \wedge \varepsilon^2 \wedge \varepsilon^3$ — единственный базисный вектор $\Lambda^3(\mathbb{R}^3)^*$.

**Пример 2.** $(\varepsilon^1 \wedge \varepsilon^2)(e_1, e_2) = 1$, $(\varepsilon^1 \wedge \varepsilon^2)(e_2, e_1) = -1$.

**Пример 3.** $\alpha = dx$, $\beta = dy$ — формы на $\mathbb{R}^2$: $(dx \wedge dy)(v, w) = v_1 w_2 - v_2 w_1$ = ориентированная площадь.

### 7. Типичные ошибки

- Путать нормировки: по Панову $P \wedge Q = \frac{(p+q)!}{p!q!}\mathrm{Alt}(P\otimes Q)$; по Ершову — без коэффициента.
- Считать, что $\alpha \wedge \alpha = 0$ для **любой** формы (нет! только при нечётной степени или для 1-форм; для чётных степеней $\alpha \wedge \alpha$ может быть $\neq 0$, например, $\omega \wedge \omega \neq 0$ для симплектической 2-формы).
- Забыть условие $i_1 < i_2 < \cdots < i_q$ в базисе.

### 8. Мини-конспект

$P \wedge Q = \frac{(p+q)!}{p!q!}\mathrm{Alt}(P\otimes Q)$ (по Панову). Для 1-форм: $(\alpha\wedge\beta)(u,v) = \alpha(u)\beta(v)-\alpha(v)\beta(u)$. Свойства: $(-1)^{pq}$ коммутативность, ассоциативность. Базис $\Lambda^q(V^*)$: $\{\varepsilon^{i_1}\wedge\cdots\wedge\varepsilon^{i_q}\}_{i_1<\cdots<i_q}$, $\dim = \binom{n}{q}$. Внешняя алгебра $\Lambda^* = \bigoplus_q \Lambda^q$, $\dim = 2^n$. Определитель: $v_1\wedge\cdots\wedge v_n = \det(v_1,\ldots,v_n)\cdot e_1\wedge\cdots\wedge e_n$.

---

## После батча 51–53

### Итоговая таблица

| Билет | Главная идея | Что учить дословно | Доказательство | Важность | Сложность |
|-------|-------------|-------------------|----------------|----------|-----------|
| 51 | Симм./кос. тензоры | Определения, $T_{\ldots k\ldots k\ldots}=0$ | Тривиально из определения | ★★★ | ★ |
| 52 | Симм-ция, альт-ние как проекторы | Формулы $\mathrm{Sym}$, $\mathrm{Alt}$; $\mathrm{Alt}^2=\mathrm{Alt}$ | $\mathrm{Alt}^2 = \mathrm{Alt}$ | ★★★ | ★★ |
| 53 | $\wedge$, внешняя алгебра, базис | $P\wedge Q = \frac{(p+q)!}{p!q!}\mathrm{Alt}(P\otimes Q)$; базис; $\det$ через $\wedge$ | Антикоммут., базис | ★★★ | ★★★ |

### Если времени мало

1. Кос.: $T(\ldots,v_i,\ldots,v_j,\ldots) = -T(\ldots,v_j,\ldots,v_i,\ldots)$; при $v_i=v_j$: $= 0$.
2. $\mathrm{Alt}(T)_{j_1\ldots} = \frac{1}{q!}\sum_\sigma \mathrm{sgn}(\sigma)T_{j_{\sigma(1)}\ldots}$; это проектор.
3. $P\wedge Q = \frac{(p+q)!}{p!q!}\mathrm{Alt}(P\otimes Q)$.
4. Базис $\Lambda^q$: $\{\varepsilon^{i_1}\wedge\cdots\wedge\varepsilon^{i_q}\}_{i_1<\cdots<i_q}$, $\dim = \binom{n}{q}$.
5. $v_1\wedge\cdots\wedge v_n = \det(\ldots)\cdot e_1\wedge\cdots\wedge e_n$.

### Вопросы для самопроверки

1. Что значит «кососимметрический тензор»?
2. Почему $T_{ijk} = 0$, если $i=j$ и $T$ кос.?
3. Запишите формулу $\mathrm{Alt}$ для $q=2$.
4. Почему $\mathrm{Alt}^2 = \mathrm{Alt}$?
5. Что такое внешнее произведение? Напишите формулу.
6. $P\wedge Q$ и $Q\wedge P$ — как связаны?
7. Каков базис $\Lambda^2(\mathbb{R}^4)$? Какова размерность?
8. Чему равно $v_1\wedge v_2\wedge v_3$ в $\mathbb{R}^3$?
9. Что такое внешняя алгебра?
10. Почему $\alpha\wedge\alpha=0$ для 1-формы $\alpha$?

### Задачи

1. Найдите $\mathrm{Alt}(T)$ для $T_{ij}$ — произвольной матрицы $2\times2$.
2. Вычислите $(dx\wedge dy)(e_1, e_2)$ и $(dx\wedge dy)(e_2, e_1)$.
3. Каков базис $\Lambda^3(\mathbb{R}^4)$? Сколько элементов?
4. Верно ли, что $(P\wedge Q)\wedge R = P\wedge (Q\wedge R)$? Почему?
5. Выразите $\det\begin{pmatrix}1&2\\3&4\end{pmatrix}$ через внешнее произведение строк.

### Plan

**Сразу:** запомнить формулы $\mathrm{Alt}$ и $\wedge$, базис $\Lambda^q$.  
**Вечером:** доказать $\mathrm{Alt}^2 = \mathrm{Alt}$ и антикоммутативность.  
**Утром:** написать формулу $v_1\wedge\cdots\wedge v_n = \det(\cdot)e_1\wedge\cdots\wedge e_n$.
