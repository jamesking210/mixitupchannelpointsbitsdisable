Goal: on twitch, set a channel point redemption to trigger a 15 min timer or OBS scene for 15 mins, if a total of 500 bits are donated to channel during the channel point redemption timer, it will stop the source (timer)

Prerequsite, have Mix It Up bot installed
https://mixitupapp.com/

Guide: $kittys are bits, $kittens are bit totals in counter, $cats is the channel point timer either 0 or 1

Import the following
*note when i was importing into the selected areas i had to click all files in the drop down to the left

Action Group
1. actiongroup_addbitsup (adds bits when added to channel via a counter "kittens")
2. actiongroup_kittensreset (resets bit counter "kittys" force to 0)
3. actiongroup_catsread (reads if the channel point timer is active or not, 0 for off or 1 for on)
4. actiongroup_catsreset (resets channel point redeem "cats" force to 0)
5. actiongroup_readkittens (reads kittens in counter)


After you import make sure you edit everyting to your system, the File (Read & Write) area, replace jimmyk with your USERNAME on your windows PC (you can find by goung to c:\users)
You will probably need to make the folder navigate to C:\Users\USERNAME\AppData\Local\MixItUp and create a Counters folder. when you run action it should make the .txt file
add a name to the action group then save and test! .txt files should come back with 0.

Channel Points
1. channelpoints_trigger_15min (resets the kittens counter, activates timer source, waits 15 mins, resets kittens counter, turns off timer source)

After you import, change USERNAME in File (Read & Write) just like above.
under command, run command, command type select action command, kittensreset
check everything else including the wait time, change to what you want it to be, my case is 15 mins, and OBS source name, i had to relink my OBS too.

when trouble shooting, I ran into the channel point not working, i closed the program and opened and it worked!

Commands
1. command_reset (!reset to reset kittens and cats)

name & chat trigger (reset)
under command 1, command type action group, command kittensreset
under command 2, command type action group, command catsreset
you can also add an OBS source visability here for testing too
This command is mostly for troubleshooting or mod control

Events (for bits)
1. events_bits (when bits are given is the cats(channel point timer) active? 1 yes, 0 no
if yes 1, count the bits with the counter and add them up to total kittens, chat goal,
when 500 kittens reached trigger chat command and turn off timer source
if no 0, do nothing

This is where you marry everything up and make it work when the timer is going so be careful to make sure you do this right, trial and error. test test test

command: command type action command, addbitsup
edit those two File (read &write) with your USERNAME from above again
two conditionals at the bottom, edit them to your liking, 1st one is for bits under 499, second one is bits over >=500, make sure you turn off that timer source because thats the goal of this project.
also, the two conditionals at the bottom is how you can change the goal to meet your stream. a big streamer wouldnt use 500 bits, they would use something like >=2000

Have Fun Streaming!
any questions, whisper me at @JimboSliceChicago
if you would like to see it in action, it is made for my DJ buddy @ChuckTheDJCA the redemption is "Shut Up 15 Mins" - i can activate it for you if im in there ;)




