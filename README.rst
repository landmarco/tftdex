TFTdex
=============



The TFTdex is a tool for Teamfight Tactics that shows the probability of finding desired champions in the shop. The chart is set up to show the expected value of of finding a champion after a certain number of rolls. The TFTdex is intended to be a companion tool that can be usefully accessed during play by keeping input time to a minimum and clearly displaying expected values of finding champions.

Usage
-----

Run the cell (click inside it and press SHIFT+ENTER) in order to activate the plot. Choose your current level, then input the tier of the first champion you are looking for in the textbox for "Champion A". The plot will update automatically to show the expected value of hitting that champion after a certain number of rolls. You can also change the number of rolls displayed on the chart by adjusting the "Max Rolls" parameter. You can include up to five champions at a time by inputting their tiers in the textboxes for champions A-E. Multiple champions are displayed as a stacked bar chart, showing the expected value for a given champion as well as the expected value for finding any one champion you're looking for. A quick glance shows you how long you should expect to need to roll before getting a hit, and adjusting your level can show you how much those expectations can change if you wait to roll down at a higher level. That should be all you need to get started with the TFTdex - happy rolling!

The TFTdex also provides ways to further refine the plot if you would like to include the additional parameters that influence the probability calculations. The expected value displayed is a good starting point for quickly evaluating expected outcomes in game, but it is not precisely representative of the actual likelihoods faced as it is assumes all champions in a shop are available and so does not account for claimed champions being removed from the pool. In order to remove all instances of a desired champion that have already been claimed, you can input the parameters separated by a comma in the textbox for a champion in the format "TIER OF CHAMPION,NUMBER OF CLAIMED CHAMPIONS". For example, say you have two Kennens (a tier 3 champion) and are looking for a third. After looking through the board you see that there are seven 1-star Kennens (including your two) and two 2-star Kennens claimed, which means there are 13 Kennens removed from the shop pool. You would then input into the Champion A textbox "3,13". Note that the expected values that are then displayed are a lower bound of the true values as they do not account for all the other champions in the same tier that have been claimed and also removed from the shop pool.

If you want to completely account for all parameters, you can include all champions claimed within a tier in the format "TIER OF CHAMPION, NUMBER OF CLAIMED CHAMPIONS, TOTAL NUMBER OF OTHER CLAIMED CHAMPIONS IN TIER". Continuing the Kennen example, if you took the time to count up all the champions on all boards and found that there are 42 Tier 3 champions claimed (other than the 13 Kennens you've already accounted for), then you would input into the Champion A textbox "3,13,42". Now the displayed values are completely representative of the current game state. Obviously having to count up all the other champions in a tier is a pretty time-consuming process, and I find I only drill down to this level of specificity if I'm looking for tier 5 champions, there are only three or less players left, or I'm theorycrafting outside of an active game.

Now say you claim your expectations transcend arithmetic means. "My expectations require more knowledge of the stats." You devil! You fiend! Very well, there's also an option to show the geometric CDF of your likelihood of a hit after a certain number give number of rolls.

The geometric plot can be especially helpful when you're in a bad spot and essentially need to choose between different types of hail marys. Do you roll down 40 gold in search for the last Aurelion Sol that will give you the power spike you need? Or do you spend 20 of that gold leveling so that you can roll for a higher chance for Aurelion Sol or Karthus?


Installation
------------

Requirements
^^^^^^^^^^^^
- Python 3.5
- Numpy 1.15.4
- Pandas 0.22.0
- Plotly 3.6.0
- ipywidgets 7.4.1

Compatibility
-------------

License
-------
TFTdex is free (libre) software and licensed with a GPLv3 copyleft license, which means it can be incorporated into any software that is also licensed with GPLv3. If you are using any component of this, I would appreciate it if you would inform me via `email <marc.loeffke@gmail.com>`_.

Authors
-------

`tftdex` was written by `Marc Loeffke <marc.loeffke@gmail.com>`_.
