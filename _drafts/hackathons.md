Lately, I have been participating to some hackathons in Berlin:

## Apps World Germany

22/04/2015

This was 2 days event about development, strategy and marketing around mobile and hopefully it included a hackathon -- much more interesting than the conferences. The hackathon had two sponsors :

* [Blukii](http://www.the-hackfest.com/events/blukii-hackfest/), a company working on sensors based on Bluetooth LE.
* [Wincor Nixdorf](http://www.the-hackfest.com/events/wincor-nixdorf-hackfest/), offers an Android device including payment system with printer and nfc reader...

For that I join one collegue, [Markus](https://github.com/Neoklosch) and a former collegue [Andreas](https://github.com/buffstop) and formed the [team Cookie Monster(s)](https://github.com/Cookie-Monsters) to work on two projects, one for on each sponsor.

* [Donator](https://github.com/Cookie-Monsters/Donator), an Android app to donate money to charity organisation.
* [Plantkii](https://github.com/buffstop/FlowerAlarm), an iOS app to read the humidity, luminosity and temperature of a plant.

Technically on the iOS part, I spent to much time on little details like permissions that were not going to show up on the demo. But I did learn a thing or two 'cause the SDK to interact with the sensor was in Swift and some methods were not available through the bridge to Objective-C.

## HacknWear

12/06/2015

Organised by Bemyapp and sponsored by Salesforce, was the occasion to play with some gadgets. On this hackathon with the same team, we end it up doing a Located Question based app called [uQu](https://github.com/buffstop/Qute).

This was better than the Apps World because of the mood, the beer did help ;) but a lot because of the friendly staff and everyone is in the same state, trying to make Salesforce api work.

Besides, I had a chance to play with a Sphero as you can see below. I wouldn't buy it but it was fun to try it out:

{% vimeo 131478785 %}

So more about the hack, it was the first/quick attempt to learn about doing an Apple Watch extension, but again wasted time on stuff that did not matter like getting the location and display a map on it and ended up *faking it*.


## BattleHack Berlin

19/06/2015

I was not egger to go to that one -- mostly because it was again one (part) of the weekend busy -- but at the end, happy with the result.

We had to include of the sponsors in our hack such as Braintree/Paypal (payment), Heroku, Pusher, Sendgrid and Twilo.

This time I teamed up with Ben and Thomas and we chose to make a Github bot which will help fix issues in giving rewards ($) to contributors.

Though we discovered other people had this [idea](http://bountysource.com) or even a team the week before in [Japan](https://2015.battlehack.org/tokyo?locale=ja), I especially like the fact that all the interaction stays on Github and that it does not require permissions on Github. You can call @potogold on any repos and any issues.

**[Pot o' Gold](https://github.com/netbe/potogold)** was not a winning project but was a success for me because we achieved what we wanted in a 24 hours straight (no sleep) and learned new stuff:

* Github api
* Braintree for payment
* Flask (similar as Sinatra but in python)
* Twilio for sending sms

We also used Sendgrid and Heroku but that was not really new to me.

So we will continue this project to make it available (now using sandbox payment) and hopefully the community will support it.

## Conclusion

At the end the hackathons are a good experience not only to try something new but as a reminder on what matter during a project : Get the shit done. It does not matter if the code is well organised follow convention or documented. Besides most of time you end up faking it for the demo.


