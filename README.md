# Python-mini-research-projects
In this repository I reproduced the results of the paper [1] Juan Carrasquilla and Roger G. Melko, Nature	Physics 64,	063810	(2001) "machine learning phases of matter". 
    The starting point was the Ising model and the first task is to produce Monte Carlo simulations for the
total magnetization as a function of temperature for a square lattice. These data
were then used to train a fully forward neural network to perform supervised learning of the
thermalised and uncorrelated raw configurations sampled by the Monte Carlo simulation

###### LATEST COMMIT #########

Changed the FCN to be more like the one specified in the paper. Appropriately gave better results with the following parameters

"The neural network is composed of an input layer with values determined by
the spin configurations, 100-unit hidden layer of sigmoid neurons, and an analogous output
layer. We use a cross-entropy cost function supplemented with an L2 regularization term
to prevent overfitting. The neural network is trained using the Adam method for stochastic
optimization"

####### FILE LIST ###########
1. Create Ising training and test data.ipynb
2. file pre-processing.ipynb
3. Machine learning FCN.ipynb
4. Toy_model.ipynb

####### USER GUIDE ##########
Make sure all .ipynb files are in the same repository.
- Open the create Ising training and test data.
  * change the high temperature and low temperature limits(T_high/T_low) as needed
  * determine number of thermalisation steps, samples and number of starting configurations
  * specify what Lattices you desire and of what size e.g L = [10,20,30,40,50,60]
  * now run the code block. The current version of this code is not optimised so here is a short table of times vs lattice sizes
  * 
     | lattice sizes | Time taken for simulation( 26 samples, 1000 starting configurations, 200 thermalisation steps )|
     
     |      10       |     48 minutes
     
     |      20       |     48 minutes
     
     |      30       |     1hrs 51 minutes
     
     |      40       |     3hrs 14 minutes
     
     |      50       |     5hrs 8 minutes
     
     |      60       |     8hrs
     
     This was on the cpu of a HP pavilion laptop 15-eh0xx
- now run the file pre-processing ipynb and change splitting segments for training and test sets if necessary
- Run the machine learning FCN ipynb and obtain the required graphs. The model can be tailored as necessary, the rest shouldn't require tweaking
- Run the Toy_model.ipynb and obtain the required graphs. no tweaking or modification should be necessary

##### extra #########
I have added sample datafiles(as .npz in the format lats=lattices, temperatures=temperatures) files to the folder so the user may download and play around with the fully connected neural network without having to run the ising model code for new configurations. 
So if one uses these files, you can start from the pre_processing step. Sample files are for lattices 10,20,30,40,50,60
