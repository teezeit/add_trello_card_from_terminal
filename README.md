# add trello card from your linux terminal
based on: https://gist.github.com/CrookedNumber/8856939.
This is, if you only want a single place that your notes go to.

0. Log in to trello.
1. Go to: https://trello.com/1/appKey/generate.
2. This is your `APP_KEY`.
3. At the same page, click on "generate Token".
4. This is your `USER_TOKEN`.
5. Take the board of your choosing. look at the url and extract the `BOARD_ID`:
  e.g. in https://trello.com/b/eV33ltgS/work it would be `eV33ltgS`.
6. run in a browser or curl (replace `BOARD_ID`, `APP_KEY` and `USER_TOKEN`: https://api.trello.com/1/board/BOARD_ID?cards=open&lists=open&checklists=all&key=APP_KEY&token=USER_TOKEN
7. In the resulting json, search for the name of the list you like to add the cards to and extract the `LIST_ID`.
  e.g. if you have the two lists called "today" and "later" the important part of the json looks like this:
  ```json
  {"id":"daf38f754ebbdaffaadc5332","name":"today","closed":false,"idBoard":"533334efb72ae5e34342d","pos":131271,"subscribed":false},{"id":"53dadffa5594a1cf68f8959ae2","name":"later","closed":false,"idBoard":"333f74efb72ae5e3ae3434","pos":126607,"subscribed":false}
  ```
  and if you want to add to list "today", `LIST_ID` would be `daf38f754ebbdaffaadc5332`
  
8. copy the file `trello` from https://github.com/teezeit/add_trello_card_from_terminal/blob/master/trello
9. replace `APP_KEY`, `USER_TOKEN` and `LIST_ID` with your information. ideally, keep the name `trello`
10. put the file in `/usr/local/bin/` and make the file executable
11. you should be able to run `trello "do not forget milk"` from terminal.
12. let me know if it works!
