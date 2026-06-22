# Thermal Imaging Camera
Normal humans can only see visible light. Imagine being able to see in an entirely new dimension - heat! With the power of a Raspberry Pi 4 and an MLX90640-D55 thermal camera, you can explore the new world of thermal vision and see beyond the ordinary. The thermal camera captures raw data which is then processed by the Raspberry and displayed as a thermogram.




| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Alexandru T | Cambridge High School | Mechanical Engineering | Incoming Junior

<!--**Replace the BlueStamp logo below with an image of yourself and your completed project.

![Headstone Image](logo.svg) -->
  
# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/yVGZo8T66iE?si=1QpRDz8t5H55B18i" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- For the first milestone, I decided to set up the Raspberry Pi and connect it to the thermal camera to begin receiving text-only temperature readings.
- So far, the project includes a Raspberry Pi 4B, an MLX90640-D55 thermal camera, and python code. The camera scans the surrounding area to gather thermal data, then sends it to the Raspberry Pi, which uses the python code to interpret the data and display it in text format on the command terminal. The Raspberry Pi acts as the brain of the project, taking data from the camera, interpreting the data, sending the data elsewhere, as well as distributing power to all components. By itself, the thermal camera has no ability to process the thermal readings or display any data. The Raspberry Pi is therefore essential to be able to use the data, and the python code is the crucial element informing the Raspberry Pi on how to take raw thermal readings and use mathematical algorithms to translate thermal data into temperatures.
## Technical Progress
### Setting up the Raspberry Pi
- I first set up the Raspberry Pi, using the Raspberry Pi Imager to install the operating system onto a micro SD card from my computer. I then took the micro SD and plugged it into the Raspberry Pi, enabling it to have an operating system. After this, updates and upgrades were installed to ensure that the Pi was up to date, along with specific packages such as adafruit-blinka. These packages were necessary to ensure that python could run on the Raspberry Pi.
### Connecting the Camera
- Next, I had to connect the camera to the Raspberry Pi, with each of the four wires needing to connect to specific pins. The camera uses a 3V power supply, corresponding to pin 1 on the Pi. The camera also has two communication wires, SDA (Serial Data) and SCL (Serial Clock). SDA transferrs the actual information, while SCL controls the speed of communication and the rate at which information is exchanged between the Pi and the camera.
### Coding
- The final step of my first milestone was using python code to allow the Raspberry Pi to properly process the information given to it by the thermal camera. Although the Pi acts as the brain of the operation, it does not know how to actually use the information until the python code tells it how to interpret the raw thermal data. When the code is run, the camera records data and sends it to the Raspberry Pi. The Pi processes the data and turns it into temperatures which are then displayed on the command terminal.
## Challenges
- A first major obstacle I came across was installing the necessary python packages when setting up the Raspberry Pi. The Raspberry Pi uses built-in python in its operating system to control certain elements. Installing python packages acts as a danger to this operating system, potentially overwriting or damaging core files needed for the Raspberry Pi to function. As such, the Pi protects itself from these installations, blocking them from occuring. Therefore, I needed to create and activate a python virtual environment within the Raspberry Pi, which allowed me to install essential packages inside of a protected environment where the operating system could not be damaged.
- Another challenge occured when plugging in the camera to the Raspberry Pi. The camera specifically needs a 3V power source, and anything above that could cause damage. Because the Raspberry Pi has both 3V and 5V pins, I needed to be very careful when plugging in the camera, or I could have caused permanent damage.
## Future Plans
- Now that the camera is connected and the Raspberry Pi is fully set up, I need to create a visual representation of the thermal data. For this, I will need to find a display, such as a monitor, and I will need python code. Instead of converting data into text-only temperatures, I will need the code to convert the thermal data into a constantly updating graphic representing surrounding temperatures with colors. After this is completed, I plan to begin working on modifications to my project, which could include additional electronic parts and protective casings for components.




# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Technical Progress
### Coding
- To progress from text-only readings to an actual image, I had to replace the text-only code with a new Python script that converts the raw thermal readings into a thermogram. When run, the thermal camera now displays an image on a monitor connected to the Raspberry Pi. However, the resulting image is low-quality and provides a very limited and pixelated view. To solve this, I added another Python script that interpolated the original 24x32 thermal display, resulting in a smoother and enhanced image. Interpolation estimates unknown data values between known values. As such, the image now contains "artificial" pixels interspersed between the original pixels. These new pixels are approximations of the thermal values between the pixels of the original 24x32 display, creating both a higher resolution image and a smoother display. 
### Modifications
- While using the camera, I had to be very careful, as the Raspberry Pi was exposed and was very easy to damage. It was also becoming difficult to touch, as my camera detected that the Pi was reaching temperatures of up to 42 degrees Celsius. Although this is not dangerous for the Raspberry Pi itself, it made the camera hard to handle. Therefore, I decided to add copper heatsinks and a fan. The heatsinks are attached to the main chips of the Pi, using the conductive property of copper to draw heat away from the chips and into the heatsink. The fan then pumps air across the surface of the heatsink, dispersing the heat. I also added a protective case to protect the Raspberry Pi, where the lid of the case also holds the fan in place. The protective case makes the cooling system even more essential, as a lone Raspberry Pi in a closed low-ventilation plastic case would easily overheat.

## Challenges
- When I first connected my camera to the Raspberry Pi and ran the Python script, an image showed up, but it was a single frozen frame displaying incorrect temperature values. After checking the wire connections and attempting to edit the code, I came to the conclusion that the sensor was corrupted and the camera could not be used to obtain thermal images. I had to then use a replacement camera in order for my project to work. The corruption could have been caused by a small static shock from my hands or the environment, so I decided to be very careful with the replacement camera. I researched and found out that the MLX90640 thermal camera comes inside of an anti-static bag. When not using the camera, I kept the camera inside of the bag to avoid any electric discharge. When I had to use the camera, I carefully removed it from the bag only after touching a grounded metal object to discharge any static electricity from my body.
- The replacement camera was in perfect condition, but while I was adding my fan, the ground wire was damaged. The fan had a 5V wire and a ground wire, both encased within a plastic connector. As such, they had to be placed adjacent to each other on the Raspberry Pi's 40-pin layout. The only possible orientation for this was to place the plastic connector at pins 4 and 6, which was next to the wires for the thermal camera. Because the plastic casing for the fan wires was fairly large, placing it next to the camera wires led to bending and damage, even if the damage was not visible. Combined with the strained position caused by the lid of the case, the ground wire was damaged and stopped working. I remembered that the old thermal camera had functional wires, and just the camera itself was damaged. I chose to swap the wires from the new camera with those from the old camera, resulting in a functioning camera with a fully functional set of wires. Furthermore, to add the fan back, I needed to find a way to place it in a different position. I realized that I could use male to female jumper wires to be able to put the 5V wire and the ground wire in different positions on the Raspberry Pi. These wires were also smaller, so they would not cause damage to surrounding connections. This allowed me to operate both the camera and the fan at the same time.
- The orientation of the lid on top of the wires also caused damage, as the lid of the protective case was causing the wires to bend out of shape. To solve this, I cut a small hole in the lid to allow the wires for the camera to pass through. This allowed the wires to sit in their natural orientation without deformation.

## Future Plans
- Currently, the thermal camera can display an image of the surrounding temperatures. However, it must remain plugged into an outlet in the wall and the display relies on a stationary computer monitor. This makes the camera extremely limited, as it cannot be moved. I plan to use a 7-inch display and a portable battery to make the thermal camera portable. This way, it can be carried around to any location for as long as the battery lasts.
 

<!--# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE -->

# Schematics 
![Model of the Completed Thermal Camera](Fritzing Model for Github.png)

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials


| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| MLX90640-D55 Thermal Imaging Camera | Capturing thermal radiation data for later processing | $66.30 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/MLX90640-D55-Camera-Compatible-Firefighting-Maintenance/dp/B0FQHVSX91/ref=sr_1_1?dib=eyJ2IjoiMSJ9.jtNmEUR-VLfwR8hJ1WjkNVY3VPySrW2bIGnH2NSUyn6m8nhTRFDHPY6YVo4mLBkRc74tI_rWtxQjdTZxwcbizjL2RYnrAAuZNBwUwlVd7YqlmMfvj4r_R8B7PvDr6qpBePyuLE01dsYIQT7V5eSGT_kvE9efR4pfdsueW-OmAfiFNDadrS9jiiQyXJR-fLYbTfqnpk_jbZ-VEeOFLNXqqV9ip1bo3zLFXjRpoYvtOlA.CINsSo8TMzkVIALr3qcIUSqzT1uVdxTs3g-1aQQATSU&dib_tag=se&keywords=mlx90640-d55+thermal+imaging+camera%2C+32x34+IR+array&qid=1781014765&sr=8-1)"> Link </a> |
| USB to Micro SD Card Adapter | Adapting a Micro SD Card to USB for use on a computer | $8.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/uni-Adapter-Supports-Compatible-MacBook/dp/B081VHSB2V/ref=sr_1_1_sspa?crid=4HMRF3ZXALEF&dib=eyJ2IjoiMSJ9.3vArOtBXB8aXRuKS3rF7i1W8da1mEJZ8FAyQegKc6Qv-nrgdHMgbAkmIkR88XQLEdRpD246tyGdE5FEj8RrFrqYi-7b8nIAgkHXmmnUqpGaUyuZhtWDp68ATDQwplNNrcK6h5DnuiBsgcLkHNhQpFTHu-9pgERSckNd66AyX1iG3Svd3cLGtrqwAUO78rHqmqVnRfLaZH-aZnLJgDjyg3RbDGqByar3kimNjPZCUdiS8dudgH8ajmyD8RSnFddEd7-72pyILS-f37yzbQZ8IzeDlUyC7Yf32Y0R3ZMZqw4k.czrbZM6nHxzsWFQhOnxFrCl8msMVR4X7z-G3IH3l9DI&dib_tag=se&keywords=uni%2Bsd%2Bcard%2Breader%2C%2Bhigh%2Bspeed%2Busb%2Bc%2Bto%2Bmicro%2Bsd&nsdOptOutParam=true&qid=1781014814&s=electronics&sprefix=uni%2Bsd%2Bcard%2Breader%2C%2Bhigh%2Bspeed%2Busb%2Bc%2Bto%2Bmicro%2Bsd%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)"> Link </a> |
| Raspberry Pi 4 4GB Starter Kit | Converting raw infrared radiation data to useable thermal readings and creating thermal images, as well as provifing useful additions to the Raspberry Pi | $147.79 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/RasTech-Raspberry-Starter-Heatsink-Screwdriver/dp/B0C8LV6VNZ/ref=sr_1_1?crid=H858RUP1GVGJ&dib=eyJ2IjoiMSJ9.2HMtfI55o-jCAhg3n24VqcHqd28JgVwq_KHhbgkkY4I8SmClwzS1SWxigj4MRUP1vR7FwjO5d5VZvEkDfo3MCMX-fjZNvdKmAOmox1zTMs5O6UvQh4M5ciMj7XHkvVA4MbxLJNFpSMIyTYQUBuwe82-79JUo8-VHxRusRwNJktFidiGQROEb6xRUQBoaxJiFmMiIzHzByFXxRstYmg48ANKjXpPmnyBaUhu-Kb4VyJY.t1kDiKpg8nlTriBtHmPPfHmazEwSEM0OAZk--b7xDnE&dib_tag=se&keywords=raspberry%2Bpi%2B4%2B4gb%2Bstarter%2Bkit%2Bwith%2Bpi%2B4%2B4gb%2Bboard&nsdOptOutParam=true&qid=1781014855&sprefix=raspberry%2Bpi%2B4%2B4gb%2Bstarter%2Bkit%2Bwith%2Bpi%2B4%2B4gb%2Bboar%2Caps%2C128&sr=8-1&th=1)"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources
- [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
- [Raspberry Pi SSH Guide](https://www.onlogic.com/uk/blog/how-to-ssh-into-raspberry-pi/)
- [Raspberry Pi Setup](https://www.tme.com/in/en/news/library-articles/diy/page/64698/a-simple-guide-to-setting-up-a-raspberry-pi/)
- [Raspberry Pi Virtual Environment For Python](https://www.raspberrypi.com/news/using-python-with-virtual-environments-the-magpi-148/)
- [3D Print Models](https://www.printables.com/tag/bitbeam)
- [Fritzing](https://fritzing.org/)
