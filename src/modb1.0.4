#include <Arduino.h>
#include <M5Core2.h>
#include <string.h>
#include <stdio.h>

#include <WiFi.h>

#define mainColor WHITE
#define secColor DARKGREY

String FLine[14]; //die zeilen aus dem File
String Wert[14][12];  // Vor und hinter "=", erster index zeile, zweiter index 1=davor, 2=dahinter
int line_count;
const char *ssid;
const char *pwd;
float volt = 0;
String Einheit;
String WWert;
String IDBank[2] = {"1", "2"};
int BWeiter = 0;
String BankParam;


void readFile(fs::FS &fs, const char * path) 
{
    
  Serial.printf("Reading file: %s\n", path);
  M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
  M5.Lcd.setCursor(10, 5);
  M5.Lcd.setTextColor(secColor);
  M5.Lcd.printf("Reading file: %s\n", path);
  M5.Lcd.setTextColor(mainColor);
  delay(500);

  File file = fs.open(path);
  if(!file)
  {
    Serial.println("Failed to open file for reading");
    M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
    M5.Lcd.setCursor(10, 5);
    M5.Lcd.println("Failed to open file for reading");
    return;
  }

  Serial.println("Read from file: ");
  
  line_count = 0; //Index für Zeilennummer
    
  bool ZSprung = false;
    
  while (file.available()) 
  {
    line_count++;
    ZSprung = false;
    FLine[line_count] = file.readStringUntil('\n');  // \n character is discarded from buffer
    // check, ob Kommentar oder Leerzeile:
    if ((FLine[line_count].startsWith("/")) or (FLine[line_count].startsWith("\n")) or (FLine[line_count].startsWith(" ")) or (FLine[line_count].length()<=1))
    {
      line_count = line_count-1;
      //Serial.print("Lerzeile ");
      ZSprung = true; //wir überspringen eine zeile
    }

    if (!ZSprung) //wenn die zeile nicht übersprungen wird, also gültig ist
    {
      Serial.print("Line ");
      Serial.print(line_count);
      Serial.print(": ");
      Serial.println(FLine[line_count]);
      //M5.Lcd.println(FLine[line_count]);

      //Zeilen zerlegen
      int len;
      char *holen = NULL;
        
      len = FLine[line_count].length();
      char zeile[len];
      FLine[line_count].toCharArray(zeile, len);
      int wert_count = 1;
      holen = strtok(zeile, "|");
      Wert [line_count][wert_count] = String(holen);
      Serial.print(" 1. Wert: ");
      Serial.println(Wert [line_count][wert_count]);

      while (holen != NULL) 
      {
        wert_count++;
        holen = strtok(NULL, "|");
        if (holen != NULL)
        {
          Wert [line_count][wert_count] = String(holen);
          Serial.println(String(wert_count));
          Serial.println(Wert [line_count][wert_count]);
        }
      }
    }
  }
}

void WifiConn()
{
  for (int n = 1; n <= line_count; n++) //ssid holen
  {
    if (Wert[n][1] == "SSID")
    {      
      ssid = Wert[n][2].c_str();
      break;
    }
  }

  for (int n = 1; n <= line_count; n++) //pw holen
  {
    if (Wert [n][1] == "PW")
    {
      pwd = Wert[n][2].c_str();
      break;
    }
  }

  Serial.println("Connect Wlan");
  Serial.println(ssid);
  //M5.Lcd.clear();
  M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
  M5.Lcd.setCursor(10, 5);
  M5.Lcd.setTextColor(secColor);
  M5.Lcd.print("Connecting Wifi: ");
  M5.Lcd.println(ssid);
  M5.Lcd.setTextColor(mainColor);
  delay(200);
    
  WiFi.begin(ssid, pwd);

  while (WiFi.status() != WL_CONNECTED) 
  {
    delay(500);
    Serial.print(".");
  }
  Serial.println(" connected");
  Serial.print("local IP: ");
  Serial.println(WiFi.localIP());
  M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
  M5.Lcd.setCursor(10, 5);
  M5.Lcd.setTextColor(secColor);
  M5.Lcd.print("Connected: ");
  M5.Lcd.println(WiFi.localIP());
  M5.Lcd.setTextColor(mainColor);
  delay(1000);

}

float getParams(String Param) 
{
  uint16_t port;
  const char *host;  //Change to whatever your Controller IP is

  for (int n = 1; n <= line_count; n++) //Port holen
  {
    if (Wert[n][1] == "Port")
    {      
      port = Wert[n][2].toInt();
      break;
    }
  }
  for (int n = 1; n <= line_count; n++) //Host holen
  {
    if (Wert[n][1] == "Host")
    {      
      host = Wert[n][2].c_str();
      break;
    }
  }

  WiFiClient client;

  byte command[8];
  //const char *buffer;

  for (int n = 1; n <= line_count; n++) //Werte holen
  {
    if (Wert[n][1] == Param)
    {      
      Einheit = Wert[n][3]; //Einheit holen
      WWert = Wert[n][2]; //Welcher Wert holen

      for (int i=0; i<8; i++)
      {
        command[i]=Wert[n][4+i].toInt(); //tut mit dezimalen werten
        //Wert[n][3+i].toCharArray(buffer, 2);
        //Serial.println(buffer);
        //sscanf(buffer, "%2x", command[i]);
        //Serial.println(Wert[n][3+i]);
        Serial.println(command[i]);
      }
      
      break;
    }
  }
 
  if (client.connect(host, port)) //Try to connect to TCP Server
  {
    Serial.println("Connected to Controller... ");
    M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
    M5.Lcd.setTextColor(secColor);
    M5.Lcd.setCursor(10, 5);
    M5.Lcd.print("Connected to client. ");
    M5.Lcd.setTextColor(mainColor);

    //byte command[] = {0x01, 0x04, 0x31, 0x00, 0x00, 0x01, 0x3F, 0x36};
    client.write(command, sizeof(command));

    Serial.println("Command sent ... "); // command is the color or animation sent to the LED controller
  } 
  else
  {
    Serial.println("connection failed ... ");
    M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
    M5.Lcd.setTextColor(secColor);
    M5.Lcd.setCursor(10, 5);
    M5.Lcd.print("Connection failed. ");
    M5.Lcd.setTextColor(mainColor);
  }

  delay (500);

  int value[8];
  int i = 0;
      
  while (client.available()) 
  {
    int ch = client.read();
    i++;
    value[i] = ch;
    Serial.print(i);
    Serial.print("  ");
    Serial.println(value[i]);
    delay(20);
  }
      
  volt = ((value[4] * 256 + value[5])*0.01) ;

  delay(1000);

  if (!client.connected())
  {
    Serial.println();
    Serial.println("disconnecting ... ");
    M5.Lcd.fillRect(10, 5, 320, 20, BLACK);
    M5.Lcd.setTextColor(secColor);
    M5.Lcd.setCursor(10, 5);
    M5.Lcd.print("Disconnecting. ");
    M5.Lcd.setTextColor(mainColor);
    client.stop();
    //for(;;);
  }    
  return volt;
}

// the setup routine runs once when M5Stack starts up

void setup() { 
 
    // initialize the M5Stack object
    M5.begin();
    M5.Lcd.loadFont("Calibri-48", SD);
    M5.Lcd.drawRoundRect(5, 140-30,312,75,10,BLUE);
    M5.Lcd.setCursor(13, 140-22);
    M5.Lcd.fillRect(13, 140-22, 200, 24, BLACK);
    M5.Lcd.setCursor(10, 140);
    M5.Lcd.print(" ModB Mini");
    M5.Lcd.loadFont("Calibri-20", SD);
    M5.Lcd.print(" ");
    M5.Lcd.println("v1.0.3");

    delay(5000);

    Wire.begin();

    // Lcd display
    M5.Lcd.setBrightness(100);
    M5.Lcd.fillScreen(BLACK);
    M5.Lcd.setCursor(10, 5);
    M5.Lcd.setTextColor(WHITE);
    M5.Lcd.setTextSize(1);

        // config lesen
    readFile(SD, "/config.txt");
    WifiConn();

}

void loop() 
{
  // put your main code here, to run repeatedly:
  M5.update();
  //if we are not connected
  if(WiFi.status() != WL_CONNECTED)
  {
    WifiConn();      
  }

  // interner Akkustand anzeigen
  float batVoltage = M5.Axp.GetBatVoltage();
  float batPercentage = ( batVoltage < 3.2 ) ? 0 : ( batVoltage - 3.2 ) * 100;
  M5.Lcd.fillRect(240, 220, 80, 24, BLACK);
  M5.Lcd.setCursor(240, 220);
  M5.Lcd.setTextColor(secColor);
  M5.Lcd.print("Bat ");
  M5.Lcd.print((int)batPercentage);
  M5.Lcd.println("%");
  M5.Lcd.setTextColor(mainColor);

  // Knopfabfrage
  if (M5.BtnA.isPressed()) 
  {    //If the key is pressed. 
    BWeiter++;
    if (BWeiter > 1)
    {
      BWeiter=0;
    }
  }

  M5.Lcd.fillRect(35, 220, 100, 24, BLACK);
  M5.Lcd.setCursor(35, 220);
  M5.Lcd.setTextColor(mainColor);
  M5.Lcd.print("Bank ");
  M5.Lcd.print(String(BWeiter+1));
  // M5.Lcd.setTextColor(mainColor);

  BankParam = "ID1" + IDBank[BWeiter];
  volt = getParams(BankParam);
  int OZeile = 60; //oberste Zeile für Ausdruck
  if ((volt < 1000) and (volt >= 0))
  {
    Serial.print(BankParam);
    String voltstr;
    voltstr = "  " + String(volt);
    Serial.println(voltstr);
    
    M5.Lcd.fillRect(10, OZeile, 320, 48, BLACK);
    M5.Lcd.drawRoundRect(5, OZeile-30,312,75,10,BLUE);
    M5.Lcd.fillRect(13, OZeile-22, 200, 24, BLACK);
    M5.Lcd.setCursor(13, OZeile-22);
    M5.Lcd.print(WWert);
    M5.Lcd.loadFont("Calibri-48", SD);
    M5.Lcd.setCursor(10, OZeile);
    for (int i=1; i< (12 - voltstr.length()); i++)
    {
      M5.Lcd.print("  ");
    }
    M5.Lcd.print(voltstr);
    M5.Lcd.loadFont("Calibri-20", SD);
    M5.Lcd.print(" ");
    M5.Lcd.println(Einheit);
  }

  BankParam = "ID2" + IDBank[BWeiter];
  volt = getParams(BankParam);
  OZeile = 140; //oberste Zeile für Ausdruck
  if ((volt < 1000) and (volt >= 0))
  {
    Serial.print(BankParam);
    String voltstr;
    voltstr = "  " + String(volt);
    Serial.println(voltstr);
    
    M5.Lcd.fillRect(10, OZeile, 320, 48, BLACK);
    M5.Lcd.drawRoundRect(5, OZeile-30,312,75,10,BLUE);
    M5.Lcd.setCursor(13, OZeile-22);
    M5.Lcd.fillRect(13, OZeile-22, 200, 24, BLACK);
    M5.Lcd.print(WWert);
    M5.Lcd.loadFont("Calibri-48", SD);
    M5.Lcd.setCursor(10, OZeile);
    for (int i=1; i< (12 - voltstr.length()); i++)
    {
      M5.Lcd.print("  ");
    }
    M5.Lcd.print(voltstr);
    M5.Lcd.loadFont("Calibri-20", SD);
    M5.Lcd.print(" ");
    M5.Lcd.println(Einheit);
  }

  BankParam = "ID3" + IDBank[BWeiter];
  volt = getParams(BankParam);
  Serial.print("ID3 ");
  volt = volt * 100;

  Serial.println((int)volt);
  OZeile = 190; //oberste Zeile für Ausdruck
  if ((volt < 1000) and (volt >= 0))
  {
    Serial.print(BankParam);
    String voltstr;
    voltstr = String((int)volt);
    Serial.println(voltstr);
    
    M5.Lcd.fillRect(10, OZeile, 310, 24, BLACK);
    M5.Lcd.fillRect(157, OZeile, 160, 20, BLACK);
    M5.Lcd.progressBar(157, OZeile, 160,20, voltstr.toInt());
    M5.Lcd.setCursor(13, OZeile);
    M5.Lcd.print(WWert);
    M5.Lcd.print("  ");
    M5.Lcd.print(voltstr);
    M5.Lcd.print(" ");
    M5.Lcd.println(Einheit);
  }

  delay(4000);
}

