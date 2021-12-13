# for more clearity and reference please read the report 
# face_detection_using_mtcnn
About the project
Introduction 
Face detection -- also called facial detection -- is an artificial intelligence (AI) based computer technology used to find and identify human faces in digital images. Face detection technology can be applied to various fields -- including security, biometrics, law enforcement, entertainment and personal safety -- to provide surveillance and tracking of people in real time.
Face detection has progressed from rudimentary computer vision techniques to advances in machine learning (ML) to increasingly sophisticated artificial neural networks (ANN) and related technologies; the result has been continuous performance improvements. It now plays an important role as the first step in many key applications -- including face tracking, face analysis and facial recognition. Face detection has a significant effect on how sequential operations will perform in the application.

How face detection works
Face detection applications use algorithms and ML to find human faces within larger images, which often incorporate other non-face objects such as landscapes, buildings and other human body parts like feet or hands. Face detection algorithms typically start by searching for human eyes -- one of the easiest features to detect. The algorithm might then attempt to detect eyebrows, the mouth, nose, nostrils and the iris. Once the algorithm concludes that it has found a facial region, it applies additional tests to confirm that it has, in fact, detected a face.
To help ensure accuracy, the algorithms need to be trained on large data sets incorporating hundreds of thousands of positive and negative images. The training improves the algorithms' ability to determine whether there are faces in an image and where they are.
The methods used in face detection can be knowledge-based, feature-based, template matching or appearance-based. Each has advantages and disadvantages:
•	Knowledge-based, or rule-based methods, describe a face based on rules. The challenge of this approach is the difficulty of coming up with well-defined rules.
•	Feature invariant methods -- which use features such as a person's eyes or nose to detect a face -- can be negatively affected by noise and light.
•	Template-matching methods are based on comparing images with standard face patterns or features that have been stored previously and correlating the two to detect a face. Unfortunately these methods do not address variations in pose, scale and shape.
•	Appearance-based methods employ statistical analysis and machine learning to find the relevant characteristics of face images. This method, also used in feature extraction for face recognition, is divided into sub-methods.
Some of the more specific techniques used in face detection include:
•	Removing the background. For example, if an image has a plain, mono-color background or a pre-defined, static background, then removing the background can help reveal the face boundaries.
•	In color images, sometimes skin color can be used to find faces; however, this may not work with all complexions.
•	Using motion to find faces is another option. In real-time video, a face is almost always moving, so users of this method must calculate the moving area. One drawback of this method is the risk of confusion with other objects moving in the background.
•	A combination of the strategies listed above can provide a comprehensive face detection method.


What is MTCNN
MTCNN is a python (pip) library written by Github user ipacz
In this paper, they propose a deep cascaded multi-task framework using different features of “sub-models” to each boost their correlating strengths.
MTCNN performs quite fast on a CPU, even though S3FD is still quicker running on a GPU 
Installing MTCNN Library
MTCNN is available as a pip package, meaning we can easily install it using
 
Now switching to Python/Jupyter Notebook we can check the installation with an import and quick verification:
Afterwards, we are ready to load out test image using the matplotlib imread function.
 
Now your output will look a lot like this:
 
What does this tell us? A lot of it is self-explanatory, but it basically returns coordinates, or the pixel values of a rectangle where the MTCNN algorithm detected faces. The “box” value above returns the location of the whole face, followed by a “confidence” level.
If you want to do more advanced extractions or algorithms, you will have access to other facial landmarks, called “keypoints” as well. Namely the MTCNN model located the eyes, mouth and nose as well!
Drawing a box around faces
To demonstrate this even better let us draw a box around the face using matplotlib:
 
 
Output 

 
Adding more features in the model to display eyes, mouth and nose around faces
Now let us take a look at the aforementioned “keypoints” that the MTCNN model returned.
We will now use these to graph the nose, mouth and eyes as well.
We will the add following code snippet to our code above:
 # 

 
Extra Experimental analysis ( in case of large dataset)
Advanced MTCNN: Speed it up (\~x100)!
Now let us come to the interesting part. If you are going to process millions of pictures you will need to speed up MTCNN, otherwise, you will either fall asleep or your CPU will burn before it will be done.
But what exactly are we talking about? If you are running the above code it will take around one second, meaning we will process around one picture per second. If you are running MTCNN on a GPU and use the sped-up version it will achieve around 60–100 pictures/frames a second. That is a boost of up to 100 times!
If you are for example going to extract all faces of a movie, where you will extract 10 faces per second (one second of the movie has on average around 24 frames, so every second frame) it will be 10 * 60 (seconds) * 120 (minutes) = 72,000 frames.
Meaning if it takes one second to process one frame it will take 72,000 * 1 (seconds) = 72,000s / 60s = 1,200m = 20 hours
With the sped-up version of MTCNN this task will take 72,000 (frames) / 100 (frames/sec) = 720 seconds = 12 minutes!
To use MTCNN on a GPU you will need to set up CUDA, cudnn, pytorch and so on
Once installed we will do the necessary imports as follows:
 
The above image shows the output of the code running on an NVIDIA Tesla P100, so depending on the source material, GPU and processor you might experience better or worse performance.
Extracting all images seperately 
 

Conclusion
Face recognition is an emerging technology that can provide many benefits. Face recognition can save resources and time, and even generate new income streams, for companies that implement it right.
What lies ahead for this technology?
It’s difficult to be certain. Some experts predict that our faces will replace IDs, passports and credit card pin numbers. Given the fact how convenient and cost-effective this technology is, this prediction is not far-fetched.
If this prediction becomes a reality, any company that implemented the technology today might gain a competitive advantage in the future.
What the Future Holds or future scope?

The future of facial recognition technology is bright. Forecasters opine that this technology is expected to grow at a formidable rate and will generate huge revenues in the coming years. Security and surveillances are the major segments which will be deeply influenced. Other areas that are now welcoming it with open arms are private industries, public buildings, and schools. It is estimated that it will also be adopted by retailers and banking systems in coming years to keep fraud in debit/credit card purchases and payment especially the ones that are online

Reference 
-Towards machine learning blogs
- Some Github repository
