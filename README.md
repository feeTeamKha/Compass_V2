![image](https://github.com/feeTeamKha/Compass_V2/assets/110970367/734743f4-641f-48c9-9b6b-32707710b125)\

Code for Anduino Mega2560:

    uint8_t Header = 0;
    uint8_t Start_Frame = 0;
    uint8_t rxBuffer[1];
    uint8_t rxBuffer2[4];
    uint8_t counter=0
    int16_t Angle;
    void setup() {
    
    Serial.begin(9600);
    Serial1.begin(115200);
    Serial1.write('a');
    delay(100);
    Serial1.write('z');
    }
    
    void loop() {
      if(Serial1.available() > 0)
      {


      Serial1.readBytes(rxBuffer, 1);
      Header = rxBuffer[0];
      if(Header == 'z')
      {
        Start_Frame = 1;
        counter = 0;
      }
      else if(Start_Frame== 1)
      {
        if(counter == 0) {rxBuffer2[0] = rxBuffer[0]; counter =1; }
        else if(counter == 1) {rxBuffer2[1] = rxBuffer[0]; counter =2; }
        else if(counter == 2) 
                {
                  rxBuffer2[2] = rxBuffer[0]; 
                  counter = 3; 
                  Start_Frame = 2; 
                  Angle = (rxBuffer2[0] * 10000 + rxBuffer2[1] * 100 + rxBuffer2[2]) - 500000;
                  Angle = Angle*360/3600;
                  Serial.println(Angle);
                }
        }
      }
    }
