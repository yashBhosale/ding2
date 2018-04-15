## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/yashBhosale/ding2/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block


##Entry 4
Now that we've got movement for Elise, we can start working on other mechanics. We're going to start off with a ranged attack,
because I feel like we can get away with that not really having an animation for Elise. There's a sprite of a fireball which is 
comically oversized, but it also has exploding animations, so I'm going to use that to test our projectile. It's basically just
a sprite with a trigger attatched to it. That way when it collides with anything, it'll be able to access its damage function as well
as run the animation for an explosion. Something really convenient that I found out is that Unity's animation engine allows for 
an object to call a function specifically during a specified animation. That way, right at the end of the explosion animation, 
we can call for the bullet to de-instantiate itself.

 


##Entry 3
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



##Entry 2
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





##Entry 1 (Jan 31)
So, this is our first entry for the Devlog of Elise: A warriors quest (working title.) We spent a lot of time 
thinking about what kind of game we wanted to make, and of course we wanted to make a game that we’d actually 
enjoy playing. I recently played Hyper Light Drifter and have a fair amount of hours in Teleglitch, so I had 
the idea of making a top-down 2D video game in the style of the old Zeldas. We decided that our protagonist 
should be a girl, basically because link has never been a girl.

I'm thinking about making the sprites myself, because I enjoy drawing. I suppose whether or not I do that will depend heavily on
whether or not I actually ever get the time to do that. I have also never drawn isometric characters, so I don't
really know how to go about doing that. Our backup plan is to go take sprites from old games like Zelda: Link to the Past and
just repurpos them for our own needs.

When Matt and I were working on a previous project, he’d seen a tutorial to create a script that allows the
game to instantiate objects in specific areas in world-space based on the RGBA values in a PNG file. That
seems like it’ll be really useful for us, so Matt is planning on doing that soon.














# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/yashBhosale/ding2/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
