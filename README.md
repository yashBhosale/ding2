## Welcome to the Devlog for Elise: A Warrior's Quest!


## Entry 6 (April 11)
Elise has pushback now We fixed one glitch with the basic enemy's movement but it's still doing things 
that we don't want it to We moved all of the movement code for Elise so that it goes through the physics 
engine, so that she can't just run through walls and stuff.

A while back, matt implemented controller functionality so that we can move around with the controller. This 
makes playtesting a lot more fun for us. He also tweaked some of the UI elements so that they look better.
We're also slowly adding clooiders to all of the things that actually need them, so that the world actually
acts like it's supposed to. At some point we'd like to have it so that all of the grass and dirt is 
actually just one large map, but that'll probably be one of the last things we ever do. 

## Entry 5 (March 28)
We've been pretty busy since the last entry. We have a working bullet for Elise. I'm working on creating new, 
different enemies- one's going to be a ranged enemy, and we're not sure if the other enemy is going to be 
ranged or not. I've also created a better UI that shows off the health- we now have a heart system, so that
when the player gets hurt they lose a heart. 

The chest now also has a randomized passive pick up in it, out of 3. This is determined when the chest is
instantiated- The player either gets a higher base speed, longer dash distance, or lower dash cooldown. 
We're probably going to make it so that the pickups only last for a certain amount of time, but for now
they last for the entirety of the game. If the player already has a pickup, but they open a chest, the
previous effect is eliminated and the player only has the effects of the current pickup.

Matt implemented the board system so that now when I move into a specific "exit" point on one map, the 
level loader will load me into a spot in the next (or previous, or whatever you want to call it) area. 
He also set it up so that Elise has the ability to dash. However, the dash is pretty clunky as it stands-
We haven't set the dash code to work with the physics engine; rather, we're making it so that it translates the 
sprite a set amount based on the current movement direction. This gets us into trouble in the case that 
Elise translates into some area that she isn't supposed to because she bypassed some wall that was too thin
to catch her. we will need to fix that. 

## Entry 4 (march 14)
Now that we've got movement for Elise, we can start working on other mechanics. We're going to start off with a ranged attack,
because I feel like we can get away with that not really having an animation for Elise. There's a sprite of a fireball which is 
comically oversized, but it also has exploding animations, so I'm going to use that to test our projectile. It's basically just
a sprite with a trigger attatched to it. That way when it collides with anything, it'll be able to access its damage function as well
as run the animation for an explosion. Something really convenient that I found out is that Unity's animation engine allows for 
an object to call a function specifically during a specified animation. That way, right at the end of the explosion animation, 
we can call for the bullet to de-instantiate itself.

Matt has gotten the camera to move in such a way that, instead of moving every time Elise moves, it only moves if Elise pushes the 
boundaries of an invisible box. This is going to be really useful for when we actually implement the dashing mechanic, because it'll
be a lot less jerky than it would've been for a hard-parented camera. He's also made it so that when we go up to the chest and press
an interaction button, the chest actually opens. We haven't really put anything inside the chest, but when we do I'm sure it'll be 
epic. 

Now that we've gotten the camera control and basic health system, we want to start making other levels besides 
the demo level. Thanks to Matt's tool, all I have to do is create a PNG and stick it in a specific folder, and
see how it works out. We can iterate really quickly thanks to this tool. Each map will be in a different scene,
and there will probably be specific spawn- and exit- points leading in and out of each scene. They're not really
levels, but on our side they will be kind of like levels.


## Entry 3 (February 28)
We just added Unity Collab to our project! It's incredibly useful- until we moved over, we were basically working
on one computer. That, as is probably obvious, is rather terrible for productivity. Now we have the productivity
of two different people that are actually working on two different computers!

I've been having some weird problems with the map generator. The map generator itself isn't a problem, but the
problem that we're now running into is that some objects that are instantiated next to other objects are either
being covered by or covering objects in such a way that we don't want them to. Trees are one of the biggest culprits
I think that I'll be able to work around this by tying an object's z axis to its y axis. It'll make sense in most 
if not all cases, because in an isometric world, "down" is considered "closer to the camera"

Matt has implemented a health system- The character has a health value, and there is a counter in the corner of 
the screen that allows us to see how much health the character has. We created a basic enemy to test it out- it just
jumps out at you after following you for a bit. In the beginning, when we got the first iteration down, it would take
a lot more health than it was supposed to. However, all Matt had to do was add some debouce logic to make sure it only
took a specific amount of health per any one 'hit'.



## Entry 2 (February 14)
Originally I’d planned to do the sprites myself, but then I realized I don’t really have the time for that. 
Instead, the first thing we did in the development process is that I took sprite sheets from Zelda: a Link to 
the Past, and cut them out for use as our own sprites. This has given us a little bit of a problem, in that 
because the sprite for our main character is a tertiary character she doesn’t really have any animation 
besides walking around. However, we’re going to have to make do with this. There are a pretty decent amount of
enemy sprites in the game files, though, so that's really nice.

I've created a gameObject for our main character and I'm working on making it functional. I've recently created and
set up the animations, so now all I have to do is write the code that allows it to move and do other things, like dash.


Matt created his script to instantiate objects based on a png. Using it is dead simple- all I have to do is
paint a PNG with specific RGBA values and the objects that are associated with those values will be instantiated
in specific spots. We've created a rudimentary map based on that.

He's also in charge of the camera. Right now the camera's transform is parented to the transform of Elise. However,
once I'm finished we want to make a script that will soft-follow Elise (for lack of a better phrase), rather than
being stuck exactly onto Elise's transform. 


## Entry 1 (Jan 31)
So, this is our first entry for the Devlog of Elise: A warriors quest (working title.) We spent a lot of time 
thinking about what kind of game we wanted to make, and of course we wanted to make a game that we’d actually 
enjoy playing. I recently played Hyper Light Drifter and have a fair amount of hours in Teleglitch, so I had 
the idea of making a top-down 2D video game in the style of the old Zeldas. We decided that our protagonist 
should be a girl, basically because link has never been a girl.

I'm thinking about making the sprites myself, because I enjoy drawing. I suppose whether or not I do that will depend heavily on
whether or not I actually ever get the time to do that. I have also never drawn isometric characters, so I don't
really know how to go about doing that. Our backup plan is to go take sprites from old games like Zelda: Link to the Past and
just repurposE them for our own needs.

When Matt and I were working on a previous project, he’d seen a tutorial to create a script that allows the
game to instantiate objects in specific areas in world-space based on the RGBA values in a PNG file. That
seems like it’ll be really useful for us, so Matt is planning on doing that soon.
