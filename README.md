# Verkefni-5 - Animatronics-figura

[Myndband af virkni](https://www.youtube.com/channel/UCalAswnoYvKqwOg9npZweKw)

---

Markmiðið var að vera með beinagrind sem snýst í hringi, hristir hendurnar, ljós í augum skipta um lit og kjálki hreyfist í takt við hljóð. Við notum hreyfiskynjara sem trigger.

---

# Verkskipting

## Búkur - Guðbjörg og Mohamed

- Búkur samansettur
- Snúning á búk (kominn kóði)
- Hendur snúast á úlnliðunum (vantar kóða)

## Höfuðkúpa - Hreimur og Alexíus

- Hreyfing á kjálka
- ljós í augum
- skynjari virkar
- hátalarar virka

---

# Efniviður notaður
- DC Motor
- DC Motor driver
- rör
- skrúfur
- málmbitar
- Arduino
- jumperar
- koparvír
- 2 Servo motorar
- rgb led perur
- hreyfiskynjari
- mp3 spilari
- hátalarar
- límband
- zipties

---

# Heimildir
- [DC Motor kóði](https://lastminuteengineers.com/l298n-dc-stepper-driver-arduino-tutorial/)
- Arduino examples

---

# Myndir
![bukur](https://user-images.githubusercontent.com/111804480/195713701-589f3835-6df9-48d2-868a-1eac73fa2a6a.png)
![Duddalingur](https://user-images.githubusercontent.com/111804480/195713707-c52dac76-2f9f-4190-93a8-677416b08fbd.png)
![festing](https://user-images.githubusercontent.com/111804480/195713710-fda83a8c-0977-40fb-a947-d9ad759b3409.png)
![hofud](https://user-images.githubusercontent.com/111804480/195713713-70e58f09-0fca-482b-8558-c22344d1906c.png)
![pose](https://user-images.githubusercontent.com/111804480/195713716-29884d30-6b5b-4e96-8aa1-5e5e0c114c60.png)

---

#Kóði

## Búkur

```

// Motor A connections
int enA = 9;
int in1 = 6;
int in2 = 5;

void setup() {
  // Set all the motor control pins to outputs
  pinMode(enA, OUTPUT);
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  
  // Turn off motors - Initial state
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
}

void loop() {
  directionControl();
  delay(1000);
  speedControl();
  delay(1000);
}

// This function lets you control spinning direction of motors
void directionControl() {
  // Set motors to maximum speed
  // For PWM maximum possible values are 0 to 255
  analogWrite(enA, 150);

  // Turn on motor A & B
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  delay(2000);
  
  // Now change motor directions
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  delay(2000);
  
  // Turn off motors
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
}

// This function lets you control speed of the motors
void speedControl() {
  // Turn on motors
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  
  // Accelerate from zero to maximum speed
  for (int i = 0; i < 151; i++) {
    analogWrite(enA, i);
    delay(20);
  }
  
  // Decelerate from maximum speed to zero
  for (int i = 150; i >= 0; --i) {
    analogWrite(enA, i);
    delay(20);
  }
  
  // Now turn off motors
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
}

```

## Höfuð

```

Hreimur var með kóðann af því á sinni tölvu

```
