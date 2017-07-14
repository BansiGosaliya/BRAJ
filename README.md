# BRAJ
#include <GSM.h>

#define PINNUMBER ""


GSM gsmAccess;
GSM_SMS sms;

void setup()
{
 
  Serial.begin(9600);
  while (!Serial) {
    ; 
  }

  Serial.println("SMS Messages Sender");

  
  boolean notConnected = true;

  
  while (notConnected)
  {
    if (gsmAccess.begin(PINNUMBER) == GSM_READY)
      notConnected = false;
    else
    {
      Serial.println("Not connected");
      delay(1000);
    }
  }

  Serial.println("GSM initialized");
}


