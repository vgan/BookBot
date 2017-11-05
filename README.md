# BookBot
Using [char-rnn-tensorflow](https://github.com/sherjilozair/char-rnn-tensorflow) to write a book for [#NanoGenMo 2017](https://github.com/NaNoGenMo/2017)

I downloaded a selection of books from [Project Gutenberg](https://www.gutenberg.org/) as training input. I cleaned up the text as much as I could and tried to keep the formatting consistent, the combined text for input ended up being 8.1MB.
 
This is a lovely command for combining them:

`ls *.txt | xargs -L 1 cat >> input.txt`
 
Ingredients:
- Alice in Wonderland
- Isaac Asimov
- Jane Austen
- Ray Bradbury
- Communist Manifesto
- Craphound
- Philip K. Dick
- Charles Dickens
- Frank Herbert
- Herman Hesse
- The complete Sherlock Holmes books
- Bram Stokers Dracula
- The Brothers Grimm
- Peter Rabbit
- The Secret Garden
- Treasure Island

## Notes:

I was working with a GTX1080 and after tweaking the training settings through trial and error this was the final command I ended up using:

`python train.py --data_dir=./data/bookbot/ --batch_size 1000 --rnn_size 700 --num_layer 3`

Some small sample output from the trained model:
- The bear was delightedly round, when very free trails of debris were to go, could eat all the blackened slopes of strength to do something like blood from the fireplace.

OK, now to write the 50k word book for NanoGenMo:

`python sample.py -n 300000 >book.txt`

Here is the [book](https://github.com/vgan/BookBot/blob/master/book.txt)!
