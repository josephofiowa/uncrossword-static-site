# Uncrossword.com

Build a (web)app that enables users to get hints and solutions for IRL crosswords.

## UX

Something like this:

1. Snap a photo of your crossword and the hint
2. Click (or tap) the place where you'd like feedback 
3. Get a hint or provided solution

## Tecnically:

Ingest, process, interact.

**Ingest info**
- Identify all spaces, overall, on the crossword. Read the small numbers corresponding to squares and their clues
- Identify all the spaces a user has filled with handwriting
- Read all clues 

**Process**
- Piece together the shape of the puzzle and corresponding numbered clues
- Prompt an LLM to fill guess clues
- Use context of likely correct clues to re-prompt filling things in

**Interact**
- Enable user to designate which tiled area they'd like help (clicking on the screen)
- Initially, offer a hint (prompt the LLM for another fact about the solution word)
- Display the solution when a user asks for it on the corresponding area in the crossword

## Progress

July 14
- Got a domain, made static placeholder site (why not start easy, eh?)

July 18
- Solve NYT Mini Crossword with GPT-4 prompts

![NYT_july18](./assets/img/nyt-july19-crossword.png)

Example prompting with GPT-4: [https://chat.openai.com/share/2d4b66c9-8039-4d8d-8892-44ae6095a9c5](https://chat.openai.com/share/2d4b66c9-8039-4d8d-8892-44ae6095a9c5)

Notably, GPT-4 was not flawless on this puzzle. For this clue:
> I'm playing a crossword. The clue is "Senior ____ (high school tradition)" and the word is five letters. What is the word?

It first suggested "Prom." After being given an addition letter in this clue:
> I'm playing a crossword. The clue is "Senior ____ (high school tradition)" and the word is five letters. The last letter is "k." What is the word?

It correctly guessed "prank."

Thus, it will be a hard but solvable problem to iteratively find the words that fit the clues and then subsequently and iteratively use that context to solve the rest of the puzzle.

Another failure mode will be recent events (absent GPT-4 with browsing). Not sure on solutions here yet.

Also, Llama2 got 'mad' at the first clue:

![NYT_july18](./assets/img/nyt-crossword-july19-llama2.png)




