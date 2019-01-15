# KeyboardRunner

This game was created as a project for my Advanced Software Engineering class at TEI of Krete and it was my first try at programming a game using the [PIXI.JS](http://www.pixijs.com/) library.

Your goal in the game is to write words that appear on the screen as fast as possible. Misstyping is not penalized, the lack of speed is. Clicking `Play` button will always start the last unlocked level. There is a total of 16 levels and the speed of words moving towards you is increasing as you progress through the levels. Once the last level is unlocked, new words are added to every level and their order is shuffled.

Highscores are only local, exit button points towards my website, under [/projects](https://danieldusek.com/projects) route where you can check my other projects.

To try and play the game, visit one of the following links: [MIRROR 1](https://dusekdan.github.io/KeyboardRunner/) | [MIRROR 2](http://projects.nile.teicrete.gr/keyboard_runner) | [MIRROR 3](javascript:alert("Not yet"))

## Screenshots

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/04Playing.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/04Playing_LighBigPyramid_Transition.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/01_Menu.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/01Menu_1stItemSelected.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/01Menu_2ndItemSelected.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/01Menu_3rdItemSelected.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/01Menu_4thItemSelected.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/02LevelSelect.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/03Scoreboard.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/04Playing_Defeat.PNG)

![KeyboardRunner game screenshot](https://raw.githubusercontent.com/dusekdan/100BrowserGames/master/002_KeyboardRunner/screens/04Playing_Victory.PNG)

## Lessons learned

Since I am starting this project mostly to observe my own improvement over time, I will put together few thoughts relevant to the game implementation - what went well, what was done terribly and should be improved next time and what was totally missed in the game.

There is not much that went well about this game. I progressed slowly at the beginning, not understanding exactly how to work with PIXI.JS, but in the end, I got a good grip on it, learned to read its docs, started visiting html5gamedev forum to read answer to my questions that other people have already asked. In the end, it was exactly as everyone was saying - PIXI alone is mostly canvas drawing framework and a lot has to be done to make a game using just that. Overall I am pretty satisfied with how the game *works* (not looks), considering it was the first time trying this. Now let's move on what was not such a success.

### Applying design patterns

In the beginning I did not really considered properly separating the logic from the UI and mixed it up together. This is quite funny because when I normally code something, I do separate the logic properly. Somehow it did not ocurrred to me while working on the game that game programming is no different from other stuff I normally program. I might have been influenced by tutorials I followed, which were always very basic and so no reasonable separation was done.

Finally - if you inspect the code, it is clearly visible that later on, when programming entities that are coming towards the player, I tried to save myself a little bit and created something like views and models, but at that point was fairly late.

### Game design

Every game on which I have ever spent some rather unreasonable time had a game design through through pretty well. I felt motivated to progress further and try harder when I started failing. When I decided to leave the game alone for a while I tended to feel like going back to give it one more try "maybe after I will cool off" or something. Game design is very important and the great game design is a must for the game that should entertain people for hours.

First of my misdeeds on this game was that I based the speed of entities moving towards the player on my own typing skills - and I type quite fast compared to other people. I had people who work with computer pretty much daily telling me they did not manage to beat the level 1 and the game was pretty much unplayable for my little brother.

Other problem, quite frequently mentioned was that the words are often not words, but multiple words put together. That resulted in a lot of typos and lost of typing speed.

### Instructions must be included in the game

Almost no one was able to figure out that they are expected to type the words that appear on screen, without me telling them first. I should have put this information in the game itself, maybe in the first level or in the main menu. It could have been pretty straightforward, just a text "Type what you see on screen to get points" or something like that.

### "Random" background generation

Generating algorithm is pretty dumb and has a lot of hardcoded suggestions from which it then randomly picks. It would certainly benefit from some procedural algorithms which would make it feel more natural. I have no skills in that area, but I believe that it would be beneficial for my future games for me to learn a little bit of it. I do not want to develop the games that will be always the same, I like *some amount* of randomness that surprises me as a player when playing it (the game does not loses its charm for me after the hours I spent programming it).

### Graphic resources and UX

I have no graphic design skills as you could have seen from the screenshots. I did my best to use only material colors to keep the game uniformed, at least in colors, but it was barely enough. The lack of various, nicely prepared graphic resources is noticable and makes the game feel very amateur-ish. At the moment, I am not entirely sure how to fix this situation as currently I have no plans (or means) for hiring someone to make the graphics for me.

There were other things people mentioned: The text should not move, because it makes reading it harder - possibility of moving only the enemy entity and keeping the text in place comes into mind.

No one mentioned it, but I feel it: When pressing keys in improper moment, some frames are dropped. This is due to handlers being implemented as keydown/keypress listeners and that happens asynchronously and interferes with PIXI.JS game loop. I believe that PIXI tries to compensate for the time it took the key press event handler to run and drops the frame or two anytime this happens. It results in the game feeling laggy.

### The Takeaways

Apply design patterns to separate UI and the logic, think through the game design in advance and balance it for the expected audience, learn about procedural generation, put instruction directly into the game, give the game uniform graphic style and feel (material colors are not enough)

## Ideas, Issues, Future Improvements

There are some things that did not make it into the final version of the game (it was good enough for univesity project), these are listed here. Either as issues, or as ideas that could be implemented in the future, should I ever decide continue on *browser version* of the game. I currently do have great plans in progress regarding non-browser version of this game. It is more likely that the desktop only version of the game will be implemented and that this browser game will be abandoned. I have a story and ideas for the browser version and would prefer publishing it on Steam (free).

### Features that would be nice to have

- [ ] Entity death animation is animated (explodes, falls down, not just dissapearing)
- [ ] When heart is removed it blinks on the screen few times
- [ ] When heart is added to the screen it shines once
- [ ] Player stickman actually runs (requires 60 frames animation which makes this big to implement)
- [ ] Player stickman shoots bullets or lasers (easier); it hits when correct letter is typed out, it misses when not
- [ ] When game screens are changed, the transition is smooth
- [ ] Possibility to pause and exit the game at any time

### Ultra nice features to improve the game

- [ ] Created original image assets for enemy entities; enemies spawned in certain height have animated wings
- [ ] Player name after the game is recorded in in-game prompt (style fits in), not by standard JS prompt
- [ ] Large boss at the end of the level with a lot of text to write; spawns smaller entities heading towards the player every once in a while; entities must be defeated before continuing fighting the boss
- [ ] Endless level that will switch between preset difficulties; boss between stages; points for reaching certain level-lengths