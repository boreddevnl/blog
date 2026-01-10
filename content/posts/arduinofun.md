+++
date = '2026-01-10T17:12:37+01:00'
draft = false
title = 'Arduino Fun'
summary = "A computer science Arduino Project. Read on to see how everything suddenly went wrong!"
+++
*(Sponsored)*

Last year, I had a computer science assignment where I needed to create an Arduino project with a partner. After brainstorming for a while, we came up with the idea of making a turret. (I know it sounds a little silly, but we thought it would be a fun challenge!)

Originally, we planned to control it using my buddy's PS3 controller. However, we quickly realized we would have to splice the cable apart to get it working, which was too messy. instead, we settled on using my laptop's webcam. This turned out to be a more difficult task, but it made the project much more interesting.

I started working on the code with the following structure:

```md
/facetrack
-facerec.py
-facetrack.ino
-README.md
-LICENSE
-/models
 -turntable.stl
 -buttonpushersbig.stl
 -ver_pipe_aimer.stl
 -pumpframe.stl
 ```

I wrote a Python script ```facerec.py)``` using cv2 to track a face via the camera. The script sends those coordinates to the Arduino sketch ```(facetrack.ino)```, which converts them into degrees for two servos:
* Vertical
* Horizontal

I tested this at home with some tape on a servo, and saw it properly track my face which was great news!

**The Hardware**

The following week, my buddy designed and 3D printed a turntable ```(turntable.stl)``` with a thread at the bottom for the horizontal servo and a mount on top for the vertical servo.

The week after that, he brought in a water pump and a printed frame ```(pumpframe.stl)``` with slots for two more servos. We designed attachments ```(buttonpushersbig.stl)``` that would mechanically press a button to start the water pump when a face was detected, and press a stop button when the face disappeared from the feed.

**Oh no..**

Unfortunately, when we presented this to our computer science professor, disaster struck. The "button pushers" snapped off after pressing the buttons twice, from the pressure. We had printed them on the school printers using standard PLA. Apparently, the material couldn't handle the torque required to press the buttons. Luckily, we didn't lose any points for the mechanical failure, since i knew this was a manufacturing issue, not an issue with our design, but I knew we could do better. I just wasn't sure how to fix it at the time.

**The Solution** 

A few weeks later, just before winter break, **PCBWay** reached out to me for a collaboration. I was surprised since I'm not a massive influencer, but their timing couldn't have been better.

PCBWay offers strong metal and nylon printing options, which solves the exact problem of brittle PLA breaking under pressure. After discussing the project with them, I sent over the files. I ordered the turntable in white resin and the button pushers in aluminum.

The parts arrived yesterday, and the difference is night and day. I attached them to our contraption, and sure enough, the aluminum pushers fit the servos perfectly and handled the pressure without breaking. They effectively saved my otherwise dead project.

A big shout out to [PCBWay](https://pcbway.com) for sponsoring this post. If you ever have PCB prototyping or advanced 3D printing needs, I highly recommend [PCBWay](https://pcbway.com)
a try!

Have a look at [my GitHub repo](https://github.com/boreddevnl/facetrack) to check this project out!