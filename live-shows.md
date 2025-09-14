---
title: Live Shows
---
- Table of Contents
{:toc}

## Live show gameplay

### Hearts and mines

During the song, hearts and mines (could also be called spikes) will pop up on the screen regularly.

Swipe the hearts, avoid the mines. Pretty simple. But to effectively make money in this game, you want to perfect this art. See the audience pull computation below for a detailed explanation of that.

Hearts and mines popping onto the screen appears on every beat of the song, so songs with a higher BPM will pop more frequently. This mostly makes a difference if you are very fast at collecting hearts, because there is also a cap to the number of objects (hearts + mines) on the screen at any point in time (at the moment, this appears to be 8.)

Increasing voltage gradually increases the likelihood that a heart or mine will pop onto the screen, until a voltage of 100 is reached.

Hitting mines decreases voltage, which in turn will decrease the pop rate. There is no other direct effect on the pop rate when a mine is hit.

There can only be two mines on the screen at a time, so if you see two, you know it's safe to swipe down at the bottom of the screen. At all other times, this is not recommended as a mine could appear right where your finger is.

### Fever

On reaching 100 voltage in a live show, Fever will start. Staying in Fever further increases the likelihood of hearts and mines appearing until the likelihood hits some fixed limit (at the moment, this appears to be 75%.)

Because staying in fever longer results in getting more hearts, you want to choose as long a song as possible to get the highest scores.

### Special Fever

At a set point in each song, if your maximum combo so far has reached the required number (which is also different for each song) _and_ you are in Fever, Special Fever will start. Instead of hearts and mines flying up, a huge number of stars will fly up. Since there are no mines at all during this time, it is fairly effective to just swipe left and right continuously.

## Skipping live shows

If you elect to skip the live show, no new audience members will be pulled in. This doesn't mean it's totally useless, as experience is still awarded and sometimes you just have AP to burn with no time to do a live show.

## Live rankings

Once a day (from 12:00 to midnight), you get the chance to enter the live rankings. This works exactly the same as a normal live show, but your score will be contributed to the rankings at the end.

## Computing the live score

The means of computing the live score is currently unknown. We do know what might go into the score, though:

- Number of hearts caught
- Number of hearts total
- Number of stars caught
- Number of stars total
- Number of mines hit (of each type)
- Longest combo
- Longest chain (hearts or stars caught in rapid succession)
- Voltage at the end

The following also used to contribute to high score, and may still:

- Highest diva statistic
- Number of guests at the start

The reason why we don't know for sure how many parameters go into the score is that it is decided by the server. From watching network traffic you can see which parameters are being sent, but it is impossible to know what the server is doing to compute the score. The only way to guess would be to write down all parameters and the score, and gather data until there is enough data to figure out how the scoring works. Unfortunately, Special Fever now makes this quite hard, as the live result screen does not show all the individual scores which went into computing the score.

## Effect of the live score

The live score for normal lives appears to have no effect at all. Practising at getting higher scores is mainly useful for improving your position in the live rankings.

## Computing the audience pull

**_Note: This section is incorrect since the update in early February. The rules are currently much less harsh!_**

Inputs:

- Max audience limit
- Heartcatch
- Dropped hearts
- Total hearts (caught + dropped)
- Small mines hit
- Large mines hit

Calculation:

> Round([Max audience limit] × ( <br/>
> [Heartcatch] / [Total hearts] <br/>
> \- [Dropped hearts] * 0.2 <br/>
> \- [Small mines hit] * 0.2<br/>
> \- [Large mines hit] * 0.4
> ))

If the value hits 0 then it will truncate to 0 instead of becoming negative. Perhaps more importantly, if the live performance does not end on full voltage, the number of guests is automatically zero. So it is a _very bad idea_ to hit a mine near the end of the performance. Unless you can recover the 10 hearts required to get back to full voltage, you won't be pulling any new audience members!

The maximum number of audience members is 68, so if it goes over this value the additional audience members will be ignored.

Worked example:

- Max audience limit: 39
- Heartcatch: 118
- Dropped: 2
- Total hearts: 118 + 2 = 120
- Small mines hit: 0
- Large mines hit: 1

Audience pull = Round(39 * (118/120 - 2*0.2- 0*0.2 - 1*0.4)) = Round(39 * 0.583333) = **7 new guests**

