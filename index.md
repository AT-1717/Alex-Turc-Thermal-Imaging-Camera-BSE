# Thermal Imaging Camera
Normal humans can only see visible light. Imagine being able to see in an entirely new dimension - heat! With the power of a Raspberry Pi 4 and an MLX90640-D55 thermal camera, you can explore the new world of thermal vision and see beyond the ordinary. The thermal camera captures raw data which is then processed by the Raspberry and displayed as a thermogram.




| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Alexandru T | Cambridge High School | Mechanical Engineering | Incoming Junior

**Replace the BlueStamp logo below with an image of yourself and your completed project.

![Headstone Image](logo.svg)
  
# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your first milestone, describe what your project is and how you plan to build it. You can include:
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project
- For the first milestone, I decided to set up the Raspberry Pi and connect it to the thermal camera to begin receiving text-only temperature readings.
- So far, the project includes a Raspberry Pi 4B, an MLX90640-D55 thermal camera, and python code. The camera scans the surrounding area to gather thermal data, then sending it to the Raspberry Pi, which uses the python code to interpret the data and display it in text format on the command terminal. The Raspberry Pi acts as the brain of the project, taking data from the camera, interpreting the data, sending the data elsewhere, as well as distributing power to all components. By itself, the thermal camera has no ability to process the thermal readings or display any data. The Raspberry Pi is therefore essential to be able to use the data, and the python code is the crucial element informing the Raspberry Pi on how to take raw thermal readings and use mathematical algorithms to translate thermal data into temperatures.
## Technical Progress
### Setting up the Raspberry Pi
- I first set up the Raspberry Pi, using the Raspberry Pi Imager to install the operating system onto a micro SD card from my computer. I then took the micro SD and plugged it into the Raspberry Pi, enabling it to have an operating system. After this, updates and upgrades were installed to ensure that the Pi was up to date, along with specific packages such as adafruit-blinka. These packages were necessary to ensure that python could run on the Raspberry Pi.
### Connecting the Camera
- Next, I had to connect the camera to the Raspberry Pi, with each of the four wires needing to connect to specific pins. The camera uses a 3V power supply, corresponding to pin 1 on the Pi. The camera also has two communication wires, SDA (Serial Data) and SCL (Serial Clock). SDA transferrs the actual information, while SCL controls the speed of communication and the rate at which information is exchanged between the Pi and the camera.
### Coding
- The final step of my first mileston was using python code to allow the Raspberry Pi to properly process the information given to it by the thermal camera. Although the Pi acts as the brain of the operation, it does not know how to actually use the information until the python code tells it how to interpret the raw thermal data. When the code is run, the camera records data and sends it to the Raspberry Pi. The Pi processes the data and turns it into temperatures which are then displayed on the command terminal.




# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

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
| Raspberry Pi 4 4GB Starter Kit | Converting raw infrared radiation data to useable thermal readings and creating thermal images | $147.79 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/RasTech-Raspberry-Starter-Heatsink-Screwdriver/dp/B0C8LV6VNZ/ref=sr_1_1?crid=H858RUP1GVGJ&dib=eyJ2IjoiMSJ9.2HMtfI55o-jCAhg3n24VqcHqd28JgVwq_KHhbgkkY4I8SmClwzS1SWxigj4MRUP1vR7FwjO5d5VZvEkDfo3MCMX-fjZNvdKmAOmox1zTMs5O6UvQh4M5ciMj7XHkvVA4MbxLJNFpSMIyTYQUBuwe82-79JUo8-VHxRusRwNJktFidiGQROEb6xRUQBoaxJiFmMiIzHzByFXxRstYmg48ANKjXpPmnyBaUhu-Kb4VyJY.t1kDiKpg8nlTriBtHmPPfHmazEwSEM0OAZk--b7xDnE&dib_tag=se&keywords=raspberry%2Bpi%2B4%2B4gb%2Bstarter%2Bkit%2Bwith%2Bpi%2B4%2B4gb%2Bboard&nsdOptOutParam=true&qid=1781014855&sprefix=raspberry%2Bpi%2B4%2B4gb%2Bstarter%2Bkit%2Bwith%2Bpi%2B4%2B4gb%2Bboar%2Caps%2C128&sr=8-1&th=1)"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources
- [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
- [Raspberry Pi SSH Guide](https://www.onlogic.com/uk/blog/how-to-ssh-into-raspberry-pi/)
- [Raspberry Pi Setup](https://www.tme.com/in/en/news/library-articles/diy/page/64698/a-simple-guide-to-setting-up-a-raspberry-pi/)
- [Raspberry Pi Virtual Environment For Python](https://www.raspberrypi.com/news/using-python-with-virtual-environments-the-magpi-148/)
- [3D Print Models](https://www.printables.com/tag/bitbeam)
