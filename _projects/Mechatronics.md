---
layout: project
title: Mechatronics 
description: Circuit Diagrams and Debugging, Arduinos, Mechanical and Electrical engineering
technologies: [C++, circuit building]
image: /assets/images/robot.png
---

Our robot was designed around a simple cube collection mechanism consisting of two arms connected to servo motors. These servo motors allowed the arms to be deployed at the start of the match and to lift up and down during turns. The arms were initially held upwards before the match began to ensure the robot fit within the required 8x8in starting constraint, and then were moved 90° downward to fit within the 12in diameter size limit when the match began. We mounted a color sensor to the bottom of the robot and placed two QTI sensors at the end of each arm.

<!-- robot pic -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/robot.png' | relative_url }}" alt="Robot image">
  <figcaption>Completed Robot</figcaption>
</figure>

The workflow of the robot began with it moving forward while simultaneously moving the arms down. When the color sensor detected a color change, which indicated that the robot had reached the center of the board, the robot turned 90° to the right. During each turn, the arm on the same side as the turning direction lifted up to allow the robot to more effectively scoop and collect additional cubes. Once the turn was completed the lifted arm would lower back down. After the initial color change detection, the robot was programmed to move forward until it hit the black border, which was detected by the QTI sensors. It was also programmed to no longer respond to changes in the board’s color. If the robot hit the black border, it backed away slightly and then turned 180° in the direction opposite to the arm that detected the border. This strategy allowed the robot to continue moving back and forth along the middle of the playing field to maximize cube collection. It also ensured that if the robot was bumped during play, it would not fall off the board and would still manage to collect cubes.

