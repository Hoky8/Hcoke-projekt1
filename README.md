# hocke-projekt(tepltní snímač)

projekt obsahuje porovnaní s teploměrem crivit a zrychlený postup složení teplotního snímače

potřebné komponentny: 

Počítač (k napájení a programování)/
Teplotní senzor TMP36/
LCD displej/
Nepájivé pole/
Vodiče/
Resistor 220Ω/
Vývojovou desku Arduino Uno/
USB kabel/

schéma:


![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/b09244d7-a449-47c4-980d-ae28515a7f2c)

software:

// Projekt Arduino teplota na displeji

#include <LiquidCrystal.h>
const int sensorPin = A0;
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup() {
  lcd.begin(16, 2);
  // nastaveni posilani pres seriovy port rychlosti 9600 baud
  Serial.begin(9600);
}

void loop() {
  int sensorVal = analogRead(sensorPin);
  float voltage = (sensorVal / 1024.0) * 5.0;
  float temperature = (voltage - 0.5) * 100.0;
  lcd.setCursor(0,0);
  lcd.print("teplota");
  lcd.print(temperature);
  lcd.print(" C ____");
  delay(2000);
}

zapojení:

napajení(červené drátky)

![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/e1f43b45-9826-42f4-b879-272074d89e17)

analog(bílí drátek)

![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/6483b41e-ca8c-4121-a69f-22fc58c540a7)

zem(modré drátky

![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/180b7bad-3726-48cd-8960-27f3242aefd6)

zapojení digitalních drátku dne schématu 

![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/aebe5150-7102-408d-8455-5915813a97e0)

z osobní zkušenosti varuji před nedostatkem ve schématu kde není zapojení Vo (dle obrázku žlutého drátku) jedná se o zapojení potenciometru avšak pro náš projekt bude stačit zapojit na zem

po složeni vlastního "teploměru" můžete porovnat s nějakým co máte již doma ja tak učinil a došel jsem k závěru že je co doladit 
níže je výsledek porovnání které probíhalo ve 3 různých prostorách hodnoty v tabulce jsou vždy průměrem 3 měření cca 20 sekund po sobě 

![image](https://github.com/Hoky8/hocke-projekt/assets/154540264/e19910f2-6214-45d1-9677-34c2ecd80a93)
# Hcoke-projekt1
