Download Link: https://assignmentchef.com/product/solved-ml-assignment1-distance-weighted-nearest-neighbour-algorithm-for-regression
<br>
<h1>Distance Weighted Nearest Neighbour Algorithm for Regression</h1>

You should use the training and test file from the <strong><u>regression folder</u></strong> in data.zip for Part 1.

In the regression folder you will find a training and test csv file. There are 12 features in the dataset. There are 6400 instances in the training set and 1600 instances in the test dataset. The target regression value is the final column in each dataset (13<sup>th</sup> column).

Part 1(A) – Development of Distance Weighted k Nearest Neighbour Algorithm for Regression (25 Marks)

Your objective is to build (from the ground up) a distance weighted k-NN regression algorithm.

The k-NN algorithm you develop should:

<ul>

 <li>Use Euclidean distance for calculating the distance between query instances and the instances in the training data.</li>

 <li>Use the inverse distance as the weight.</li>

 <li>Assess the performance of your kNN regression algorithm using R<sup>2</sup> as your evaluation metric.</li>

</ul>

As already mentioned you <strong><u>should not be using imported functionality</u></strong> from Scikit Learn (or similar packages) for implementing the kNN (or the R2 metric) but should instead implement it in core Python or NumPy.

As part of the code for your k-NN implementation you should include the following:

<ol>

 <li>A function called <em>calculate_distances</em>. The primary objective of this function is to calculate the Euclidean distances between a <u>single query point</u> in feature space and a collection of other data points in feature space (your training instances). The distance formula you should use is the standard Euclidean distance</li>

</ol>

The function <em>calculate_distances</em> should accept as arguments a single NumPy 2D array containing all the feature training data as well as a 1D NumPy array, containing a single

query instance (please note that no ‘for loops’ should be used in this function). Also, you should not implement the Euclidean distance using any high-level functions. You should

only be using basic NumPy operations such as summation, subtraction etc (you should not

be using higher level functions such as numpy.linalg.norm).

The function should return a NumPy array containing the distance from the query point to         each of the individual training data instances.

<ol start="2">

 <li>A function called <em>predict</em> that will accept as arguments a NumPy 2D array containing all the feature training data as well as a single 1D NumPy array, containing a query instance. The function should return the predicted regression value for the query instance (This function will need to call the <em>calculate_distances</em> You may also may find <a href="https://numpy.org/devdocs/reference/generated/numpy.argsort.html">np.argsort</a> useful when coding the <em>predict</em> function).</li>

</ol>







<ol start="3">

 <li>A function called <em>calculate_r2</em>, which will take in two NumPy arrays. The first array will contain the true target regression value for all test instances and the second array will contain the predicted regression values (predicted by your model) for each test instance. The function should calculate the R<sup>2 </sup>performance of your model.</li>

</ol>




Include a copy of the above 3 functions in your report document. Once you have completed your implementation include the R<sup>2</sup> value achieved by the model for k=3 into your report document.




<table width="667">

 <tbody>

  <tr>

   <td width="667"><strong><u>Checklist for Part 1(A)</u> </strong> Your report should contain the following:•      The final R<sup>2</sup> performance of kNN for K= 3•      Your implementation of the function <em>calculate_distances</em>•      Your implementation of the function <em>predict</em>•      Your implementation of the function <em>calculate_r2</em>Your submitted zip file should contain the full code entitled Part1A.py (If you are using Jupyter notebooks that you name your notebook PartA). <strong>Please note a failure to include the above material in your written report (or a failure to include these functions as named and described above in your code) will incur a penalty.  </strong> </td>

  </tr>

 </tbody>

</table>

<h2>Part 1(B) – Parameters/Techniques Impact Model Performance (25 Marks)</h2>







“<em>By default, a k-NN algorithm will weigh the contribution of each feature equally when using standard Euclidean distance</em>”. In your report document clearly explain your understanding of this statement (why this is the case and how it could negatively impact the performance of your k-NN model).




Research and present a range of possible methods for tackling this issue in your report. Incorporate one of these methods into your code and assess the impact.




Please take note of the following two points:




<ul>

 <li>To score well in this section you should expand your research beyond the techniques presented in the lecture notes and support your answer with references where possible. You should clearly explain all techniques presented.</li>

</ul>




<ul>

 <li>Incorporate one of these methods in your code and present the results. Please note <strong>it is acceptable to use a high-level toolkit for this section</strong>.</li>

</ul>







Aside from the above there are a range of other techniques/parameters that you can investigate that could potentially impact the performance of k-NN regression algorithm. Describe the set of techniques/parameters and why they may potentially impact the performance of a kNN.




Select two of these technique/parameters and comprehensively investigate their impact on the performance of your model.




<table width="667">

 <tbody>

  <tr>

   <td width="667"><strong><u>Checklist for Part 1(B)</u> </strong> Your report should contain the following:•      Your understanding of the statement “<em>By default, a k-NN algorithm will weigh the contribution of each feature equally when using standard Euclidean distance</em>”•      A detailed account of the research you undertook into a range of possible methods for addressing this problem.•      A detailed description and assessment of the impact of incorporating one of these researched techniques.•      List and describe the techniques/parameters that can potentially impact the performance of a kNN.•      Assessment of two selected techniques/parameters on your model performance.Your submitted zip file should contain the full code entitled Part1B.py (Please note if you are using Jupyter notebooks that you name your notebook Part1B).</td>

  </tr>

 </tbody>

</table>




<h1>Part 2 – Development of KMeans Clustering Algorithm (50 Marks)</h1>

You should use the feature dataset from the <strong><u>clustering folder</u></strong> in data.zip for Part 2.

In the cluster folder you will find a csv file containing just feature data. There are 6 features in the dataset. There are 10000 instances.

<h2>Part 2(A) – Development of a KMeans Clustering Algorithm (30 Marks)</h2>

The objective of this section is to develop a random restart KMeans clustering algorithm using Python and NumPy. As already mentioned you should only use NumPy and Python in your code.

The KMeans algorithm you develop should reuse the <em>calculateDistances</em> function from Part 1. It will be used for calculating the Euclidean distance between all training instances and a single centroid in feature space.

Your solution should contain the following functions:

<ol>

 <li>A function called <em>generate_centroids</em> that will take in as arguments the feature data and the number of centroids (an integer which we will call k). The function will randomly select k feature instances (k rows of the dataset) and return these as the initial centroids (the k centroids should be returned as a single array).</li>

 <li>A function called <em>assign_centroids</em>, which will take in as arguments the feature data and the current array of centroids. This function should calculate the distance between each centroid and all feature data instances (each of the rows in the dataset). It should return the centroid index that is closest to each individual feature instance.</li>

</ol>

In other words, if we have 3 centroids and 10 feature instances (10 rows in our data set) then this function calculates the distance between each of the 3 centroids and the 10 rows in the dataset. It will then return an array containing 10 integer index values. The first integer value in the array indicates the index of the centroid to which the first feature instance (first row in dataset) is closest. The second integer value in the array indicates the index of the centroid to which the second feature instance is closest and so on.

So in the example above, if <em>assign_centroids</em> was to return the following array [<strong>2</strong>, <strong>0</strong>, <strong>1</strong>, 1,

2, 0, 0, 1, 1, 0] this would mean that the first feature instance is closest to the 3<sup>rd</sup> centroid (index 2), the second instance is closest to the 1<sup>st</sup> centroid (index 0), the third instance is closest to the 2<sup>nd</sup> centroid (index 1) and so on.

<ol start="3">

 <li>A function called <em>move_centroids</em>, which will take in as arguments the feature data, an array containing the centroid indices assigned to each feature instance (this is the output of <em>assign_centroids</em>) and the current set of centroids. This function will compute the new position of the centroids (by calculating the mean of the datapoints assigned to each specific centroid) and will return an array containing the new centroids.</li>

 <li>A function called <em>calculate_cost</em> which will take in as arguments the feature data, an array containing the centroid indices assigned to each feature instance (this is the output of <em>assign_centroids</em>) and the current array of centroids. It should calculate and return the current distortion cost function. The distortion cost function can be calculated below.</li>

 <li>A function called <em>restart_KMeans</em>, which will take in as arguments the feature data, the number of centroids (an integer), the number of iterations (an integer) and the number of restarts (an integer).</li>

</ol>

The number of iterations just specifies the number of iterations of the inner loop of KMeans (consisting of assigning centroids and moving centroids). This can be set to 10 for this problem (for this data your algorithm could converge quickly).

The number of restarts is the number of times you will restart KMeans from scratch (generate new random centroids and iterate again through the assign centroid and move centroid steps). Again, we will set this value to 10 for our problem.

The <em>restart_KMeans</em> function will use the function described above (1 – 4) to implement a random restart KMeans algorithm and will return the best solution found over the 10 restarts. More specifically it will return:

<ul>

 <li>The array of centroid IDs that produced the best distortion cost function value (this defines the cluster to which each feature instance belongs). • The corresponding best distortion cost function value</li>

</ul>

As usual marks will be given for an efficient implementation that minimizes duplication and uses NumPy where possible.

Once you have fully implemented the above code, you should use it to produce an elbow plot and describe what you consider to be the most appropriate number of centroids (clusters) for this dataset. Clearly explain your interpretation of the plot and how you selected the appropriate number of clusters (centroids).

<table width="667">

 <tbody>

  <tr>

   <td width="667"><strong><u>Checklist for Part 2(A)</u> </strong> Your report should contain the following:•      Your implementation of the function <em>generate_centroids</em>•      Your implementation of the function <em>assign_centroids</em>•      Your implementation of the function <em>move_centroids</em>•      Your implementation of the function <em>calculate_cost</em>•      Your implementation of the function <em>restart_KMeans</em>•      A picture of the elbow plot you produced and your written interpretation of the elbow plot and your justification for the selection of the appropriate number of clusters (centroids) Your submitted zip file should contain the full code entitled Part2A.py (Please note if you are using Jupyter notebooks that you name your notebook PartB). <strong>Please note a failure to include the above material in your written report (or a failure to include these functions as named and described above in your code) will incur a penalty.  </strong> </td>

  </tr>

 </tbody>

</table>

<h2>Part 2(B) – Researching Alternatives to KMeans</h2>




When dealing with large amount of data, the KMeans algorithm can be quite slow. The number of necessary distance calculations is (<em>n</em>*<em>c</em>*<em>a</em>) where <em>n</em> is the number of feature instances (rows in our dataset), <em>c</em> is the number of centroids and <em>a</em> is the number of iterations (of course this does not consider the issue of random restarts).

A number of alternative strategies have been proposed in literature to improve the performance of the KMeans category of clustering algorithm. A commonly used alternative to KMeans, which is particularly useful when dealing with large amounts of data is called Mini-Batch KMeans.

Research Mini-Batch KMeans and include a detailed description of its operation in your report document. To grade well in this section, you should demonstrate that you clearly understand the operation of this algorithm and demonstrate evidence of research (maximum 2 pages).