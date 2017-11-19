# we-are-not-alone
Exploring the "Science Hack Day Berlin" social network with music and images. A project for the "Science Hack Day Berlin" 2017 hackathon.
The main artifact is the [Jupyter notebook](https://github.com/ellenkoenig/we-are-not-alone/blob/master/Create%20network%20from%20twitter%20(Ellen).ipynb) . 

Dependencies
 * `Python 3.5`
 * `jupyter` for running the notebook
 * `python-twitter` for accessing the Twitter API
 * `networkx` (version 2.0) for the social network graph representation and analysis
 * `matplotlib` for basic graph visualization
 * `audiolazy` & `pyaudio` for sound "visualization"
 
# TEAM  

* Ellen König
* Tom Beutin
* Syennie Valeria

## HOW WE BUILT IT  
We used
 * `jupyter` for running the notebooks
 * `python-twitter` for accessing the Twitter API
 * `networkx` for Social network and graph analysis
 * `matplotlib` for basic graph visualization
 * `audiolazy` for the sound "visualization"

From the Twitter API, we fetched the follower lists for the most recent tweeters using the #shdb17 hashtag and the science hack day attendee twitter list curated by the orga team at https://twitter.com/SHD_Berlin/lists/shd-berlin-2017.
Due to the strict API rate limiting on Twitter's side, we had to run the data collection over night and pause whenever the rate limit was exceeded (the API library we used offers that as a setting). 

We then feed the follower lists into the NetworkX library to create a graph, draw a basic network visualization and compute some per-node social network metrics (betweenness, closeness, in_degree_centrality, out_degree_centrality). The graph was limited to only include follower links between the attendees, ignoring all other followers,

As a last step, we used the computed 4 metrics per attendee to iterate over the graph and turn each tweeter into a sound. We varied the following sound parameters based on the metrics
 * Pitch: Closeness 
 * Length: In_degree
 * Volume: Out_degree
 * Pause: Betweeness

To make the result a bit more pleasant sounding, the pitches were mapped only on sounds from the pentatonic scale.  
