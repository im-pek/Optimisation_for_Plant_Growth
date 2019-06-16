# Optimisation for Maximum Plant Growth
Achieve optimal plant growth through derivation of best growth recipe (i.e. input growth parameters) using Genetic Algorithm and Modelling (e.g. Linear Regression) methods. Data sends to & retrieves from AWS' DynamoDB; the latter is a centralised system for IoT integration between controls & sensors, for an integrated smart plant growth system.

#GeneticAlgorithm #Optimisation #PlantGrowthModelling

# Instructions for Integration
To integrate or modify this set of code, focus attention on comments in the code which are capitalised.

For integration with growth scores obtained and calibrated from computer vision components, focus on editing all lines with comments which write '#GROWTH VALUE HERE'.

This set of code calls on two different AWS DynamoDB Tables, and adds / updates items in these tables. The creation of these tables prior to the development of this set of code was done using simple AWS DynamoDB upload table formats (at the point of creation of the tables, in which one does not need to specify and create all attributes yet; creation of just one attribute is sufficient at the point of table creation [make sure that its 'KeyType': 'HASH']).

The current Hashed Attribute for OptimisationHistory table in AWS DynamoDB has the column name 'EpochTime', and that of LatestOptimisation table is 'ID' (which has only one fixed ID value of '1', that should never change).

The ultimate objective of these processes is for a user to be able to run a round of Optimisation and get the best recipe at that point in time, with a single click (or not even needing to click, for it is possible to automate initialisation of various Optimisation rounds by setting some sort of timer [ctr + F 'timer' in the code; commented out]). This current set of code re-runs automatically once a single run is initiated. Comment out the 're-run' part (ctrl + F it too) to enable manual re-runs. The magic phrase for re-run after that is done, is 'yes'.
