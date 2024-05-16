# hocke-projekt(tepltní snímač)

# projekt obsahuje porovnaní s teploměrem crivit a zrychlený postup složení teplotního snímače

Počítač (k napájení a programování)/
Teplotní senzor TMP36/
LCD displej/
Nepájivé pole/
Vodiče/
Resistor 220Ω/
Vývojovou desku Arduino Uno/
USB kabel/

# schéma:

![schema](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/7711c844-d2c8-44d0-b23d-f5d2173a0ce7)




# software:

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

# zapojení:

# napajení(červené drátky)

![IMG_7945](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/1cb9afb6-1b80-41c0-8d4f-580e68a65ffa)


#analog(bílí drátek)

![IMG_7946](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/5fe094e9-80f9-42f0-a98e-c5f0c81da225)


# zem(modré drátky

![IMG_7947](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/08f07dca-9f5c-4c87-a5ec-1104dfc3d9d6)


# zapojení digitalních drátku dne schématu 

![IMG_7948](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/69309b35-992a-42f2-bdb6-c9af94148a49)
# doporučení
z osobní zkušenosti varuji před nedostatkem ve schématu kde není zapojení Vo (dle obrázku žlutého drátku) jedná se o zapojení potenciometru avšak pro náš projekt bude stačit zapojit na zem

po složeni vlastního "teploměru" můžete porovnat s nějakým co máte již doma ja tak učinil a došel jsem k závěru že je co doladit 
níže je výsledek porovnání které probíhalo ve 3 různých prostorách hodnoty v tabulce jsou vždy průměrem 3 měření cca 20 sekund po sobě 

![projekt 264](https://github.com/Hoky8/Hcoke-projekt1/assets/154540264/33c21bc6-648a-4a13-9a39-bc1575eeccdd)


# Hcoke-projekt1
