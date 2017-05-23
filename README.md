# Prototype for a visualized network analysis of City of Chicago FOIA requests using Neo4J

One of my favorite assignments while taking General Assembly's Data Science Immersive coursework was a surprise one-day "hackathon" where we were tasked with coming up with a viable idea for a project using data from the [City of Chicago data portal](https://data.cityofchicago.org/) and some results to show for it. We had recently been introduced to social network analysis, and our teacher pointed us to a neat demo that [Neo4J](https://neo4j.com/) had for visualizing graph databases (the movies/actors/directors example in the tutorial for the download version). Since playing around with that demo, I had been wanting the opportunity to start to learn Neo4J, and so I seized this class assignment as an opportunity to dive in.

I'm active in community grassroots politics and volunteering with a group that is trying to begin to map political connections in a way that would be useful for reporters and citizens, so I came up with the idea to use the [FOIA (Freedom of Information Request) request log for Ethics](https://data.cityofchicago.org/FOIA/FOIA-Request-Log-Ethics/fhb6-wwuu) to see what might emerge as a social network. My thinking was that by tracking who is being FOIAed for ethics issues, we might get a sense of who citizen watchdogs and reporters should be keeping an eye on in terms of corruption and shenanigans (because if someone has to go to the effort of FOIAing a politician with respect to the subject area of ethics, there's likely some sort of reluctance to release information to the public going on).

Some things of note before I jump to a video I made exploring the network visualization and some screencaps:

1) This is the product of one day's work, plus a few additional hours outside of that.

2) This initial prototype is a *very* rough start. Only some of the FOIAed people are in here, and only some of the relationships have been mapped. I also just set up a quick-and-dirty way of getting the entities and their relationships into the graph database by setting up some scripts that would batch write the queries and then just pasting them en masse into the Neo4J user interface.

3) The FOIA data is held in a spreadsheet where who was FOIAed is descriptive--those fields contain more than just the names of the FOIAed people. So I looked around to see if I could find a quick open-source proper-name extractor to strip the politicians' names out of the three columns that held the FOIA subject information. In the short time I had allotted, I couldn't find one, so I just moved on and wrote the foundation of one using regex (more about that here: [ADD LINK]--this is something I'd like to work more on and would love collaborators). I only had time to create patterns for some of the name types, so this in by no means anywhere near complete. I also started to create a list of dataset-specific stopwords, but you'll see from the video that explains the results that I have more to identify and add.

4) There's also an entity matching issue with the names, which you'll also see in the video (for example R. Emmanuel and Rahm Emmanuel). Something to tackle in the future.

5) Right now, because I have not had a chance to pull all the FOIAed subjects' names out of the spreadsheet the visualizations are very reporter-centric and tell more of a story of which reporters are really diligent investigators rather than trends in who is being investigated. However, I hope that when I have a chance to input more of the politicians by extracting their names from the spreadsheet, the focus will be more on some of them. A fun experiment at the very least!

Okay, so for a glimpse into what the visualizations look like you can watch this short screengrab video I made explaining what's going on (sorry for my computer fan periodically running loudly in the background...my poor computer is old and gets taxed easily).

[![YouTube Screenshot](/Images/YouTubeVideoScreencap.png)](https://youtu.be/0429f9pyw9I "Click to Watch!")

And for those without the time to watch the video, here are a few screencaps.
![SS1](/Images/ScreenShot1.png)
![SS1](/Images/ScreenShot2.png)
![SS1](/Images/ScreenShot3.png)
![SS1](/Images/ScreenShot4.png)
![SS1](/Images/ScreenShot5.png)
