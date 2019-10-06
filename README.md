# stock-analysis
Prepare a basic quantitative analysis of public equities

### Challenge

## Refactoring of Preliminary Code to optimize performance 
Approach
* Create additional arrays to store volume, starting price and ending price to match the previously determined ticker array. 
* Establish a tickerIndex as a counter to cycle through the ticker array. This will be helpful in storing the other data (volume and pricing information) for the individual equities.
* With the objective to cycle through the underlying data set one time only, several blocks of code were created to be executed in series so that for each equity, the starting price was determine first, the volume second and the ending price last. As each row of data is only "viewed" one time, the code determines if the daily price is the "starting price", add the daily volume activity to the volume aggregator and finally if the daily price is the "ending price". After these actions are evaluated and stored in the associated array, if necessary, the next row of data is evaluated until the last row of data is reached. 
* Only after the equity's ending price is determined do the following actions take place. 1) The tickerIndex is increased by one and 2) the volume counter is reset to zero. 
* After all the arrays are populated, an output sheet is populated and formated



Limitations
* I was unsure how to create/modify an array of undetermined size (i.e. if I had a data set with more than 12 distinct equities).
* One issue I had was the treatment of the return on the last set of data in the array. As I was unsure how to create an array of "undefined" size but this had to do with the initial treatment of an array of size(12) which would actually contain thirteen tickers with the last being empty. As a result, since both startingPrices(12) = 0 and endingPrices(12) = 0, this creates a number limit challenge. Rather than include code to deal with potential #n/a errors, the ticker array was to changed to size 11. 
* This code will run into problems if the underlying dataset gets resorted in any way, i.e. by date. 
