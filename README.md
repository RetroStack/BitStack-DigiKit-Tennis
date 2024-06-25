# DigiKit Tennis Replica

While watching my regular YouTube channels, I saw a digital electronics kit from the 70s called Tennis from the company DigiKit, [shown on the Tech Time Traveller](https://www.youtube.com/watch?v=UqEwdttDtZE&t=2260s). This is a neat little board with a fun game that looks useful for beginners to learn digital electronics. The provided schematic had a lot of bugs and was very incorrect. 

I spent some time reverse engineering it from screenshots of the YouTube video, and the result is this board.

![Photo](/Latest/DigiKit_Tennis_Photo.png)

## Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/DigiKit_Tennis_Gerber_PCBWay.zip) and [JLCPCB](/Latest/DigiKit_Tennis_Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/DigiKit_Tennis_BOM.csv) and [PDF](/Latest/DigiKit_Tennis_BOM.pdf) formats.
- The [full schematics](/Latest/DigiKit_Tennis_Schematics.pdf) of the board.

## How to Play

This is a simple game of Pong where the lights in the center of the board are used to indicate the path of the "ball." The goal of the game is to hit the ball back to the other player. When the player on the receiving end misses the ball, a point is given to the one sending it. The counting needs to be done independently and is not done on the board.

### How to set it up?

1. The first option to set is the toggle switch, which defines the speed of the ball. It should remain the same for the duration of the game.
2. Next, select who should serve the first ball. Switch the "Serve" slide switch to the side of the player who should serve. Then, press any "Reset" button. If the green light is not on the correct side of the person serving, switch it by pressing the "Shot" button from the other side. This will toggle the light.

### Play

When everything is set up, the serving player should press the "Shot" button on their side. (A red light and a green light should be lit on the same side!) As soon as "Shot" is pressed, a simulated "ball" is animated across the lights in the center. When the last light is reached, the other player needs to return it by pressing "Shot" in time on their side.

## Implementation

The replica has been implemented using KiCAD 8. The KiCAD project files are included in this repository.

![Replica Front](/Latest/DigiKit_Tennis_3D_Front.png)
![Replica Back](/Latest/DigiKit_Tennis_3D_Back.png)

## Bill of Materials (BOM)

Below is a list of materials needed to assemble the PCB.

![Board](/Latest/DigiKit_Tennis_Blank.png)

| Reference               | Qty | Description        | Footprint                                                      | Datasheet                           |
| ----------------------- | --- | ------------------ | -------------------------------------------------------------- | ----------------------------------- |
| C1,C4                   | 2   | 2nF                | Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm                     |                                     |
| C2,C3                   | 2   | 33uF               | Capacitor_THT:CP_Radial_D5.0mm_P2.00mm                         |                                     |
| C5,C6,C7,C8,C9,C10      | 6   | 0.1uF              | Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm                     |                                     |
| D1,D10                  | 2   | Green              | LED_THT:LED_D5.0mm                                             |                                     |
| D2,D3,D4,D5,D6,D7,D8,D9 | 8   | Red                | LED_THT:LED_D5.0mm                                             |                                     |
| J1                      | 1   | Barrel_Jack_Switch | Connector_BarrelJack:BarrelJack_Horizontal                     |                                     |
| R1,R2,RN1               | 2   | 150                | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal |                                     |
| RN1                     | 1   | 150                | 8 Resistors; 9 pins                                            |                                     |
| R3,R4                   | 2   | 1k                 | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal |                                     |
| R5                      | 1   | 4.7k               | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal |                                     |
| SW1                     | 1   | Player A           | RetroStackLibrary:SW_SPST_Push                                 |                                     |
| SW2                     | 1   | Reset A            | RetroStackLibrary:SW_SPST_Push                                 |                                     |
| SW3                     | 1   | Serve              | RetroStackLibrary:SW_DPDT_Slide_RightAngle                     |                                     |
| SW4                     | 1   | Speed              | RetroStackLibrary:SW_SPDT_Toggle                               |                                     |
| SW5                     | 1   | Reset B            | RetroStackLibrary:SW_SPST_Push                                 |                                     |
| SW6                     | 1   | Player B           | RetroStackLibrary:SW_SPST_Push                                 |                                     |
| U1,U3,U4                | 3   | 74LS00             | Package_DIP:DIP-14_W7.62mm                                     | http://www.ti.com/lit/gpn/sn74ls00  |
| U2                      | 1   | 74LS10             | Package_DIP:DIP-14_W7.62mm                                     | http://www.ti.com/lit/gpn/sn74LS10  |
| U5,U6                   | 2   | 74LS194            | Package_DIP:DIP-16_W7.62mm                                     | http://www.ti.com/lit/gpn/sn74LS194 |

## RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. BitStack is a sub-project of RetroStack, focusing on education in digital electronics. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
