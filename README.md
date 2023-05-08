Download Link: https://assignmentchef.com/product/solved-the-game-of-pig
<br>
The game of Pig is played between two people who take turns rolling a pair of six-sided dice. The goal is to accumulate 100 points in your bank before your opponent does. On each turn, a player may roll the dice multiple times, accumulating a running sum of turn points. After each roll, the player must choose to pass the dice to the other player, banking his/her accumulated points for that turn, or to roll again (be a pig) in an attempt to accumulate more points. However, if a one is rolled on either die, the player forfeits all points accumulated during that turn and must pass the dice to the other player. If both dice show a one (snake eyes), the player forfeits all points accumulated up to that point in the game and must pass the dice to the other player.

For this project you will write a complete Java program that allows a human player to play a game of Pig against the computer. This program will be text-based, following a general flow of interaction similar to the example below.

<h3><a id="user-content-sample-interaction" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Pig%20Game#sample-interaction" aria-hidden="true"></a>Sample Interaction</h3>

<pre><code>Player's name? John    [ After a couple of turns ... ]John's turn.      Points: 0     Bank: 25    Roll: 3 + 4 = 7     Points: 7     Bank: 25    Roll again? y    Roll: 6 + 3 = 9     Points: 16    Bank: 25    Roll again? y    Roll: 4 + 4 = 8     Points: 24    Bank: 25    Roll again? n    Passing.            Points: 0     Bank: 49Computer's turn.  Points: 0     Bank: 38    Roll: 4 + 6 = 10    Points: 10    Bank: 38    Rolling again.    Roll: 5 + 2 = 7     Points: 17    Bank: 38    Rolling again.    Roll: 6 + 5 = 11    Points: 28    Bank: 38    NOT rolling again.    Passing.            Points: 0     Bank: 66John's turn.      Points: 0     Bank: 49    Roll: 5 + 2 = 7     Points: 7     Bank: 49    Roll again? y    Roll: 3 + 1 = 4     Points: 0     Bank: 49    LOSE TURN POINTSComputer's turn.  Points: 0     Bank: 66    Roll: 1 + 1 = 2     Points: 0     Bank: 0     LOSE ALL POINTS</code></pre>

Note: The exact formatting details of your output (spacing, indentation, punctuation, etc.) do not need to match this example exactly. Instead, this example is provided for illustration purposes only. The output requirements are described below in terms of the information that must be presented.

<h3><a id="user-content-design" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Pig%20Game#design" aria-hidden="true"></a>Design</h3>

As in the last assignment, Most aspects of the design of this program are left to you, but make sure you embrace the criteria described in the Program Grading Rubric. Decompose your solution in a logical manner. Consider carefully re-reading the game description and identifying the nouns, choosing which ones make the most sense to use as classes. Carefully assign responsibilities to classes and design methods that perform specific tasks.

You must create a class called Pig that contains your main() method. Your main() method should not contain any significant logic, and should simply create an instance of a class of your own design and call one of its methods to start the game. Consider what other classes you want to use to accomplish this.

In addition, you should definitely consider creating your own class hierarchy to represent a player, so that you can have shared state and behavior between both types of players, but different logic for choosing whether to pass or roll between the human player and the computer player. Think carefully about how to design this hierarchy to minimize differences, and maximize reuse of code. Also think carefully about what state (data) is managed inside each player object, rather than in the game itself.

You should also implement a separate class to represent a single die. The design of this class (as well as how dice are managed and rolled as a pair) is up to you, but consider how to appropriately separate responsibilities into classes that represent objects in the problem, in order to simplify your design and in order to construct clean, understandable methods.

For the computer player, use the following behavior: choose to pass the dice when the current turn’s points have reached at least 20, or continue rolling if the total is less than 20. Once your game is working and you are confident in your solution, you can further improve or enhance the logic to produce a better computer opponent.

<h3><a id="user-content-additional-requirements" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Pig%20Game#additional-requirements" aria-hidden="true"></a>Additional Requirements</h3>

Your solution must also meet all of the following requirements:

<ol>

 <li>Before play begins, your program must prompt for and read in the human player’s name. Think carefully about where you place this code to minimize coupling.</li>

 <li>The human player always takes the first turn.</li>

 <li>At the beginning of each turn for the human player (before any rolls during that turn), the player’s name must be printed.</li>

 <li>At a minimum, your code must accept “y” and “n” as valid responses from the human player when deciding to roll again (but you are not limited to just these).</li>

 <li>For each roll, your program must print the total value of the roll, the points earned so far for the current turn, and the current value of the player’s “bank”, in that order. When a player’s turn ends, their current “bank” value must be printed.</li>

 <li>All input for the program will be provided on System.in, and all output should be printed on System.out (however, you are welcome to use Scanner and/or PrintWriter objects internally to decouple classes from these choices).</li>

 <li>Be sure that the Random objects you create in your code are all TestableRandom objects (described in the following section).</li>

 <li>Important Note: make sure your program can correctly handle “end of input” part-way through a game and stops successfully. Otherwise, you might have trouble writing a simple test for your main() method.</li>

</ol>

If you reach end of input on System.in (i.e., no more words to read), it is acceptable to simply end the game without a winner. Alternatively, you could treat it as “the player continually passes for all remaining turns”. Still, make sure your game deals with this situation appropriately by terminating–it should not throw an exception or go into an infinite loop.