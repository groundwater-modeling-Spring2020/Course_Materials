# Final Project
____
## Table of contents
1. [ Assignments](#assignments)
1. [ Groups](#groups)
1. [ Domain Description](#domain)
1. [ Scenarios](#scenarios)
1. [ Baseline Ensembles](#ensembles1)
1. [ Advocacy Models](#advocacy)

____
<a name="assignments"></a>
# Assignments
1. **Scenarios 1-2 (Thursday April 16)**  - *GroMore pressenting*
    - Before getting started each group should make a GitHub policy for collaboration.
    - Each group should complete scenarios 1-2 in your shared github repos
    - Submit 1 report for your group and 1 jupyter notebook that sumarizes your findings
    - Group discussion leaders should also submit a ppt presentation for the discussion
1. **Scenarios 3-4 (Tuesday April 21)** - *FoE presenting*
  - Each group should complete scenarios 1-2 in your shared github repos
  - Submit 1 report for your group and 1 jupyter notebook that sumarizes your findings
  - Group discussion leaders should also submit a ppt presentation for the discussion
2. **Scenarios 5-6 (Thursday April 23)** - *Town of Aquaseca presenting*
  - Each group should complete scenarios 1-2 in your shared github repos
  - Submit 1 report for your group and 1 jupyter notebook that sumarizes your findings
  - Group discussion leaders should also submit a ppt presentation for the discussion
1. **Ensembles (Tuesday April 28)**  
4. **Advocacy models (Tuesday May 6)**


____
<a name="groups"></a>
# Group Information 
You have been divided into three stakeholder groups:
1. **GroMore Industries**: Amanda, Justin, Tesfa, Vivek
   - https://github.com/groundwater-modeling-Spring2020/GroMore_Project
2. **Friends of the Environment**: Ben, Danielle, Jake
   - https://github.com/groundwater-modeling-Spring2020/FoE_Project
3. **The Town of Aguaseca**: Abe, Rachel, Dave
   - https://github.com/groundwater-modeling-Spring2020/Aguaseca_Project

You will perform two functions for your group.  First, you will try to put yourself in the minds of your stakeholder - to look at the proposed agricultural activity from their (biased) point of view.  Second, you will act as consulting hydrogeologists for your stakeholder - helping them to bring scientific analyses to their decision making process.

**GroMore** is proposing to start a new agricultural effort in the basin.  Their proposal is included in the base model as the rectangular irrigated area with the elevated ET and the shallow pumping well.  They are resistant to changing this plan (location of the farm, crop, location of pumping well, etc) because they have agreements with the current landowner and have done a market analysis based on the proposed pumping and the projected value of the crop.

**Friends of the Environment** is interested in preserving the Green River and its adjacent riparian area.  They are concerned that the added pumping proposed by GroMore may reduce flow in the river and/or contribute N to the river, threatening a sensitive local water strider.   They are also concerned that lowered water levels may impact the riparian ecosystem.

**The Town of Aguaseca** is concerned that the proposed GroMore activities will affect the cost of operating their supply well (located in the lower aquifer) and/or degrade the quality of the town's water supply.  On the other hand, the town generally supports agriculture in the basin.

I will serve as the **Environmental Protection Agency** which has just been notified of the GroMore proposal.  At this point, they do not have any specific concerns.  But, they are examining the application for any possible negative impacts of the proposed activities on the environment of the basin.  They have ultimate regulatory jurisdiction and must approve the new activity.

____
<a name="domain"></a>
# Domain Description
The model should have 50x50 cells, each 1000 m in x and in y.  The porosity is 0.10, specific yield is 0.10, and storage coefficient is 0.0001.  There are three layers.  The medium is homogeneous within each layer.  The K of the top and bottom layers is 10 m/day in all three principal directions.  K of the middle layer is the same as the lower layer in the leftmost 20 columns, but it is 0.0001 m/day in the z direction in the remaining columns. The bottom of the domain is topographically flat and the bottom layer is 40 m thick.  The middle layer is 5 m thick and is also flat.  The top layer elevation is provided in an Excel file below.   The top left and bottom left corners of the domain are 'rounded' by bedrock.  Specifically, in the top, there is a triangle of no flow cells (added under BCs) extending from row 45, column 1 to row 50, column 6, inclusive, comprising a total of 21 no flow cells.  There is a symmetric no flow region in the top left corner.  The middle layer has similar regions extending from row 43, column 1 to row 50, column 8.  The bottom layer: row 41, column 1 to row 50, column 10.

The right boundary in all of the layers has a constant head of 70 m relative to the datum, which is located at the bottom of the domain. All other boundaries are no flow.

Recharge occurs at a rate of 4E-5 m/day in the leftmost 15 columns and is zero elsewhere.  

A stream extends from the left to the right boundary in row 26.  The stream width, length, and thickness are 1.0.  No flow is entering the stream (from tributaries).  

The K of the streambed is 1000 m/day The streambed elevation is 1.0 m below ground surface and the stage is 0.5 m.  

The stream is a 'weak sink' with a strength of 0.5, meaning that half of the particles that enter a stream cell are captured by the stream.  (This is set under MODPATH/Particle Options.).

ET is zero in the left half of the domain.  ET is 1E-5 m/day in the right half of the domain.  ET occurs at a rate of 5E-5 m/day in a riparian area that extends from the left boundary to the right boundary and occupies rows 23 to 29, inclusive.  The extinction depth is 10 m everywhere.

There is a well that is used for water supply by the local community, which is completed in the bottom layer at row 21 and column 38.  It is pumped at a rate of 1500 m3/day.  

The description above defines the system before a proposed new agricultural project is realized.  The ag field is proposed to cover a 2000 m by 2000 m area; 1/8th of the area will be irrigated agriculture at any time (the field area is multiplied by 0.125).  The rectangular irrigated fields extend between rows 21 and 22 (inclusive) and columns 19 and 20 (inclusive).  

ET for the crop is zero - it is accounted for in the calculated recharge beneath the field. The recharge rate is assumed to be 20% of the water demand of the crop, representing intentional excess irrigation to avoid soil salinization.  The water uses of wheat, pistachios, and cotton on a daily basis are: 0.004; 0.006; and 0.008 m/day.  This leads to recharge rates of (e.g. 0.004 * 0.125 * 0.2 = 0.0001): 0.0001, 0.00015, and 0.0002 m/day for these crops, respectively.

Water is provided for irrigation from a well that is completed in the top layer at row 12 and column 14.  The pumping rate is equal to the crop water demand plus 20% for excess irrigation plus 30% for irrigation inefficiency.  For wheat, the pumping rate is 0.004 *0.125 * (1.0+0.2+0.3) * 2000 * 2000 = 3000 m3/day).  The resulting pumping rates are: 3000; 4500; and 6000 m3/day for wheat, pistachios, and cotton, respectively.  

Add two ‘monitoring wells’ to monitor the transient conditions.  Both should be in layer one, one at [25000, 25000] and the other at [12500, 12500].

For simplicity, we will consider a year to be comprised of 12 30-day months.

____
<a name="scenarios"></a>
# Scenarios

### Scenario 1: Pre Development model, no seasonality
Build the base model as described above without the proposed agricultural activity.  
- Run the model as steady state with no pumping from the town's well.  
- Calculate the flux from the stream to the groundwater
- Also show a reverse particle track map to identify the source of the water to the stream.  
- Finally, report the water level at the monitoring wells and at the town's well (even though it isn't pumping for this scenario).

### Scenario 2: Pre development model with seasonality
Build the base model as described above without the proposed agricultural activity.  
- Run the model as transient for 25 years with no pumping from the town's well.  Recharge occurs at a constant rate all year, but ET takes place from April through September (inclusive) at the rate given in the problem description.
- How long does it take for the model to reach a cyclical steady state (annual variations, but no trends)?  Use monthly water levels at the monitoring wells to support your conclusion.  This is the required 'burn in' time of your model.   

### Scenario 3: Post development with seasonality
Build the pre-development model with seasonality and extend the run time to 100 years PLUS your burn in time.  This represents the 100 years that the town has been pumping to date.  There was no pumping during the pre-development period.  The town's water demand has increased exponentially, with the pumping rate changed every 10 years following the equation: Q = 1.5 * t^1.5, for Q in m3/day and t in years.  To avoid confusion, the pumping rate is zero for for the burn-in time (I'll assume 25 years, here).  Then, on April 1 of year 25, the pumping increases to 47 m3/day.  On April 1 of year 35 it increases to 134 m3/day.  Then, on a 10 year schedule, it continues to: 246; 379; 530; 697; 878; 1073; and 1281 m3/day.  This model defines the system at the current time - remember, the town has been pumping for 100 years already.

### Scenario 4: Post development with seasonality, future projection
Project your post-development model with seasonality an additional 100 years into the future.  (Remember to project the town's water demand, too!)
-  Compare this model with your pre-development model with seasonality.  
- How can you quantify the impacts of the town's water extraction on the hydrologic system?  Describe your metrics as precisely as you can and quantify the impact(s).

### Scenario 5: Post agriculture model with seasonality - future projection
Add the proposed agricultural element (pumping and localized recharge) for growing pistachios to your post-development model with seasonality.  Agriculture starts now, 100 years after the end of the burn-in.  Both pumping and recharge related to agriculture occur at the rates described and are continuous throughout the year.  
- How can you quantify the impacts of the proposed agricultural element on the hydrologic system 100 years into the future?  
- How do these impacts compare with the impacts of the town's pumping?  
- How will the agricultural element affect the town's ability to meet its water demand (both for quantity and quality?)  Describe your metrics as precisely as you can and quantify the impact(s).

### Scenario 6: Is seasonality necessary
Moving forward, we will be running more models to try to decide whether to allow the agricultural activity and/or whether to propose changes to its design.  Whenever you are faced with running many models (or calibrating a model), it is worth considering carefully whether the model can be simplified.  Can we justify ignoring seasonality in ET?  If so, we could use a constant rate which would make our model less dynamic and probably faster-running.  But, we want to make sure that we don't misrepresent any important impacts of the farm.  Consider the question of ignoring seasonality from the point of view of four stakeholders: the agricultural company proposing the new facility, the town, a local environmental group, and the Environmental Protection Agency.  Provide a one paragraph support of your position.


____
<a name="ensembles1"></a>
# Baseline Ensembles

A model is comprised of many elements: abstractions on different levels.  We will refer to a group of related models as a model ensemble.  There are many types of uncertainty that can be represented with an ensemble of models, including:
 - *Conceptualization* - deciding which processes should be considered and which can be ignored for your specific modeling objectives.  Further, deciding how to represent processes, at which scale, and with what level of resolution.  This may include boundary condition types;
 - *Parameter uncertainty* - deciding on a reasonable range of values for parameters, boundary conditions, and stresses applied to the system.  This may include the location of applied stresses (decision variables);
 - *Spatio-temporal complexity* - deciding how much spatial variability to include in defining processes, properties, boundary conditions, and applied stresses.  Also, deciding whether it is important to consider outcomes through time or if steady-state is sufficient for the questions at hand.


We will limit ourselves to considering parameter uncertainty for now.  We will also be sharing model results, so we will all work from a common base model.  What will change is the parameter values. Each group will consider the impact of the proposed agricultural facility on the post-agriculture water level in the town's well.  Consider the following settings:
1. K of the upper and lower layers (isotropic) and horizontal K of the middle layer (all of this is one value),
1. Vertical K of the middle layer
1. Specific yield,
1. Mountain recharge rate,
1. Valley ET rate,
1. Riparian ET rate,
1. Streambed K

This is seven settings that you could change.  Think of each of these as having a high, medium, or low value (given below).  

 - K1 and K3 = [5, 25, 100]               # baseline Kx=Ky=Kz value in all zones (m/day)
 - Kzratio_lowK = [1e-6, 1e-2, 1]          # ratio of Kz in low-K layer to baseline K (-)
 - Sy = [0.05, 0.1, 0.3]                                 # specific yield (-)
 - R_mountains = [1e-5, 3e-5, 5e-5]       # recharge rate in mountains (m/day)
 - ET_valley = [1e-6, 1e-5, 1e-4]               # ET rate in valley (m/day)
- ETratio_riparian = [1, 2, 3]                    # ratio of ET in riparian area to  ET rate in valley (m/day)
 - Kratio_streambed = [1e-2,1e-1, 1]       # ratio of K in streambed to baseline K (-)


To organize our thinking about different model scenarios we are going to use teh concept of a model tree. If we define a set the number of elements (ne) to be varied (you are considering 7) and the number of different values (nv) for each element (in this case we have three values: 0 = lowest; 1 = middle; 2 = highest), we can define the total number of possible models as ne^nv.  You have 343 models to choose from.  To keep track of the models, you can name them based on its element values, in order.  For example, a model with low values for every variable but high value for riparian ET would be  named model_1111131 and a model with  average values for the two conductivity parameters but low values for the rest would be model_2211111.  Thus, the name directly defines the values of each parameter.  It also describes the relationship between that model and other models.   This requires that we define the elements to vary and THE ORDER that they are listed in the model tree.  We also have to determine the number of values and the specific values for each element.  The order of the parameters. Follow the  ordering above and the prescribed high medium and low values for your model.  Be sure to familiarize yourself with them and ask questions if anything is unclear.  

#### Instructions:
1. As group propose 10 combinations of the parameters listed above that you think will lead to the 'most different set' of predicted levels of drawdown in the town well.  Your goal is not to choose sets of parameter values that lead to the highest or lowest impacts.  Rather, you want to define models that are 'most different from each other' with respect to this prediction of interest. This exercise is designed to start you thinking about building model ensembles.  First, why would we want to have models that represent the range of outcomes of interest rather than just the extremes?  Second, how do we decide which settings to vary?  Third, related to the first, why don't we just vary everything?

1. BEFORE YOU RUN ANY MODELS: create a table with 10 rows and eight columns (one for each of the key settings that you identified + one for model name).  Each row represents one model.  Enter  +, 0, or - to choose the high, medium, or low value of each setting in your table.  Then, add another column and enter your estimated ranking of the models based on the post-agriculture water level in the town's well: 1 = minimum drawdown, 10 = maximum.  

3. Draw your model tree and think about the models that you have chosen in terms of their placement on the model tree (use the order of parameters that I gave you).  Does the location of a model on the tree help you to determine how 'different' they are from one another?

 4. Modify your Jupyter notebook so it can easily run different scenarios. I recommend setting it up so that you can give it a list of 7 numbers like this: scenario=[1,1,2,3,1,1,1] and it will correctly choose the correct parameter values and name your model accordingly.

4. Now run the model for your 10 scenarios and look at your predictions and the actual model results.  How well did you do?  Try to explain two of your 'worst' mistakes (assuming that you didn't get the ranking perfect).


#### What to submit
Please email submissions 1 & 2 to me by the start of class so I can add to the course material repo
1. Your table of scenarios as an excel workbook
2. One ppt presentation per group that summarizes your simulations and includes:
   - A brief explanation of how you chose which settings to include and how you decided on the model rankings.
   - A discussion of how well you did
   - Examples and explanation of two of your 'worst mistakes'
3. One Jupyter notebook that includes your simulations (Its also fine if you have your analysis in a separate Jupyter notebook but they should be easy to follow).
3. The discussion leaders for this week will create a  google sheet and share it with everyone in the class.  There should be a column for stakeholder name, model number (see above), and the -/0/+ setting for each parameter.  Finally, add a column for the post-ag water level in the town's well and enter your result. Every group should enter their results into the sheet

### Additional Discussion questions
- Each group will have run 10 models, leading to a class-wide ensemble of 30 models - assuming no redundancy.  This will sample less than10% of the possible models  How can we be sure that we have a reasonable representation of the range of different models?  Is this important?
-  What is a good metric of 'model difference' if your goal is to establish an ensemble that represents the range of models?  
- How can you use the model tree structure to select the models to run?  Do you need to have a prediction of interest to define 'differences' among models?  
- Is there any role for just randomly selecting model parameters?  
- If you do, what is the difference between Monte Carlo and Latin Hypercube sampling?    


#### Note
We are entering a new domain, here.  There is no key against which to compare your models.  It is up to you to decide if your models look hinky (technical term of art meaning that something seems to be wrong but you don't know what, exactly).  Moving forward, others will rely on you to do three things: describe your model inputs clearly and correctly; name your model in a way that it can be retrieved and used efficiently; and run the model that you described.

​____
<a name="advocacy"></a>
# Advocacy Models
Coming  soon
