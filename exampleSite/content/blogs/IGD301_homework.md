---
title: 'IGD301: Lecture Homework'
content: My reflexion on some MR subjects
date: 2022-01-00

---

## Context

This post is part of the homework for the Human-Computer Interaction for Mixed Reality course I'm taking at Telecom Paris. I will be addressing a series of lecture tasks that we have been asked to reflect on.

## HomeWork 1:

### Task:
Watch the video called Hyper Reality. 
{{< youtube YJg02ivYzSs >}}
Hyper Reality presents a dystopian future using Mixed Reality technology. It consists of multiple scenarios in which potential dangers are presented. Come up and present TWO additional scenarios from our daily life in which Mixed Reality technology can create problems for the user or can be abused by content creators, authorities, users or other entities. Elaborate what makes this scenario abusive and reflect upon techniques how we could avoid this trajectory.

### Answer:

#### First scenario:
##### How Mixed Reality technology can create problems for the user and be abusive:
One way MR can go wrong is actually an extension of the toxicity and abuse we can already note in the digital domain like in some cases of online video games or chatrooms. The creation of one or more metavers hinges on the idea of crossing the physical barriers and achieving a high level of realism in communication. This will lead logically to the augmentation of the effect of any type of digital violence (stalking, hate speech, sexual abuse,...). To illustrate this case better, you can take the case of a "content creator" who's doing a VR chatroom Q&A with their "followers". If this "influencer" has bad intention and is counting on taking advantage in some way or another of one of the followers, the VR experience will give a close to reality experience where they can use the pretext of "Virtuality" and "This is not real" to lay the ground for more serious and toxic behaviour they're intending on bringing to reality later. The VR experience can pose as a discrete and hidden trap for more vulnerable targets like kids. It can be used to normalize what should be condemned in the real world. 
##### How we could avoid this trajectory:
I think this type of problem is one of the most serious ones and should be addressed before any VR experience design process. This is something that the Internet and the digital world have totally failed in so far. Ensuring that this type of abuse is not replicated in the VR context should be a top priority for all designers and companies in the industry. "Hacky" solutions have been proposed, such as the "mute" button, which allows you to decide to make an avatar disappear from your virtual environment and no longer hear the user. This is a good solution in a certain context, but it does not solve the main problem. It relies on the victim being aware of being the target of toxic behavior. This is obviously not always the case, and you can take the example of the many children who are transformed by these kinds of experiences into a more violent version of themselves because they have learned that this is the normal thing to do. Another example is the fan who is targeted by a more malicious and "tactical" approach by the " infuencer" they follow. Chat control has been used in the context of video game chat where certain players can be banned or tagged. These systems are built on text-based AI (still not good enough and even more difficult for more subtle behaviors in 3D interactive environments) or on a reporting system relying on victims. To be honest, the problem I am talking about is very complex and intricate and I don't think there is a magic solution for every case. I'm more inclined to think that it should be addressed on a case-by-case basis and mostly upstream in the design process, not after the application is launched. Second, platforms are generally controlled by large companies that should have enough resources to enforce socially compliant beta testing of any app before deploying it. A table of controversial scenarios can be created collaboratively among all parties active in MR and this table can be the basis for such beta testing.

#### Second scenario:
##### How Mixed Reality technology can create problems for the user and be abusive:
Tracking is an essential part of any XR system, as context-aware interaction is the essence of it. To achieve a higher level of realism and a more personalized experience, more data (camera, hand movement, gestures, eye tracking, ...) must be captured and processed by the system. This will lead to serious privacy issues, as more and more accurate user profiling will occur. Governments and corporations can abuse this access to target individuals with discreetly tailored propaganda and behavior-altering signals. This can have negative effects on individuals who find themselves trapped in an "idea bubble" where they are less and less exposed to different points of view and develop more biased and dogmatic opinions. This phenomenon alone can seriously undermine social cohesion, with the emergence of conspiratorial communities and the decrease of social dialogue platforms. Again, the context of the XR is important because it makes it difficult for the user to break out of such rings because of the realism it imparts to the experience. Bots and real people can become even more indistinguishable through improved avatar technologies and voice generation.

##### How we could avoid this trajectory:
I personnaly believe that there is no going around when it comes to the privacy matter. No personal data, what so ever, should be loaded to external servers even for temporary processing. Counting on the good wilingness of app creators or XR companies is a naive approach. The issue is therefore 100% political and should be treated as such. We should have a serious debate on the necessary limits for such applications and the role of goverments to enforce them. From a designer and developer point of view, data processing should be done locally while the communication and experience sharing should be implemented as an exchange of higher level abstract data.


## HomeWork 2:

### Task:
Read the “Ultimate Display” and discuss how Ivan Sutherland’s vision of the Ultimate Display fits into the Reality-Virtuality Continuum of Milgram. Is it a discrete point ? Is it an area ? Is it inside the continuum or is it even surrounding the continuum ?

![](/uploads/milgram_conitnuum.png)

### Answer:
Before answering the question, I will start by reflecting a little bit on what Ivan Sutherland envisioned in his article.
An expression that was repeated for a reason is *"a looking glass into a mathematical wonderland"*. Sutherland stresses this idea of a wonderland that encompasses the physical rules we are used to, those beyond our capacity to perceive, and a new set of unreal rules that could only exist in this "wonderland." The display in this context is a "looking glass". This is obviously not a simple metaphor for sight but, as the author explains, it refers to "as many senses as possible". So, to recap, we have a new world that follows real and unreal rules and a direct way to immerse oneself in it. So it seems that this version of the display spans the entire spectrum of mixed reality, with this sense of mixing real and virtual elements and augmenting the real and virtual. 
That being said, I don't think this is exactly what Sutherland envisions based on the following two points:

 - Speeking of these new rules that we can imagine, he writes: *"we can learn to know them as well as we know our own natural world"*.This idea of learning and integrating new experiences into one's life goes beyond the context of information display and can be seen as a kind of symbiotic relationship between human and computer.

 - *"The ultimate display would, of course, be a room within which the computer can control the existence of matter"*. This last sentence establishes an even sharper divergence from Milgram's Reality-Virtuality Continuum, because not only are we mixing virtual and real elements at the display level, but we are establishing a cause-and-effect relationship that crosses the barriers between the two words.


 ## HomeWork 3:

 ### Task:
 Think about THREE alternative ways that we could implement locomotion. You should focus on the following questions:
 - What is the goal of your locomotion (e.g., be the fastest, be the most enjoyable, ...) ?
 - How does your locomotion system work ? (e.g., what is the metaphor for the user and how do you want to implement it) ?
 - How do you want to evaluate if you were able to achieve your "goal" ? (e.g., what do you want to compare against, what metrics do you want to collect and how ...)

### Answer:

#### 1. **HoVRboard**
##### The idea:
<iframe src="https://giphy.com/embed/l3vRkIlMY2Ovt99jq" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/colbertlateshow-stephen-colbert-late-show-segway-l3vRkIlMY2Ovt99jq">via GIPHY</a></p>

The idea is quite straightforward: the user would be using a virtual hoverboard that can be controlled exactly like the actual one works. This locomotion technique can be fast and easy to use. It would be precise after a small amount of learning time. For more immersion and for implementation reasons, the user can stand on a wooden object that has similar degrees of freedom as does a hoverboard. This object would be tracked by fixing for example controllers on it and we can then retrieve orientation info on some of its parts and map those values to commands for the virtual hoverboard.

![](/uploads/hovrboard.jpg)

##### How to evaluate this technique:
I think the main "selling" point of such technique would be with comparaison to fast one like teleportation. I believe it would be interesting to see if we can achieve similar speed performance while still presenting a higher level of presence.

#### 2. **Giant hand extended**
##### The idea:
This locomotion technique is based on an interaction one I'm currently developping in the context of a guided reasearch project (Project Post: In the palm of your hand). The idea is to map the environment to one hand of the user and they can then pinpoint positions on that map by simply pressing the corresponding position using using a finger from the other hand. To have a better visual input, we display a giant hand in the environment that shows the correspondance between areas on the users hand and areas in the scene. The user is then teleported to the targeted position.

![](/uploads/gianthandsketch.jpg)

##### How to evaluate this technique:
This technique is designed to allow the same advantages of classical teleportation techniques while aiming at leveraging the precesion and natural feeling that propreoception proposes. It would then be interesting to see if we can achieve the same teleportation speed performance with better accuracy and greater accessibility to less visible locations.


#### 2. **Gomu Gomu locuMe**
##### The idea:
This thechnique is inspire by One Piece's protagonist Luffy. In this anime, this character is a rubber man and can stretch his body by will or by pressure.

<iframe src="https://giphy.com/embed/9S1CJae4qyOZGLWa4y" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/funimation-one-piece-luffy-stretch-9S1CJae4qyOZGLWa4y">via GIPHY</a></p>

Based on that, we can imagine a VR experience in which the user can extend their hand in one direction, then move it in another direction while continuing to extend it. Upon reaching a target position, the user can press a button and is drawn to that location by following the curve of the hand. This technique is mainly intended for gaming applications, as it is not really practical, but it can give a fun and magical experience unmatched in the real world. It can also be useful to reach corners or hidden places.
For the implementation, we can start by adapting the go-go interaction technique by adding a hand mesh that stretches according to the hand's curve and then implement the movement on button press.


##### How to evaluate this technique:
The main purpose of this technique is to increase the enjoyment metric. A good evaluation protocol would be to design a game experience where different locomotion techniques are competed in the same context. We could then conduct a user study and examine whether or not this goal is achieved.