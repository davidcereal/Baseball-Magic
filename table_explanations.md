# Table Explantions
### Explanation of some unintuitive fields in our tables

## atbat
**`num`** - The nth batter-pitcher matchup of the game.

**`start_tfs_zulu`** - The time of the at-bat(?). 

**`event2`, `event3`, `event4`** - Any additional events on top of `event` (If an error was comitted on the play, for example).

## pitch
**id** - a unique identification number per pitch within a game. The numbers increment by one for each pitch but are not consecutive between at bats.

**type** - a one-letter abbreviation for the result of the pitch: B, ball; S, strike (including fouls); X, in play.

**sz_top** - the distance in feet from the ground to the top of the current batter’s rulebook strike zone as measured from the video by the PITCHf/x operator. The operator sets a line at the batter’s belt as he settles into the hitting position, and the PITCHf/x software adds four inches up for the top of the zone.

**sz_bot** - the distance in feet from the ground to the bottom of the current batter’s rulebook strike zone. The PITCHf/x operator sets a line at the hollow of the knee for the bottom of the zone.

**pfx_x** - the horizontal movement, in inches, of the pitch between the release point and home plate, as compared to a theoretical pitch thrown at the same speed with no spin-induced movement. This parameter is measured at y=40 feet regardless of the y0 value.

**pfx_z** - the vertical movement, in inches, of the pitch between the release point and home plate, as compared to a theoretical pitch thrown at the same speed with no spin-induced movement. This parameter is measured at y=40 feet regardless of the y0 value.

**px** - the left/right distance, in feet, of the pitch from the middle of the plate as it crossed home plate. The PITCHf/x coordinate system is oriented to the catcher’s/umpire’s perspective, with distances to the right being positive and to the left being negative.

**pz** - the height of the pitch in feet as it crossed the front of home plate.

**x0** - the left/right distance, in feet, of the pitch, measured at the initial point.

**y0** - the distance in feet from home plate where the PITCHf/x system is set to measure the initial parameters. This parameter has been variously set at 40, 50, or 55 feet (and in a few instances 45 feet) from the plate at different times throughout the 2007 season as Sportvision experiments with optimal settings for the PITCHf/x measurements. Sportvision settled on 50 feet in the second half of 2007, and this value of y0=50 feet has been used since. Changes in this parameter impact the values of all other parameters measured at the release point, such as start_speed.

**z0** - the height, in feet, of the pitch, measured at the initial point.

**vx0, vy0, vz0** - the velocity of the pitch, in feet per second, in three dimensions, measured at the initial point.

**ax, ay, az** - the acceleration of the pitch, in feet per second per second, in three dimensions, measured at the initial point.

**break_y** - the distance in feet from home plate to the point in the pitch trajectory where the pitch achieved its greatest deviation from the straight line path between the release point and the front of home plate.
break_angle: the angle, in degrees, from vertical to the straight line path from the release point to where the pitch crossed the front of home plate, as seen from the catcher’s/umpire’s perspective.

**break_length** - the measurement of the greatest distance, in inches, between the trajectory of the pitch at any point between the release point and the front of home plate, and the straight line path from the release point and the front of home plate, per the MLB Gameday team. John Walsh’s article “In Search of the Sinker” has a good illustration of this parameter.

**break_angle** - the angle, in degrees, from vertical to the straight line path from the release point to where the pitch crossed the front of home plate, as seen from the catcher’s/umpire’s perspective.

**sv_id** - a date/time stamp of when the PITCHf/x tracking system first detected the pitch in the air, it is in the format YYMMDD_hhmmss.

**pitch_type** - the most probable pitch type according to a neural net classification algorithm developed by Ross Paul of MLBAM.

**type_confidence** - the value of the weight at the classification algorithm’s output node corresponding to the most probable pitch type, this value is multiplied by a factor of 1.5 if the pitch is known by MLBAM to be part of the pitcher’s repertoire.
