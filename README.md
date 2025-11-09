# How Computers Understand Information  
### Foundations of Digital Representation for Software Engineers  

> Explore how computers interpret numbers, text, and data through binary logic and positional numeral systems.

---

## 1. Introduction  

When we think of a computer, we usually picture a machine capable of doing many things at once — running programs, displaying images, playing music, or connecting to the Internet. Yet behind all that apparent complexity lies a simple idea: a digital system does not understand the world as we do. It doesn’t recognize sounds, words, or colors on its own; it can only work with data represented in a form it can interpret.  

A software engineer must first understand **how information is represented inside the system**. Otherwise, programming becomes a purely mechanical activity, disconnected from the reality of what actually happens when a program runs or when a file is saved. The goal of this first topic is not to teach electronics, but to explore the starting point of all computing: how real-world data is transformed into a format that machines can process with precision.  

You can think of a computer as someone who follows instructions only when they’re written in their own language. When we ask it to perform an operation or display text, what we are really doing is translating our ideas into a set of symbols that it can understand. This translation is possible thanks to a set of mathematical and logical conventions that allow **any kind of information** — a number, a word, an image, or a sound — to be expressed using only a few basic symbols.  

For example, if we wanted to save the sentence “Hello world” on a computer, each letter would first need to be converted into a form the system can interpret. The same happens with a photograph, a song, or even a program instruction: everything the computer manipulates must be transformed into an organized sequence of data. That organization doesn’t arise by chance; it follows specific rules that we will study in this module.  

The purpose of this introductory block is therefore to understand **what “information” means for a machine**, and how it can store and process it. In the following sections, we will explore the different numeral systems, see how data can be expressed in multiple ways depending on the context, and discover how these representations form the foundation upon which all software is ultimately built.  

## 2. Positional Numeral Systems  

Every computer system needs a way to represent information. A computer cannot handle words, images, or sounds directly; it must first translate everything into numerical values that can be stored and processed through precise mathematical rules. Before understanding how that happens, it’s essential to review how numeral systems work, since they are the foundation of all digital representation.  

In everyday life, we use the **decimal system**, which has base ten because it relies on ten symbols: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. With these symbols we can form numbers of any size by combining digits according to their position. This position is crucial — it determines the **weight** of each digit within the number. That’s why we call it a *positional system*. In the number 472, the digit 4 does not simply mean “four,” but “four hundreds,” because it occupies the third position from the right. Meanwhile, the 2 represents two units, because it’s in the first position.  

Let’s break down 472 to make this clearer:  

472 = (4 × 10²) + (7 × 10¹) + (2 × 10⁰)  

Here, each position represents a **power of the base** (10⁰, 10¹, 10²…) and each digit is multiplied by that power. Performing the operations gives us 400 + 70 + 2 = 472. This is the general rule for any positional system, regardless of the base used.  

The decimal system is just one of many possible systems. Its choice is not mathematical, but historical and biological: humans have ten fingers, and since prehistoric times we’ve counted using them. Other civilizations adopted different bases. The **Babylonians** used base 60 (*sexagesimal*), which still survives in how we measure time and angles (60 seconds per minute, 360 degrees in a circle). The **Maya** used base 20 (*vigesimal*). This shows that the base itself is just a convention — the logic behind it remains the same.  

Each numeral system has its own set of symbols and its own rules for advancing from one number to the next. The central idea is simple: **when a position reaches its maximum value, it resets to zero and increases the position immediately to its left by one.** This mechanism, known as the **positional counting algorithm**, works identically in every base; the only difference lies in how many symbols are available.  

Let’s apply this idea to the decimal system (base 10). Here we have ten symbols (0–9). Counting always follows the same process: start at 0 and add one step by step. As long as the current digit is less than 9, we simply replace it with the next one. But when a position reaches 9 and we add one more, it resets to 0, and the next position to the left increases by one. If that position was also 9, the process repeats, cascading left until every position is within range again.  

This can be expressed as a simple algorithm:  
1. Start with the lowest number (e.g., 0).  
2. Add one to the rightmost position.  
3. If the result is still below the base, stop.  
4. If it equals the base, reset that position to 0 and add one to the next position on the left.  
5. Repeat the process as needed.  

Applying this to decimal counting gives the familiar sequence:  

0 → 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9  

Here, no resets have occurred yet because we’re still within a single digit. But when we try to add one more to 9, the digit reaches the base limit. According to the algorithm, we reset that position to 0 and add one to the left-hand position, which was previously 0. Thus we move from 09 to 10:  

09 + 1 = 10  

From that point, the left digit remains fixed while the right one cycles again:  

10 → 11 → 12 → 13 → 14 → 15 → 16 → 17 → 18 → 19  

When we reach 19 and add one more, the units position overflows again (from 9 to 0), and the tens position increases by one, resulting in 20. The same pattern continues indefinitely:  

… 97 → 98 → 99 → 100  

The governing principle remains constant: each position represents a power of the base, and the entire number is the weighted sum of those powers. For example:  

- In base 8 (octal), 345₈ = (3×8²) + (4×8¹) + (5×8⁰) = 192 + 32 + 5 = **229₁₀**  
- In base 16 (hexadecimal), 2A₁₆ = (2×16¹) + (10×16⁰) = 32 + 10 = **42₁₀**  

Understanding positional numeral systems is essential in software engineering because it explains how the data written in a program is represented internally. A number you see on screen as “125” is actually stored as a combination of electrical states that represent powers of a specific base. In computers, that base is **2**, known as the **binary system**, which uses only the symbols 0 and 1. Each of those values corresponds to a physical state in the circuit — *off/on*, *low/high*, or *false/true*.  

This simplicity brings enormous advantages. Digital systems operate with electrical signals that can be disturbed by noise or interference. If there were many possible levels —as in analog electronics— small variations could easily cause errors. But when there are only two stable states, the chance of misinterpreting a signal is extremely low. This robustness is one of the main reasons why the binary system became the foundation of modern computing.  

From a software perspective, each 0 or 1 is called a **bit**, short for *binary digit*. A bit is the smallest unit of information in a digital system. While a single bit can only represent two values (0 or 1), combining them enables exponentially larger quantities of information. With 2 bits we can represent 4 possible values (00, 01, 10, 11); with 3 bits, 8 values; with 4 bits, 16 values — and so on. This ability to generate infinite combinations from just a few symbols is what makes positional systems, and the binary system in particular, so powerful.  

