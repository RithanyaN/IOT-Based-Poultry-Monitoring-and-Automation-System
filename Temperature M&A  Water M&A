#define BLYNK_TEMPLATE_ID "TMPL34SRISORW"
#define BLYNK_TEMPLATE_NAME "Poultry Monitoring and Automation System"
#define BLYNK_AUTH_TOKEN "dJ2_RoSKEgBPtbDnf_K1-5B-qwvhIKIK"
#define BLYNK_PRINT Serial
#define DHTPIN 4  // connect to pin 2
int val=D1; 
#include <DHT.h>
#include <ESP8266WiFi.h> 
#include <BlynkSimpleEsp8266.h>
#define DHTTYPE DHT11
DHT dht(DHTPIN, DHTTYPE);
char ssid[] = "realme C11"; 
char pass[] = "rithanya";
char auth[] = "dJ2_RoSKEgBPtbDnf_K1-5B-qwvhIKIK";
void temperature()
{
    float temperature = dht.readTemperature();
  if (isnan(temperature)) 
  {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" °C");
  Blynk.virtualWrite(V0, temperature);
  if (temperature>20)
  {
    digitalWrite(val,HIGH);
    Serial.println("Light is on");
  }
  else
  {
    digitalWrite(val,LOW);
    Serial.println("Light is off");
  }
  delay(1000);
}
void setup() 
{
  Serial.begin(9600);
  Blynk.begin(auth, ssid, pass);
  dht.begin();
  pinMode(val,OUTPUT);
}
void loop() 
{
  Blynk.run();
  temperature();
}
