# "Multi-thread"_in_Arduino
A multitasking action (doing two or more tasks at once or at different times) on an Arduino can be carried out via multi-threading.
https://forum.arduino.cc/u/atul6556/

download library from here --

link => 


        #include <TimedAction.h>
        #include "thread1.h"
        #include "thread2.h"
        #include "flashing.h"
        //https://forum.arduino.cc/u/atul6556/

        void setup() {
          pinMode(13,OUTPUT);
          Serial.begin(115200);
          changeText();
          flash();
        }


        void maintask(){
          Serial.println("Main Task Running .....");
          digitalWrite(13,HIGH);
        }

        //
        void changeText(){  
          Serial.println("https://forum.arduino.cc/u/atul6556/");
        }
        //

        TimedAction mainThread = TimedAction(1000,maintask);
        TimedAction task1Thread = TimedAction(1000,task1);
        TimedAction task2Thread = TimedAction(5000,task2);
        TimedAction flashThread = TimedAction(6000,flash);





        void loop() {
          mainThread.check();
          task1Thread.check();
          task2Thread.check();
          flashThread.check();



        }
        //https://forum.arduino.cc/u/atul6556/

            }

