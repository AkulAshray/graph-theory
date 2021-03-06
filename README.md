# Graph Algorithms

1. Breath First Search

2. Depth First Search

3. Topological Sort

4. Dijkstra

5. Prim/Kruskal/Borůvka

6. A* Search

7. Bellman Ford

8. Bron Kerbosch

9. Ford Fulkerson

10. Nearest Neighbor

# Graph Problems

### 1. Maze

Walking out of a maze seems extremely complex in recursion algorithm. In graph theory, it is just a walk in the park. The only bit that takes some effort is building the data structure. Once we got graph ADT, we can use BFS/DFS/Dijkstra/A* to find the way out of the maze, although DFS may not be able to point out the shortest route.

### 2. Minimum Spanning Tree

Consider a case where a postman is going to deliver mails to every house in the community. The distance between each house is completely different, some are shorter, some are longer. Ideally the postman wants to deliver mails to each house with the least travel distance and visit each house only once. There are a few algorithms to solve this type of issue. In this case, we choose Borůvka, Prim and Kruskal. And the topological output of these algorithms can be interpreted as a <a href=https://en.wikipedia.org/wiki/Minimum_spanning_tree>minimum spanning tree</a>. It is a subset of the edges of a connected, edge-weighted undirected graph that connects all the vertices together, without any cycles and with the minimum possible total edge weight.

### 3. Shortest Path

Whenever we look at the phrase, 'shortest path', we should naturally come up with Dijkstra's algorithm in our mind. This Dutchman came up with the revolutionary algorithm named after himself while searching for the shortest path to Rotterdam without pencil and paper. The algorithm is a special case of A* algorithm without heuristic function. It is also widely used as a subroutine for other traversal algorithms. Besides Dijkstra's algorithm, the shortest path problem, which could be thought as an optimization problem, can also be solved in dynamic programming.

### 4. Water Jug

Water jug is a simple and interesting problem. Assuming there are two jugs, a m-gallon and a n-gallon. And the target is to get x gallon water in either jug. There are many ways to solve this problem. Recursion can also solve water jug problem but it is very costly. Building a graph data structure would be a much easier way. The key is to set up edges based upon the rule of the game to connect all possible scenarios together. With BFS starts from the initial status, it can efficiently find the target status and return the route for us which would be the answer.

### 5. Knight's Tour

Knight's tour is a game where a knight travels all the squares on a k by k chessboard. And each square can only be travelled once. The solution can be obtained by DFS with a list that records whether each square on the chessboard has been visited. The rules of a knight's movement are very different from pawns or king. The edges of the graph should indicate the valid move from one square to another.
 
### 6. Missionaries and Cannibals

Missionaries and cannibals is a classic river problem. I actually prefer its alternative version called jealous husband. There are k missionaries and k cannibals. They need to cross a river. There is a boat with the capacity of only two people. There should be at least one person to sail the boat. These rules are subjected to one constraint. Cannibals cannot outnumber missionaries on both sides of the river. Again, the solution is similar to water jug problem. We have to set up edges based upon the rule of the game to connect all possible and valid scenarios together. As usual, BFS always return the optimized result rather than DFS.

### 7. Forex Arbitrage

Finding the shortest path on a map is not the only problem Dijkstra can apply to. Financial market is another application. As we all know, currency pairs have both bid and ask price. The market is weak-efficient. There is always opportunity for triangle arbitrage or rectangle arbitrage. We can exchange from currency A to currency B then to currency C if we can gain profit rather than directly exchanging currency A to currency C. We set each currency as the node, the rate from one currency to another as the edge. And the return from arbitrage would be the criteria for Dijkstra. However, Dijkstra cannot detect the negative return among currency pairs. There is an improved version called Bellman-Ford that can detect the negative cycle during the traversal.

### 8. Word Ladder

Word ladder problem is a game developed by the author of Alice in Wonderland. Given one word, we try to change it into another word. Each time we can only change one letter and it should also be a valid word. This is a great test for vocabulary.  The difficult part of building a graph structure is to build edges. Connect one word to another with only one letter changed takes a bit of work. BFS is the perfect solution for this.

### 9. Text Mining

This is a self made BFS-like algorithm to travel through a graph structure built upon texts. The whole project is designed for <a href=https://github.com/je-suis-tm/web-scraping/blob/master/MENA%20Newsletter.py>MENA Newsletter</a>. The idea is to use graph structure to remove similar contents and extract key information from the texts. I highly recommend folks to take a peep at the project. Machine learning is absolutely not the best solution to text mining. Graph theory sometimes could be much more useful than expected. As usual, my own creation goes under a separate folder. The parent directory is for the self implementation of well-recognized algorithms. 

![alt text](https://github.com/je-suis-tm/graph-theory/blob/master/Text%20Mining%20project/preview/wordcloud.png)

More details can be found at the following <a href=https://github.com/je-suis-tm/graph-theory/blob/master/Text%20Mining%20project/README.md>link</a>.

### 10. K Core

K core, also known as k degenerate, is a subset of the original graph in which all vertices have degree at least k. By some definition, k core is required to be a connected graph. The standard algorithm to find a k core graph is to remove all the vertices that have degree less than k. We must be careful that removing a vertex reduces the degree of all the vertices adjacent to it, hence the degree of adjacent vertices can also drop below k. And thus, we may have to remove those vertices as well.

### 11. Maximal Clique

A <a href=https://en.wikipedia.org/wiki/Clique_(graph_theory)>clique</a> is a subset of vertices of an undirected graph such that every two distinct vertices in the clique are adjacent. A maximal clique is a clique that cannot be extended by including one more adjacent vertex, meaning it is not a subset of a larger clique. Think of maximal clique as a maximum social group where everybody knows each other. Finding a maximal clique is an <a href=https://en.wikipedia.org/wiki/NP-completeness>NP-complete</a> problem. <a href=https://en.wikipedia.org/wiki/Bron–Kerbosch_algorithm>Bron–Kerbosch algorithm</a> with degeneracy ordering is the most efficient way to find out all maximal cliques. Its time complexity can be optimized to O(3**(n/3)).

### 12. Epidemic Outbreak

### 13. Portfolio Optimization

&nbsp;

*Note that I mainly use Jupyter in this repo for the purpose of graph ADT visualization. However, ipynb takes longer to load compared to py files. That is why I also include a py version with graph ADT and all related algorithms for your reference.*

