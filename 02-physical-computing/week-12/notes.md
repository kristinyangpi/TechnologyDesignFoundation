# Week 12 📅 Nov 9–13, 2026

# 🔌 Electronics 📟 Nov 10 — Self-study (Continue to work on our Expressive Mechanics project)

## Project: Expressive Mechanics — Iteration

### **01 Concept**
- I changed the **human figure from standing to squatting** because the pose communicates the toilet scene more naturally.
- I then developed the rear-facing character into someone who could turn around with an angry expression when their privacy was interrupted.
- **This led to a motion-controlled game:** the player holds a squat to keep the toilet door closed. Standing too early opens the door, and the physical character turns to look at them.

<table width="100%">
<tr>
<td valign="top" width="50%">

Before:
<img width="4284" height="5712" alt="IMG_0122" src="https://github.com/user-attachments/assets/cab9bcf7-d629-4abd-b164-345633684e6f" />

</td>
<td valign="top" width="50%">

After:
<img width="4284" height="5712" alt="IMG_0145" src="https://github.com/user-attachments/assets/17a9aebb-6ade-4c2a-8836-b6dddc9b4213" />

</td>
</tr>
</table>

### **02 Mechanism & Setup**

| Part | Role |
|---|---|
| Computer vision | Detects the player's pose / motion |
| p5.js | Reads the detection and sends a signal |
| Arduino | Receives the signal and drives the servo |
| Mechanism | Moves the squatting figure |

- I added a circular opening where the head would be. Behind it, a connected plate carries two drawings: the back of the head and an angry face. A servo moves the plate across the opening, creating the impression that the character turns around while the body stays still.
- The mechanism developed from a larger half-turn movement into a 45° V-shaped arm, then a double-V arm that carries both the head plate and the lower pieces.

<table width="100%">
<tr>
<td valign="top" width="50%">

Sketch:
<img width="4284" height="5712" alt="IMG_0123" src="https://github.com/user-attachments/assets/668bb890-e9a1-4cf9-8634-920a090b0db6" />
<img width="5712" height="4284" alt="IMG_0136" src="https://github.com/user-attachments/assets/771daa4f-2dc3-4c03-a9c3-079fd92198b9" />


</td>
<td valign="top" width="50%">

Lasercut:
<img width="4284" height="5712" alt="IMG_0170" src="https://github.com/user-attachments/assets/77066115-3be2-4436-a2c1-9cd8aff45de6" />

https://github.com/user-attachments/assets/37f30d08-62f9-4b42-9e79-6b9de8f804c6

</td>
</tr>
</table>

### **03 Game Implementation**

After having the physical part set, I decided to connect the mechanism to a toilet game, giving the character a setting and a reason to turn around. The player helps the character poop in peace by holding a squat to keep the toilet door closed. Standing up too early interrupts his privacy, making him turn around angrily.

| Player action | On-screen response | Physical mechanism |
|---|---|---|
| Squat and hold | Door stays closed; squat time accumulates | Character faces away |
| Stand up too early | Door opens; progress pauses | Angry face moves into view |
| Squat again | Door closes; progress resumes | Character turns back |

<table width="100%">
<tr>
<td width="50%" valign="top">

Game Interface Sketch in Illustrator:
<img width="677" height="477" alt="截圖 2026-11-24 中午12 55 19" src="https://github.com/user-attachments/assets/0ddbdd29-6658-46f3-9000-98810c10e29a" />


</td>
<td width="50%" valign="top">

  **Prompt for Codex**

instruction: this is a toilet with doors open and close controlled by motion
1. he needs to go to the toilet, help him walk over (motion: detects person mimicing walking with arms swinging )
2. knock to open the door (motion: detects person using either left or right hand to knock back and forth 2 times)
3. Come on in
4. Squat to lock the door! STAY IN POSITION UNTIL HE'S DONE! Or else the door will open (motion: detects user squating, door stays locked and triggers the pooping mechanism in arduino, the person will be done in 10 sec, if detects the user stand up within the 10 sec range, make door open and the person pooping shock and angry, until the user goes back to squating, door close again and time continues to count, if user stays squat for 10 sec, see instruction 5.)
5. He's done! Give him a thumbs up! (motion: detects user giving either left or right hand thumbs up, door opens and the person walks out. and triggers arduino to return to the 空 sign.
6. thanks for helping: your pooping score is: (depedning on how accurate the squat position is and if the person stopped squating in between , give a score from 1-100)
7. restart again

the style of the interface make it mimic the laser cutting wood and engraving style with simple line drawing and typography, show me a visualization before continueing

</td>
</tr>
</table>

**Codex Output:**
<img width="1156" height="675" alt="截圖 2026-11-24 下午1 02 16" src="https://github.com/user-attachments/assets/baa2a2b8-63d4-4d83-b787-4a8d200048fb" />

### **04 Coding and Circuit**

I connected the browser game to Arduino through Web Serial over USB. MediaPipe detects the player’s movement, JavaScript decides what should happen, and Arduino receives a command to move the servo.

| Part | Role |
|---|---|
| Webcam + MediaPipe | Detect the player's pose |
| Browser JavaScript | Run the game and decide when to trigger a reaction |
| USB serial connection | Send commands from the computer to Arduino |
| Arduino Uno + MG90S servo | Move between calibrated positions |
| Laser-cut plywood mechanism | Reveal the different head and lower-display states |

**Circuit**
<table width="100%">
<tr>
<td valign="top" width="50%">

Squat:
<img width="754" height="499" alt="sqaut" src="https://github.com/user-attachments/assets/1e49d81d-7738-49d9-81f1-183153dcde09" />


</td>
<td valign="top" width="50%">

Stand early
<img width="737" height="496" alt="stand early" src="https://github.com/user-attachments/assets/b79b6a4a-a85c-4f47-a2b7-065ddd61f39c" />


</td>
</tr>
</table>

```Arduino Code:
/* Hold it — firmware 1.2.0, Uno + MG90S on D9. Protocol hold-it/1, 115200 baud.
   Browser detects poses: squat keeps BACK; standing early sends FACE;
   squatting again sends BACK. The rigid arm also switches the poop/空 piece.
   No movement at boot. Retains the H2e/H3 EEPROM layout.
   Endpoints are measured on YOUR mechanism: 45 degrees TOTAL, not 180.
   Upload with Arduino IDE: board Arduino Uno, Servo library installed. */
#include <Servo.h>
#include <EEPROM.h>
#include <stdint.h>
#include <stdlib.h>
#include <string.h>

Servo motor;
const uint8_t SIGNAL_PIN=9;
const int MIN_US=700, MAX_US=2300;
// 1000 us/second: four times the original 5-us step every 20 ms.
// Only the travel rate changes; calibrated endpoints and EEPROM stay intact.
const int MOVE_STEP_US=20;
const uint16_t MOVE_INTERVAL_MS=20;
const uint32_t MAGIC=0x48535635UL;
struct Settings {uint32_t magic; int16_t vacant; int16_t occupied; uint16_t checksum;};
Settings settings;
bool calibrated=false, attached=false, moving=false, overflowed=false;
int currentUs=1500,targetUs=1500;
uint32_t movementId=0,lastRx=0,lastStep=0,settleAt=0;
uint16_t settleTime=150;
char state='?',line[64];uint8_t lineLength=0;

bool validPulse(int v){return v>=MIN_US&&v<=MAX_US;}
bool validPair(){int span=abs(settings.vacant-settings.occupied);return validPulse(settings.vacant)&&validPulse(settings.occupied)&&span>=100&&span<=800;}
uint16_t checksum(){return (uint16_t)(settings.vacant^settings.occupied^0x52A9);}
void message(const __FlashStringHelper* type,uint32_t id){
 Serial.print(F("{\"type\":\""));Serial.print(type);Serial.print(F("\",\"id\":"));Serial.print(id);
 Serial.print(F(",\"protocol\":\"hold-it/1\",\"firmware\":\"1.2.0\",\"reaction_commands\":true,\"sweep_us_per_second\":1000,\"calibrated\":"));Serial.print(calibrated?F("true"):F("false"));
 Serial.print(F(",\"vacant\":"));Serial.print(settings.vacant);Serial.print(F(",\"occupied\":"));Serial.print(settings.occupied);
 Serial.print(F(",\"current\":"));Serial.print(currentUs);Serial.print(F(",\"target\":"));Serial.print(targetUs);
 Serial.print(F(",\"attached\":"));Serial.print(attached?F("true"):F("false"));Serial.print(F(",\"moving\":"));Serial.print(moving?F("true"):F("false"));
 Serial.print(F(",\"state\":\""));Serial.print(state);Serial.println(F("\"}"));
}
void error(uint32_t id,const __FlashStringHelper* msg){Serial.print(F("{\"type\":\"error\",\"id\":"));Serial.print(id);Serial.print(F(",\"message\":\""));Serial.print(msg);Serial.println(F("\"}"));}
void stopMotor(){if(moving)error(movementId,F("Movement stopped."));moving=false;motor.detach();attached=false;state='?';}
void moveTo(int pulse,uint32_t id,char destination){
 if(!validPulse(pulse)){error(id,F("Pulse outside 700-2300 us."));return;}
 if(moving){error(id,F("Servo is busy."));return;}
 targetUs=pulse;movementId=id;state=destination;moving=true;settleAt=0;settleTime=150;
 if(!attached){
  // Preload target BEFORE attach: no default 1500-us pulse outside calibrated arc.
  motor.writeMicroseconds(pulse);motor.attach(SIGNAL_PIN,MIN_US,MAX_US);motor.writeMicroseconds(pulse);
  attached=true;currentUs=pulse;settleTime=600;
 }
 lastStep=millis();message(F("ack"),id);
}
bool number(const char* s,long& n){if(!s||!*s)return false;char* end;n=strtol(s,&end,10);return *end=='\0';}
void command(char* input){
 char* words[5];uint8_t count=0;char* p=strtok(input," \r");while(p&&count<5){words[count++]=p;p=strtok(NULL," \r");}
 if(count<2||count>4){error(0,F("Use a command followed by a numeric request ID."));return;}
 long request;if(!number(words[count-1],request)||request<1){error(0,F("Invalid request ID."));return;}
 uint32_t id=(uint32_t)request;const char* cmd=words[0];lastRx=millis();
 if(!strcmp(cmd,"HELLO")&&count==2){message(F("hello"),id);return;}
 if((!strcmp(cmd,"STATUS")||!strcmp(cmd,"PING"))&&count==2){message(F("status"),id);return;}
 if(!strcmp(cmd,"STOP")&&count==2){stopMotor();message(F("done"),id);return;}
 if(moving){error(id,F("Wait for the current movement to finish."));return;}
 if(!strcmp(cmd,"MOVE")&&count==3){if(!calibrated){error(id,F("Save calibrated servo endpoints first."));return;}if(!strcmp(words[1],"V"))moveTo(settings.vacant,id,'V');else if(!strcmp(words[1],"O"))moveTo(settings.occupied,id,'O');else error(id,F("Use MOVE V or MOVE O."));return;}
 if(!strcmp(cmd,"REACT")&&count==3){if(!calibrated){error(id,F("Save calibrated servo endpoints first."));return;}if(!strcmp(words[1],"BACK"))moveTo(settings.vacant,id,'V');else if(!strcmp(words[1],"FACE"))moveTo(settings.occupied,id,'O');else error(id,F("Use REACT BACK or REACT FACE."));return;}
 if(!strcmp(cmd,"CENTER")&&count==2){moveTo(1500,id,'?');return;}
 if(!strcmp(cmd,"JOG")&&count==3){long delta;if(!number(words[1],delta)||(delta!=10&&delta!=-10)){error(id,F("Jog must be +10 or -10 us."));return;}if(!attached){error(id,F("Center the bare horn first."));return;}moveTo(currentUs+(int)delta,id,'?');return;}
 if(!strcmp(cmd,"RECORD")&&count==3){if(!attached){error(id,F("Move the bare horn before recording."));return;}if(!strcmp(words[1],"V"))settings.vacant=currentUs;else if(!strcmp(words[1],"O"))settings.occupied=currentUs;else{error(id,F("Use RECORD V or RECORD O."));return;}calibrated=false;message(F("done"),id);return;}
 if(!strcmp(cmd,"SAVE")&&count==2){if(!validPair()){error(id,F("Endpoints need a 100-800 us span. Measure a 45-degree total turn."));return;}settings.magic=MAGIC;settings.checksum=checksum();EEPROM.put(0,settings);calibrated=true;message(F("done"),id);return;}
 error(id,F("Unknown command."));
}
void setup(){
 Serial.begin(115200);EEPROM.get(0,settings);
 calibrated=settings.magic==MAGIC&&settings.checksum==checksum()&&validPair();
 if(!calibrated){settings.magic=MAGIC;settings.vacant=0;settings.occupied=0;settings.checksum=0;}
 lastRx=millis();message(F("hello"),0);
}
void loop(){
 while(Serial.available()){
  char c=Serial.read();
  if(c=='\n'){if(overflowed)error(0,F("Command too long."));else if(lineLength){line[lineLength]='\0';command(line);}lineLength=0;overflowed=false;}
  else if(!overflowed&&c!='\r'){if(lineLength<sizeof(line)-1)line[lineLength++]=c;else{overflowed=true;lineLength=0;}}
 }
 uint32_t now=millis();
 if(attached&&(uint32_t)(now-lastRx)>6000){stopMotor();message(F("watchdog"),0);}
 if(moving&&(uint32_t)(now-lastStep)>=MOVE_INTERVAL_MS){lastStep=now;if(currentUs!=targetUs){int delta=targetUs-currentUs;currentUs+=delta>MOVE_STEP_US?MOVE_STEP_US:delta< -MOVE_STEP_US?-MOVE_STEP_US:delta;motor.writeMicroseconds(currentUs);settleAt=0;}
  else{if(!settleAt)settleAt=now;if((uint32_t)(now-settleAt)>=settleTime){moving=false;message(F("done"),movementId);}}
 }
}

```

### **05 Iterations**

1. **Calibration**
I updated the Arduino program for a 45° movement and recalibrated the two stopping positions. The program saved these positions so I could reuse them after reconnecting the board.

https://github.com/user-attachments/assets/e9bff186-5b14-4274-81d0-7a232aafb60f

2. **Simplifying the game play and user journey**
The first version followed a full journey: running to the toilet → knocking → squatting → giving a thumbs-up to finish. This created a story, but each stage introduced a different gesture and instruction for the player to learn.

I simplified the gameplay to focus on squatting and standing up, making the interaction more intuitive and easier to understand.

| Earlier version | Simplified version |
|---|---|
| Multiple gestures across several stages | Two main actions: squat and stand |
| Running and knocking before the squat challenge | Start directly with squatting |
| Thumbs-up to finish | Stand up to finish the timing challenge |

<img width="1186" height="602" alt="截圖 2026-11-24 下午1 24 30" src="https://github.com/user-attachments/assets/908bef16-4d70-447f-b283-46f7a8a787d4" />

4. **Increase servo speed to match movement respond**
I increased the programmed servo sweep rate from 5 to 20 microseconds per 20-millisecond update, while keeping the calibrated endpoints. This made the commanded movement four times faster; the actual movement still depended on the mechanism’s load.

5. **Making pose calibration easier to follow**
Initially, players had to start the standing and squat recordings separately. I replaced this with a guided sequence:

**Press once → countdown → record standing → record squat → start automatically**

https://github.com/user-attachments/assets/55c65553-d62b-4cf3-8c43-af8cbe9a32cc


## Key takeaways/ Challenges
- **The mechanism doesn't need to be complicated but it needs to be meaningful** Connecting the turning face to an interruption of privacy gave the movement meaning and made the character feel responsive, this was also the part that challenged me the most. Since my mechanical movement was simple, I focused on thinking of a meaningful and interactive way to connect human pose with the mechanical movement.
- **Simplifying the interaction strengthened the game.** Focusing on squatting and standing made the relationship between the player’s actions and the character’s reaction easier to understand.
- **Small movements can communicate personality.** Changing from the back of a head to an angry face created a clear, humorous response with a limited range of motion.
- **The physical and digital parts had to develop together.** Pose detection, game timing, servo speed and mechanical alignment all influenced how immediate and understandable the interaction felt.

## Moving Forward
- Test with new players to see whether they understand the game with minimal instructions.
- Refine pose detection across different body proportions, camera positions and lighting conditions.
- Improve the mechanism’s alignment and durability through repeated testing.
- Explore a separate vertical movement for the 💩, coordinated with the turning face, to develop the mechanical expression further.
  https://github.com/user-attachments/assets/25827b49-cdbf-4025-b92e-77741a610089

# 🥽 Fabrication & Prototyping 🛠 Nov 12 — Expressive Mechanics Crit Day!
**Final Outcome:**
<img width="1448" height="1086" alt="01-front" src="https://github.com/user-attachments/assets/d1d5b95a-ecba-4a69-9409-3440343edd83" />
<table width="100%">
<tr>
<td valign="top" width="50%">

Face back:
<img width="1254" height="1254" alt="03-face-back-closeup" src="https://github.com/user-attachments/assets/6f35bfee-fb37-43a3-9044-ef29e6ccea13" />



</td>
<td valign="top" width="50%">

Turn around:
<img width="1254" height="1254" alt="04-face-angry-closeup" src="https://github.com/user-attachments/assets/9faea966-1c50-4f2e-bdbe-9167c902a6e3" />



</td>
</tr>
</table>

<img width="1536" height="1024" alt="02-laptop-connection" src="https://github.com/user-attachments/assets/c1b6a893-394b-4efb-b461-5162ed6af5fd" />

### Demo:

https://github.com/user-attachments/assets/665bf10b-66cc-4f5b-bb21-06c8ce0fa588


