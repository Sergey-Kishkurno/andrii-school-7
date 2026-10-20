# Навчальний параграф: «Основи схемотехніки: Як читати електричні схеми»

Електрична принципова схема — це «карта» електронного пристрою. Вона показує не те, як деталі виглядають зовні, а **як вони електрично з'єднані між собою**. Уміння читати схеми дозволяє зрозуміти логіку роботи робота, правильно зібрати схему на макетній платі та знайти помилку, якщо щось не працює.

---

## 1. Анатомія принципової схеми

На будь-якій схемі є чотири основні елементи:

* **Умовні графічні позначення (УГО):** Символи, що позначають компоненти (резистори, світлодіоди, транзистори, мікроконтролери).
* **Лінії зв'язку (провідники):** Лінії, що зображують електричні з'єднання (дроти або доріжки на друкованій платі).
* **Вузли (з'єднання):** Точки на перетині ліній. **Точка є** — лінії з'єднані в один електричний вузол. **Точки немає** — лінії просто перетинаються на кресленні без електричного контакту.
* **Позначення та номінали:** Біля кожного компонента вказується його тип і порядковий номер (наприклад, $R1$, $C2$, $LED1$), а також його характеристика (наприклад, $10\text{ k}\Omega$, $100\text{ nF}$).

### Важливо: Вузли та Перетини

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 160" style="background-color: #f8fafc; border: 1px solid #e2e8f0; border-radius: 8px; width: 100%; max-width: 500px; height: auto;">
  <!-- Node with junction dot -->
  <g transform="translate(40, 20)">
    <line x1="20" y1="60" x2="160" y2="60" stroke="#1e293b" stroke-width="3" />
    <line x1="90" y1="10" x2="90" y2="110" stroke="#1e293b" stroke-width="3" />
    <circle cx="90" cy="60" r="6" fill="#2563eb" />
    <text x="90" y="135" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#2563eb">Є контакт (Вузол)</text>
  </g>
  
  <!-- Crossing wires without junction -->
  <g transform="translate(280, 20)">
    <line x1="20" y1="60" x2="160" y2="60" stroke="#1e293b" stroke-width="3" />
    <line x1="90" y1="10" x2="90" y2="110" stroke="#1e293b" stroke-width="3" />
    <text x="90" y="135" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#64748b">НЕМАЄ контакту</text>
  </g>
</svg>

---

## 2. Базові компоненти та їхні символи

Щоб читати схеми, потрібно запам'ятати базовий «алфавіт» схемотехніки:

### Графічна таблиця символів

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 650 320" style="background-color: #ffffff; border: 1px solid #cbd5e1; border-radius: 8px; width: 100%; max-width: 650px; height: auto;">
  <!-- Grid Lines -->
  <line x1="325" y1="10" x2="325" y2="310" stroke="#e2e8f0" stroke-width="2" stroke-dasharray="4" />
  <line x1="10" y1="160" x2="640" y2="160" stroke="#e2e8f0" stroke-width="2" stroke-dasharray="4" />

  <!-- 1. Resistor -->
  <g transform="translate(20, 20)">
    <text x="10" y="25" font-family="sans-serif" font-size="16" font-weight="bold" fill="#0f172a">1. Резистор (R)</text>
    <path d="M 30,80 L 70,80 L 80,65 L 95,95 L 110,65 L 125,95 L 140,65 L 155,95 L 165,80 L 205,80" fill="none" stroke="#2563eb" stroke-width="3" stroke-linejoin="round" stroke-linecap="round"/>
    <text x="117" y="125" text-anchor="middle" font-family="sans-serif" font-size="13" fill="#475569">Обмежує струм</text>
  </g>

  <!-- 2. Capacitor -->
  <g transform="translate(340, 20)">
    <text x="10" y="25" font-family="sans-serif" font-size="16" font-weight="bold" fill="#0f172a">2. Конденсатор (C)</text>
    <line x1="30" y1="80" x2="100" y2="80" stroke="#2563eb" stroke-width="3" />
    <line x1="100" y1="50" x2="100" y2="110" stroke="#2563eb" stroke-width="3" />
    <line x1="115" y1="50" x2="115" y2="110" stroke="#2563eb" stroke-width="3" />
    <line x1="115" y1="80" x2="185" y2="80" stroke="#2563eb" stroke-width="3" />
    <text x="107" y="125" text-anchor="middle" font-family="sans-serif" font-size="13" fill="#475569">Накопичує заряд</text>
  </g>

  <!-- 3. LED -->
  <g transform="translate(20, 170)">
    <text x="10" y="25" font-family="sans-serif" font-size="16" font-weight="bold" fill="#0f172a">3. Світлодіод (LED)</text>
    <line x1="30" y1="80" x2="80" y2="80" stroke="#2563eb" stroke-width="3" />
    <polygon points="80,60 80,100 120,80" fill="#2563eb" stroke="#2563eb" stroke-width="2" />
    <line x1="120" y1="60" x2="120" y2="100" stroke="#2563eb" stroke-width="3" />
    <line x1="120" y1="80" x2="170" y2="80" stroke="#2563eb" stroke-width="3" />
    <!-- Arrows -->
    <path d="M 100,50 L 115,35 M 115,35 L 105,35 M 115,35 L 115,45" fill="none" stroke="#dc2626" stroke-width="2" stroke-linecap="round" />
    <path d="M 115,50 L 130,35 M 130,35 L 120,35 M 130,35 L 130,45" fill="none" stroke="#dc2626" stroke-width="2" stroke-linecap="round" />
    <text x="70" y="115" text-anchor="middle" font-family="sans-serif" font-size="12" font-weight="bold" fill="#16a34a">Анод (+)</text>
    <text x="135" y="115" text-anchor="middle" font-family="sans-serif" font-size="12" font-weight="bold" fill="#dc2626">Катод (-)</text>
  </g>

  <!-- 4. Power & GND -->
  <g transform="translate(340, 170)">
    <text x="10" y="25" font-family="sans-serif" font-size="16" font-weight="bold" fill="#0f172a">4. Живлення та Земля</text>
    <!-- VCC -->
    <g transform="translate(30, 0)">
      <line x1="40" y1="90" x2="40" y2="60" stroke="#2563eb" stroke-width="3" />
      <polygon points="40,45 30,60 50,60" fill="#dc2626" />
      <text x="40" y="35" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#dc2626">VCC (+5V)</text>
    </g>
    <!-- GND -->
    <g transform="translate(130, 0)">
      <line x1="40" y1="45" x2="40" y2="70" stroke="#2563eb" stroke-width="3" />
      <line x1="20" y1="70" x2="60" y2="70" stroke="#2563eb" stroke-width="3" />
      <line x1="28" y1="77" x2="52" y2="77" stroke="#2563eb" stroke-width="3" />
      <line x1="34" y1="84" x2="46" y2="84" stroke="#2563eb" stroke-width="3" />
      <text x="40" y="105" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#1e293b">GND (0V)</text>
    </g>
  </g>
</svg>

---

## 3. Правила читання та "золоті" стандарти

* **Напрямок струму:** Схеми завжди читають **зліва направо** (від входу до виходу) і **згори вниз** (від плюс живлення $V_{CC}$ до землі $GND$).
* **Невидимі з'єднання (Мітки / Net Names):** На складних схемах, щоб не плутати лінії, провідники не тягнуть через увесь аркуш. Замість цього біля виводу ставлять назву мережі (наприклад, `MOTOR_PWM` або `SPI_MOSI`). **Усі виводи з однаковими назвами мереж вважаються з'єднаними між собою.**

---

## 4. Практичний приклад: Підключення світлодіода до мікроконтролера

Розглянемо класичний фрагмент схеми керування світлодіодом від цифрового піна мікроконтролера:

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 200" style="background-color: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; width: 100%; max-width: 680px; height: auto;">
  <!-- MCU Block -->
  <rect x="20" y="30" width="140" height="140" rx="6" fill="#1e293b" stroke="#0f172a" stroke-width="2" />
  <text x="90" y="60" text-anchor="middle" font-family="sans-serif" font-size="15" font-weight="bold" fill="#ffffff">MCU</text>
  <text x="90" y="80" text-anchor="middle" font-family="sans-serif" font-size="12" fill="#94a3b8">(Arduino / STM32)</text>
  
  <!-- MCU Pin D13 -->
  <circle cx="160" cy="100" r="4" fill="#38bdf8" />
  <text x="145" y="95" text-anchor="end" font-family="sans-serif" font-size="12" font-weight="bold" fill="#38bdf8">D13</text>

  <!-- Wire 1 -->
  <line x1="160" y1="100" x2="240" y2="100" stroke="#0284c7" stroke-width="3" />

  <!-- Resistor R1 -->
  <g transform="translate(240, 100)">
    <path d="M 0,0 L 15,0 L 22.5,-15 L 37.5,15 L 52.5,-15 L 67.5,15 L 82.5,-15 L 97.5,15 L 105,0 L 120,0" fill="none" stroke="#2563eb" stroke-width="3" stroke-linejoin="round" />
    <text x="60" y="-22" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#0f172a">R1</text>
    <text x="60" y="32" text-anchor="middle" font-family="sans-serif" font-size="13" font-weight="bold" fill="#059669">220 Ом</text>
  </g>

  <!-- Wire 2 -->
  <line x1="360" y1="100" x2="430" y2="100" stroke="#0284c7" stroke-width="3" />

  <!-- LED1 -->
  <g transform="translate(430, 100)">
    <line x1="0" y1="0" x2="20" y2="0" stroke="#0284c7" stroke-width="3" />
    <polygon points="20,-20 20,20 50,0" fill="#dc2626" stroke="#dc2626" stroke-width="2" />
    <line x1="50" y1="-20" x2="50" y2="20" stroke="#dc2626" stroke-width="3" />
    <line x1="50" y1="0" x2="70" y2="0" stroke="#0284c7" stroke-width="3" />
    
    <!-- Arrows -->
    <path d="M 30,-22 L 42,-34 M 42,-34 L 34,-34 M 42,-34 L 42,-26" fill="none" stroke="#dc2626" stroke-width="2" stroke-linecap="round" />
    <path d="M 42,-22 L 54,-34 M 54,-34 L 46,-34 M 54,-34 L 54,-26" fill="none" stroke="#dc2626" stroke-width="2" stroke-linecap="round" />

    <text x="35" y="32" text-anchor="middle" font-family="sans-serif" font-size="14" font-weight="bold" fill="#0f172a">LED1</text>
  </g>

  <!-- Wire 3 to GND -->
  <line x1="500" y1="100" x2="570" y2="100" stroke="#0284c7" stroke-width="3" />
  <line x1="570" y1="100" x2="570" y2="130" stroke="#0284c7" stroke-width="3" />

  <!-- GND Symbol -->
  <g transform="translate(570, 130)">
    <line x1="-20" y1="0" x2="20" y2="0" stroke="#1e293b" stroke-width="3" />
    <line x1="-12" y1="6" x2="12" y2="6" stroke="#1e293b" stroke-width="3" />
    <line x1="-5" y1="12" x2="5" y2="12" stroke="#1e293b" stroke-width="3" />
    <text x="0" y="28" text-anchor="middle" font-family="sans-serif" font-size="13" font-weight="bold" fill="#1e293b">GND</text>
  </g>
</svg>

### Логіка роботи
1. Від цифрового піна `D13` мікроконтролера лінія йде до **резистора `R1` (номінал $220\text{ Ом}$)**.
2. Друга ніжка резистора `R1` підключена до **анода (+)** світлодіода `LED1`.
3. **Катод (-)** світлодіода `LED1` підключений до **`GND` (землі)**.

> Коли мікроконтролер подає на `D13` високий рівень ($+5\text{ В}$), струм тече через резистор і світлодіод у `GND` — світлодіод світиться. Резистор `R1` є **струмообмежувальним**: без нього світлодіод або пін мікроконтролера згорить через надлишковий струм.

---

## Алгоритм розбору будь-якої схеми (для конспекту)

1. **Знайди джерело живлення** ($V_{CC}$) та **землю** ($GND$).
2. **Знайди головний мікроконтролер / мікросхему** та розберися з призначенням виводів.
3. **Розбий схему на функціональні блоки** (блок живлення, блок датчиків, блок драйвера моторів, блок індикації).
4. **Простеж шлях сигналів** від вхідних датчиків до мікроконтролера та від мікроконтролера до виконавчих пристроїв (моторів, реле, динаміків).

---

## Приклад конспекту, який має вийти у 7-класника:

> **Тема: Як читати принципові схеми**
>
> **1. Що є на схемі:**
> * **Символи (УГО)** — деталі ($R$, $C$, $LED$, $MCU$).
> * **Лінії** — дроти / доріжки.
> * **Точка на перетині** = є контакт. **Без точки** = лінії просто перетинаються.
>
> **2. Ключові позначення:**
> * $V_{CC}$ ($+5\text{ В} / +3.3\text{ В}$) — плюс живлення.
> * $GND$ — мінус / земля ($0\text{ В}$). Усі $GND$ на схемі з'єднані.
> * **Net Names (мітки)** — однакові назви біля ніжок означають, що вони з'єднані між собою.
>
> **3. Правила читання:**
> * Читаємо **зліва направо** і **згори ($V_{CC}$) вниз ($GND$)**.
>
> **4. Приклад (Світлодіод на піні D13):**
> * $D13 \rightarrow R1 (220\text{ Ом}) \rightarrow \text{Анод } LED1 \rightarrow \text{Катод } LED1 \rightarrow GND$.
> * *Навіщо $R1$?* Щоб обмежити струм і не спалити світлодіод/пін.