## Improving the internet for the millions, with just a weekend
_Guest blog by [Luke Harries](https://www.linkedin.com/in/luke-harries/), representing the Microsoft Cogntive Services winners at HackCambridge._

HackCambridge provided the perfect oppertunity to return to Cambridge University. There I had completed my undergraduate degree in medicine and cognitive neuroscience, before moving to UCL to study a masters in Computer Science. Also in our team was [Filip](https://www.linkedin.com/in/filipkozera/), a masters student in information engineering at Cambridge, where he is using deep learning on EMG signals to control prosthetics; [Marcin](https://www.linkedin.com/in/marcin-kolaszewski-07912314a/), a joint honors Mathematics and Computer Science student from Brown University; and [Mateusz](https://www.linkedin.com/in/mateusz-jakub-staniszewski-19946590/), a recent Mathematics graduate from Imperial and a current Software Engineer at BlackRock.

With flights from Poland to London for two of the team booked, we starting discussing ideas for what would be the first Hackathon for the majority of us. Our ideas ranged from trying to implement a decentralised ICO ([DAICO](https://ethresear.ch/t/explanation-of-daicos/465)) to controlling a VR world with a [Myo armband](https://www.myo.com/). 

As the event neared, Microsoft was announced as a sponsor by a video of their [Seeing AI app](https://www.youtube.com/watch?v=R2mC-NUAmMk) being posted to the HackCambridge facebook page. The video shows how Saqid Shaikh, a blind software developer at Microsoft, using the app he created to convert a visual world into an audible experience. **It was incredible**. The app could describe kids playing Frisbee in the park, or allow him to read a menu. We could only imagine the impact it had on him and many others with visual impairments.

We knew we wanted to build on shoulders of SeeingAI's fantastic work. We initially discussed building an Android app equivalent, possibily in conjunction with Myo Armband for hands-free control. However, with five minutes to go before the hackathon started I performed a last scroll through the web to see if any other inspiration would strike us. That's when it dauned on ous how much of the internet must still be inaccessible to the visually impaired. 

## The problem

People with visual impairments frequently rely on a Screen Reader to navigate the internet. The Screen Reader reads out what’s on each page. However, when the Screen Reader reaches an image it has to rely on the “alt tag” to provide a caption. For the majority of the internet these “alt tags” are either missing (think of any user-uploaded content such as Twitter or LinkedIn), superficial or inaccurate.

> This affects millions of people everyday.

<img align="center" width="460" src="job.png" alt="Example of job post which is save as an image and therefore not accessible">  

_The Screen Reader would not pickup any details of this "Hot Job"_

## The solution

Once we had narrowed down the problem coming up with the solution was much easier. We decide we would bring Facebook's automatic "alt tag" generation to every page on the internet (right click on your profile picture, click inspect element and see what Facebook's sees!).

By using a Chrome extension we could scan through every element on the page looking for images lacking an "alt tag". For each image where the "alt tag" was missing we would send the image URL to an Azure cloud function. The cloud function would check if we already had the "alt tag" saved and if so return it. If not we would use the Microsoft's Cognitive Services Vision Api to perform object recognition and generate the description to be added as the "alt tag". 

We split into pairs: Mateusz and I built the Chrome extension, and Filip and Marcin built the cloud function and hooked it up to the Cognitive Services api. We started building at 2pm and by 9pm we were had a prototype fully working. The speed, accurarcy and ease of integration that the image descriptions were generated would not have been possible just a few years ago. The extra time allowed us to link in three more apis: facial recognition, emotion recogontion and OCR (image to text), depending on what was in the image. This provided a much more descriptive image captions.
> The speed, accurarcy and ease of integration that the image descriptions were generated would not have been possible just a few years ago.

### What's next?

We are really proud of what we have built so far and cannot wait to release it to the public. We hope our Chrome extension will impower those with visual impairments to browse the web, without having to rely on others to create the "alt tags".

![Team Picture](team.jpg)
