# Automacao em ESP32-MQTT - Temperatura e Umidade com Aviso de Incêndio

Este projeto é uma estação meteorológica baseada no ESP32 que monitora a temperatura e a umidade usando um sensor DHT22, exibe essas informações em um display LCD I2C, controla um LED indicador, publica os dados em um broker MQTT e sincroniza a hora local usando um servidor NTP. Além disso, em caso de temperatura crítica, o sistema aciona um buzzer piezoelétrico para alertar sobre perigo de incêndio.

![print1](https://github.com/JeffersonEvangelista/Automac-o-em-Esp32-Mqtt-/assets/114629197/0ad0464b-f4a4-405b-ac0b-d3804bd42e68)

## Funcionalidades

- **Leitura de Sensores**: Mede a temperatura e a umidade com o sensor DHT22.
- **Exibição em LCD**: Mostra os valores de temperatura e umidade em um display LCD I2C.
- **Controle de LED**: Acende um LED se a temperatura estiver fora dos limites definidos (acima de 50°C ou abaixo de 10°C).
- **Alarme de Incêndio**: Ativa um buzzer piezoelétrico quando a temperatura ultrapassa 60°C.
- **Publicação MQTT**: Envia os dados de temperatura e umidade para um broker MQTT (public.mqtthq.com) no tópico mqttHQ-client-test.
- **Sincronização de Hora**: Sincroniza a hora local usando o servidor NTP pool.ntp.org e exibe a hora atual no LCD.

## Hardware Necessário

- ESP32
- Sensor DHT22
- Display LCD I2C (16x2)
- LED 5mm
- Buzzer Piezoelétrico
- Resistores (10kΩ para pull-up no DHT22 e 220Ω para o LED)
- Jumpers e Protoboard

![wokwiPrint](https://github.com/JeffersonEvangelista/Automac-o-em-Esp32-Mqtt-/assets/114629197/7a49f7ca-f9ea-47ad-b2ca-d8d32cc20c4e)

## Conexões de Hardware

- **DHT22**: Pino de dados ao GPIO 15 do ESP32 com um resistor pull-up de 10kΩ.
- **LCD I2C**: SDA ao GPIO 21 e SCL ao GPIO 22 do ESP32.
- **LED**: Ânodo do LED ao GPIO 2 do ESP32 com um resistor de 220Ω e cátodo ao GND.
- **Buzzer**: Pino positivo ao GPIO 8 do ESP32 e pino negativo ao GND.

## Configuração

1. Clone o repositório e abra o projeto na sua IDE do Arduino.
    ```sh
    git clone https://github.com/seuusuario/esp32-fire-alarm.git
    cd esp32-fire-alarm
    ```
2. Certifique-se de ter todas as bibliotecas necessárias instaladas:
    - DHTesp
    - LiquidCrystal_I2C
    - WiFi
    - PubSubClient
3. Conecte o hardware conforme as especificações acima.
4. Atualize as configurações Wi-Fi e MQTT no código.
5. Faça upload do código para o seu ESP32.
6. Acesse o console serial para ver os logs de depuração.

## Como Usar

1. O ESP32 se conectará à rede Wi-Fi especificada e sincronizará a hora local.
2. Os dados de temperatura e umidade serão lidos a cada 10 segundos e exibidos no LCD.
3. Se a temperatura estiver fora dos limites definidos, o LED será aceso e, em caso de temperatura crítica (acima de 60°C), o buzzer será ativado.
4. Os dados de temperatura e umidade serão publicados no broker MQTT especificado.

## Licença

Este projeto é licenciado sob a MIT License.

Deft

