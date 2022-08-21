---
layout: post
title: Final Project Reflection Post
---

This quarter my Team (Puppy Party) worked on creating an interactive [webapp](https://pic16b-dog-detector.herokuapp.com/) to allow users to predict a dog's breed based on a picture. We wanted this web app to address the problem many cannine-lovers have: recognizing niche dog breeds. On top of our dog-breed image classifier we also created a feature on our web app to allow users to discover the best dog breeds for themselves

My team and I wrote the responses to questions 1-4 together. I wrote the responses for questions 5-6 by myself.

## 1. Overall, what did you achieve in your project?

We achieved a variety of goals in these projects. Namely, we created a model capable of predicting over 120 dog breeds based on an image. Based on 10 epochs of training we achieved validation accuracy in the range of 80%. On top of our dog breed classifier we also created an interactive web page for users to find out what dog breeds most align with their interest. Using categories such as ease of maintenance, dog size, and trainability we are able to gauge which dog breed(s) are best suited for an individual.

## 2. What are two aspects of your project that you are especially proud of?

One feature of our project is that the model learns from incorrect breed predictions when the user submits a Google Form containing the picture and correct dog breed. This is one portion of our project that we are particularly proud of, as the model actively learns from data beyond the original dataset we trained our model on. When a user inputs the incorrectly identified photo alongside the correct dog breed, this data is added to a spreadsheet that our model can then train with and learn from. On the web application, this learning process automatically occurs once a day, so within 24 hours, our model will implement the correct prediction of the same photo. We thought having the model learn from its mistakes was an innovative addition to our project and are especially proud of it for this reason. 

We are also very proud of the dog breed recommendation portion of our project. On the “Find Your Perfect Dog!” page of our web application, users can input a variety of attributes they want in a dog, and our project then returns the top three matches based on a dataset we found online. We made this page as user-friendly as possible, with an efficient matching algorithm to ensure a fast result, as well as hyperlinks that users can click on and go to the American Kennel Club website containing more information about the matched breeds. Users can then easily learn more about these dog breeds and make an informed decision regarding which breed best suits their lifestyle. 

## 3. What are two things you would suggest doing to further improve your project? (You are not responsible for doing those things.)

One suggestion to further improve our project is to include more dog breeds. Currently, the breed prediction model is trained on 121 breeds and the breed recommender includes 199 breeds. There are many more dog breeds that could be included in these two aspects of our project. Furthermore, our breed prediction model is trained on images of purebred dogs, and thus it does not perform as well on mixed breed dogs. If we could obtain or create a database of mixed breed dogs that included the list of breeds that each dog is, we could further train the model to predict the multiple breeds of a dog. This does pose many challenges since the amount of breed combinations is very great, however, it would allow our project to be more inclusive of dogs.

Another suggestion to improve our project would be to add a ranking system to the breed recommender. Currently, the user selects their preferences on 6 dog features, and all of these features are weighted equally when recommending the dog breeds. It is likely that of the 6 presented features, a user may care about some features more than others. Perhaps they want a dog with minimal shedding and maintenance, but don’t care about the size of the dog. Adding a ranking system for the features would provide recommendations that better match the preferences of the user. 

## 4. How does what you achieved compare to what you set out to do in your proposal? (if you didn't complete everything in your proposal, that's fine!)

We completed more than what we included in our proposal! Our project proposal only indicated a model on a webapp that would input a picture and output the dog breed. We successfully did this and added more features. 

Our model also includes an online learning feature. The model can take feedback from the user and improve itself in the next run. We also included sample images, so people who don’t have photos handy on their devices can still enjoy the webapp. We also included a dog recommender tab where the user can input his or her preferences, and the webapp will use KD Trees to predict the top 3 matches and display corresponding pictures and links.

## 5. What are three things you learned from the experience of completing your project? Data analysis techniques? Python packages? Git + GitHub? Etc?

This project made me familiar with using streamlit, tensorflow, and model deployment as a whole. 

Streamlit is an open-source library used for front-end web development. Finetuned for Python projects, streamlit makes front-end developement more streamlined (hence the name haha) and allowed me to focus on making my team's model compatible without having to worry too much about aesthetics. By using streamlit my team and I were able to focus on deployment and our back-end rather than getting stuck on making our web app look pretty.

Deploying tensorflow ended up being extremely challenging. Heroku (a platform as a service) is what we used to deploy our project to the cloud. However, Heroku is only compatible with tensorflow 2.0.0. As a result when building my model and deloying it I had to be acutely aware that I had to work within a tensorflow 2.0.0 virtual environment and ensure all tensorflow dependencies were not too modern (i.e. greater than version 2.0.0).

Lastly, the most important thing I learned when completing this project was how to deploy a model efficiently. During my first few attempts at predicting a breed based on image I found that it took roughly 20-30 seconds to load, compile, and predict. Eventually I discovered that Heroku restarts our team's application once every 24 hours. As a result the first interaction after "heroku restarts our application" runs the content outside of main. However, every subseuent interaction only runs main(). As a result, upon loading my model outside of main() I found that I was able to predict dog breed much more quickly, since loading the model was among the most time-consuming processes in our web application.

## 6. How will your experience completing this project will help you in your future studies or career? Please be as specific as possible.
Having gotten a taste of using tensorflow on a completely foreign dataset I want to now embark on bigger and bolder projects. More importantly, I really enjoyed working in a collaborative group where we were able to each contribute equally to create something that we are proud of. From my experience completing this project, I've come to realize I enjoy cross-collaboration and bouncing off ideas. Never in a million years would I have thought of creating a dog-breed recommender system on top of our original work. However, Charisse and Britney helped us envision this idea by finding the necessary data and using unique packages to see it through.

I feel like I have become a more efficient communicator through this process and realize I want to work in the industry as a data scientist who is responsible for creating models to helped extract new insights. Additionally, this project definitely made me realize the value of data cleaning and EDA. Without taking the time to start from the basics with clean data, it would have been near impossible to create a workable model that is compatible with the user-input.

