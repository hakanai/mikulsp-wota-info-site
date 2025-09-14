---
title: Live House
toc: true
---

The live house can have 0 to 68 audience members. Each member has a satisfaction value and may have a coin on them or not. (However, what is actually being stored is the average satisfaction for each group of audience members, after dividing them into the four overall enthusiasm categories.)

## Voltage

Voltage represents the enthusiasm of the audience, measured on a scale from 0 to 100.

### Changes in voltage

As new audience members arrive, their voltage starts at 20.

Having an employee serve drinks is one way to raise voltage. Each drink will raise the voltage of some members of the audience and not others, but will generally raise the average, which is what the bar represents. The maximum value this is possible to is 50.

The biggest effect on voltage is from live shows, as the voltage in the live house remains at the level it was at during the live show. More precisely, the voltage of all audience members is set to the value at the end of the live show.

It is reasonable to assume that satisfaction decays over time, but this has not been investigated yet.

### Effect on live show results

Having a higher voltage when beginning a live show will make it easier to get to full voltage during the live show (due to multiple factors [TODO: Link to Live Show Mechanics once we have it].)

### Effect on animation of audience members

Audience members are categorised into four levels, each with their own distinct animation depending on their voltage:

- Low (booing), ≤ 10
- Normal, > 10 but < 50
- High (cheering), ≥ 50 but < 100
- Enthusiastic (full rocking out and wotagei), = 100

## Popularity (にんきど _ninkido_)

Popularity represents the eagerness for people to come to your venue. It is measured on a scale from 0 to 20, but shown as five stars with each star being divided into quarters.

### Changes in popularity

Popularity increases when audience members are satisfied and decreases when they are dissatisfied. We also see it increase when booting satisfied audience members out of the live house.

Popularity decays over time.

### Effect on pulling an audience

Higher popularity pulls audience members into the live house faster, however this will only happen if nobody has coins.

## Luxury (ごうかさ _goukasa_)

Luxury represents the flashiness of your venue.

### Changes in luxury

Luxury is directly affected by the items placed in the live house. [TODO: Link to Items area once we have it.]

### Effect on income

Luxury directly affects income from live shows, as explained below.

### Optimum luxury values

The formula for money earned from a live show is:

> money = [audience] × ([luxury] × [customer weight] + [random component]) <br/>
>  = ([floor space] - [floor items]) × <br/>
>    (([base for door and stage] + [wall space] × [max wall luxury] + [floor items] × [max floor luxury]) × <br/>
>    [customer weight] + <br/>
>    [random component])

The default stage and door starts you at a luxury of 4, but the Christmas door or Japanese-style door bring this to 5. The best wall items carry a value of 4 and the best floor items carry a value of 4. Look to scratch cards for a cheap way to get these items.

The customer weight appears to vary based on the type of customer and can be seen to be between 0.8 and 1.2 based on maximum and minimum values obtained for each coin. It is probably fine to consider the average to be 1.0.

The random component is almost certainly between 1 and 50 so it will average out to 25.5.

Inserting all this information, the formula simplifies to:

> money = ([floor space] - [floor items]) × ((5 + [wall space] × 4 + [floor items] × 4) + 25.5)

Using that differential calculus you told your teacher you would never have a use for in real life, you can solve this to find the maximum payout and optimum number of floor items to place. I'll spare you the details, but the results look like this:

| Live house ||| Optimum values ||||
| Size | Wall space | Floor space | Floor items | Audience | Luxury | Avg. Income |
| ---- | ---------- | ----------- | ----------- | -------- | ------ | ----------- |
| 9 × 7 | 7 | 50 | 17 | 33 | 101 | 4174.5 |
| 9 × 9 | 9 | 68 | 25 | 43 | 141 | 7159.5 |
| 10 × 10 | 11 | 87 | 34 | 53 | 185 | 11156.5 |
| 11 × 11 | 13 | 108 | 43 | 65 | 229 | 16542.5 |

(Table assumes that no maids are taking up space on the floor. Maids have no noticeable benefit at the moment, unless you are completely new to the game.)

## Revenue

### Entry fees

The base entry fee is 20 G. You receive an additional 1 G on top of this for every 100 points of luxury.

### Live chips

Holding live shows produces "chips" which can be reclaimed for G. When reclaimed, the respective member of the audience will leave the live house, allowing more to come in subsequent lives.

Chips do not stack, so beginning a live without dismissing members of the audience to make room for new ones is usually a bad idea. Since the number of new members is impacted mostly by the number of missed hearts during a live and not impacted by a lower score, dismissing all audience members is the recommended approach, as once new members wander into your live house, this will reduce the number of new members required to fill the house. (The exception is when you are holding the live solely to try and get a higher score, since a higher starting voltage helps with the heart rate and the starting audience count itself contributes to the final score.)

### Visits to friends' live houses

When you visit a live house and perform an away from home live there, audience members present in their live house allow collecting money as well. The amount of money acquired from these chips is half that of normal lives.

### Scratch cards

Scratch cards can be acquired from away from home live shows and when your friends do the same thing at your live house, as well as randomly on sign-in each day and for other random rewards. Many of the prizes from these are cash prizes.

### Idol appeals

By having the idol appeal, currently-present audience members will all gain chips. Claiming these chips will collect the money, but this is also half that of a normal live. In addition, doing so dismisses the audience members and they will leave unhappy, reducing your popularity. It is recommended never to use this tactic.

### Contest winnings

Winning contests usually awards money (assuming, of course, that you can win.)

## Outlays

### Items

Room items, stages, wall and floor customisations, floor expansion and the like all cost money. Many floor items can be obtained from scratch though, if you're not choosy about which items you use.

### Training

Training costs money for each shot.

### Contest entry fees

Contests cost money to enter (although if you can win them, you recover the cost easily.)

