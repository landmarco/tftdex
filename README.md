TFTdex
=============

The TFTdex is a tool for Teamfight Tactics that shows the probability of finding desired champions in the shop. The chart is set up to show the expected value of of finding a champion after a certain number of rolls. The TFTdex is intended to be a companion tool that can be usefully accessed during play by keeping input time to a minimum and clearly displaying expected values of finding champions.

The likelihood of finding champions is explored in two different plots. The first plot shows the expected number (arithmetic mean) of champions found after a certain number of rolls, which corresponds to the simplified binomial representation of the problem. The second plot shows the likelihood of at least one hit after a certain number of rolls, which is the geometric representation. The geometric representation is plotted as a cumulative distribution function and also shows the median number of rolls until a hit.

![Imgur](https://i.imgur.com/6ZCesrs.png)

![Imgur](https://i.imgur.com/9wp1Hem.png)

Installation
===========

Requirements
------------
- Numpy 1.15.4
- Pandas 0.22.0
- Plotly 3.6.0
- ipywidgets 7.4.1

If you already have jupyter set up, after cloning this repository execute the following in the downloaded repository's path to install all the required packages at once:

``pip install -r requirements.txt``

Then open tftdex.ipynb and continue to the **Usage** section.

The following section shows how to set up the TFTdex assuming no prior python experience.

To set up your python and notebook environment, the easiest method is to install Anaconda. Visit https://www.anaconda.com/distribution/ and download the Python 3.7 version for your operating system. Follow the instructions to install Anaconda, Python, and jupyter.

Once that is finished, open a terminal window and execute the following command:

``git clone https://github.com/landmarco/tftdex.git``

If you don't have git, you can instead download this repo here https://github.com/landmarco/tftdex/archive/master.zip then unzip it. Navigate into this directory in your terminal, then type:

```
conda install pip
pip install -r requirements
jupyter notebook
```

At this point your browser should pop up showing the file list in the tftdex directory. Click on tftdex.ipynb to open the jupyter notebook, then continue to the **Usage** section.

Usage
-----
Open tftdex.ipynb and run the cell (click inside it and press SHIFT+ENTER) in order to activate the plot. Choose your current level, then input the tier of the first champion you are looking for in the textbox for "Champion A". The plots will update automatically. You can also change the number of rolls displayed on the chart by adjusting the "Max Rolls" parameter. You can include up to five champions at a time by inputting their tiers in the textboxes for champions A-E. Multiple champions are displayed as a stacked bar chart in the first plot, showing the expected value for a given champion as well as the expected value for finding any one champion you're looking for. The second plot shows the likelihood of any hit as a separate trace labeled "Total." A quick glance shows you how long you should expect to need to roll before getting a hit, and adjusting your level can show you how much those expectations can change if you wait to roll down at a higher level. That should be all you need to get started with the TFTdex - happy rolling!

The TFTdex also provides ways to further refine the plots if you would like to include the additional parameters that influence the probability calculations. The expected value displayed is a good starting point for quickly evaluating expected outcomes in game, but it is not precisely representative of the actual likelihoods faced as it is assumes all champions in a shop are available and so does not account for claimed champions being removed from the pool. In order to remove all instances of a desired champion that have already been claimed, you can input the parameters separated by a comma in the textbox for a champion in the format "TIER OF CHAMPION,NUMBER OF CLAIMED CHAMPIONS". For example, say you have two Kennens (a tier 3 champion) and are searching for a third at level 6. After looking through the board you see that there are seven 1-star Kennens (including your two) and two 2-star Kennens claimed, which means there are 13 Kennens removed from the shop pool. You would then input into the Champion A textbox "3,13". Note that the expected values that are then displayed are a lower bound of the true values as they do not account for all the other champions in the same tier that have been claimed and also removed from the shop pool.

![Imgur](https://i.imgur.com/2lFE6qv.png)

If you want to completely account for all parameters, you can include all champions claimed within a tier in the format "TIER OF CHAMPION, NUMBER OF CLAIMED CHAMPIONS, TOTAL NUMBER OF OTHER CLAIMED CHAMPIONS IN TIER". Continuing the Kennen example, if you took the time to count up all the champions on all boards and found that there are 42 Tier 3 champions claimed (other than the 13 Kennens you've already accounted for), then you would input into the Champion A textbox "3,13,42". Now the displayed values are completely representative of the current game state. Obviously having to count up all the other champions in a tier is a pretty time-consuming process, and I find I only drill down to this level of specificity if I'm looking for tier 4 or 5 champions, there are only three or less players left, or I'm theorycrafting outside of an active game.

![Imgur](https://i.imgur.com/CVuBIpr.png)


License
-------
TFTdex is free (libre) software and licensed with a GPLv3 copyleft license, which means it can be incorporated into any software that is also licensed with GPLv3. If you are using any component of this, I would appreciate it if you would inform me via `email <marc.loeffke@gmail.com>`_.

Authors
-------

`tftdex` was written by `Marc Loeffke <marc.loeffke@gmail.com>`_.
