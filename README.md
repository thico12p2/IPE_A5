#include <Stepper.h>
#include "BluetoothSerial.h"

#if !defined(CONFIG_BT_ENABLED) || !defined(CONFIG_BLUEDROID_ENABLED)
#error Bluetooth is not enabled! Please run `make menuconfig` to and enable it
#endif

BluetoothSerial SerialBT;

const int passosPorVolta = 2048;
Stepper meuMotor(passosPorVolta, 13, 14, 12, 27);

void setup() {
  Serial.begin(115200);
  SerialBT.begin("Catapulta_ESP32"); 
  meuMotor.setSpeed(12);
}

void loop() {
  if (SerialBT.available()) {
    char comando = SerialBT.read();

    if (comando == 'C' || comando == 'c') {
      meuMotor.step(2048); 
    } 
    else if (comando == 'L' || comando == 'l') {
      meuMotor.step(-2048); 
    }
  }
  delay(20);
}
