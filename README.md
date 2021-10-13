# M. Reilly's Written Report on the Neural Network Model working with Beks 

## Project Overview 
### Background and Purpose


At Alphabet Soup, our coworker Beks has been trusted to develop the best possible models, and Beks puts in the work to make sure Andy has the information he needs to make decisions. In an effort to help Beks model shine even more, we accepted a project to try a neural network model given the complexity of the dataset especially because of the ammount of features availible. She had gotten 89% accuracy but wanted to do better, we thought the multiple-neuron neural network (nn) model would be more apt for this kind of data and to meet her desired performance level.


In addition to this written report, this repository documents the main sections of the project : (1) the processing stage, which entailed dropping certain ID columns, encoding catagorical data, and scaling values; (2) code that reflects compiling and training of the neural network model, and (3) repeated attempts at optimizing models and .h5 weight files in a checks folder.

## Results: Using bulleted lists and images to support your answers, address the following questions.

### Data Preprocessing
##### What variable(s) are considered the target(s) for your model?
Classification and Application were both made into bins, but actually that is to remain a more simplifed feautres (less unique values). It was the "'IS_SUCCESSFUL" category that is the main target, dropped repeatedly from the features when establishing X for data split, and then refered to as Y in same cell(s).

##### What variable(s) are considered to be the features for your model?
Cheifly, anything except EIN and NAME. But during different attempts I tried to focus that list of features further so not to pass 9. 

##### What variable(s) are neither targets nor features, and should be removed from the input data?
Per deliverable 2, we dropped 'EIN' & 'NAME' since both columns had an enourmous ammount of unique values that were hyper specific and unessarily complex, and ultimately the inclusion of them would be a hindrance and not a help to the outcome being sought out. These values consistuted neither a target (outcome) or feature (input). 

### Compiling, Training, and Evaluating the Model
#### How many neurons, layers, and activation functions did you select for your neural network model, and why?

I randomly tested via brute force a ton of options at first. Then I considered rough estimates of 2-4 hidden layers.  
I tried to follow the rule of thumb for a basic neural network that suggests to have two to three times the amount of neurons in the hidden layer as the number of inputs. This meant to consider the length of the new imputs after dropping or readding columns/features/inputs. 

Also, I often chose around 100 epochs and no more than 150 in the interest of time. With past examples I encountered it seemed that models reached optimal performance at around 100 epochs, so I focused around that number. I remembered one example that had a .07% increase in accuracy after adding layers and up to 500 epochs on Tensor Flow. Still, the second part of going to 500 epochs was time consuming, so I left that for the end, which only yeilded 55% accuracy after all. 
![Screen Shot 2021-10-13 at 12 07 07 PM](https://user-images.githubusercontent.com/82982952/137171953-0d5c26bb-0ac3-4b7a-8054-3b7557f03e4d.png)

#### Were you able to achieve the target model performance?
No, I was not able to acheive the target model preformance of 75% or above. 
#### What steps did you take to try and increase model performance?
In attempting to increase my accuracy, (1) I changed (mostly increasing) the number of epochs, (2) added a number of hidden layers, (3) dropped more columns, then (4) added some dropped columns back, (5) changed layer type (e.g. relu to sigmoid), and (6) changed the optimizer type. I noticed that less layers seemed to do better and the first layer having about 2 to 3 times more imputs than the second hidden layer seemed to produce better accuracy measures. 

## Summary 

The highest accuracy value I could get during my attempts was ~69%, but most of the attempts yeilded an accuracy value in the 50th percentile. This kind of score does not produce confidence in our model. I have to believe that despite numerous attempts and efforts to process the data better and tweak optimizations, the data was probably still being overfitted. For this reason, I'd probably recommend a switch to ensemble classifying models, a RandomForest classifier. 

The RandomForest Classifier, a tree grouping/branching supervised learning classifier uses averaging methods and is known to reduce variance and overfitting. While generally speaking it is said that the RandomForest model could could be less efficient than other classifiers and may be further limited in auto-determining the significance of each variable since its model is creating a bias, I think compared to the neural network option here, it would have been more efficient for a number of reasons. First, it would eliminate the need to repetitively hand tweak optimizing features when working in tandem with other methods/models, as it would mostly, if not fully, avoid overfitting in the first place. Second, although we chose deep learning because we believed other machine learning models were unable to meet desired performance or analyze the complex dataset we had, we were unable to come up with a better outcome of good preformance with the deep learning nn model. So, then we mmust accept that after dropping numerous features as done in the various optimizing efforts, we could probably gain a high accuracy outcome using a simplier random forest classifier, or some other bagging classifier. We originally had a model worked 89% of the time, and even though Beks hoped to get it better with a nn model, that was not our outcome. So obviously, if left to choose right now between 50-70% accuracy or 89% accuracy, our team should choose the latter. Random Forest has higher interpretibility abilities than deep learning models, but still supposed the be around the same or higher accuracy. Thus a lightweight option is possible here, and as we concluded prior, "neural networks are not the ultimate solution to all data science problems."
