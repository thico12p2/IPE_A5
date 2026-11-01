# Catapulta controlada por Bluetooth (ESP32)

Projeto da disciplina **Introdução a Projetos de Engenharia (IME)**: uma catapulta acionada por motor de
passo e controlada pelo celular via Bluetooth.

## Como funciona

- O **ESP32** cria um dispositivo Bluetooth chamado `Catapulta_ESP32`.
- Pelo celular, um app de terminal Bluetooth envia comandos de um caractere:
  - `C` → o motor dá uma volta completa num sentido (2048 passos);
  - `L` → o motor dá uma volta completa no sentido oposto.
- O motor de passo é ligado aos pinos 13, 14, 12 e 27 e gira a 12 RPM.

## Hardware

- ESP32 (com Bluetooth Classic habilitado)
- Motor de passo de 2048 passos por volta (por exemplo, 28BYJ-48) com driver
- Fonte de alimentação para o motor

## Como usar

1. Abra `catapulta_esp32/catapulta_esp32.ino` na Arduino IDE com o pacote de placas ESP32 instalado.
2. Grave no ESP32.
3. Pareie o celular com `Catapulta_ESP32` e envie `C` ou `L` por um app de terminal Bluetooth.

## Tecnologias

C++ (Arduino) · ESP32 · BluetoothSerial · Stepper
