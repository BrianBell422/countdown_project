# countdown_project
### Npm installs for client
```
npm install
npm install vue-google-charts
npm install vue-router
```
### Npm installs for server
```
npm install
npm install express
npm install body-parser
```
### Npm installs for developer server
```
npm install --save-dev cors
npm install --save-dev mongodb
npm install --save-dev nodemon
```
### Run client
```
npm run serve
```
### Run server
```
npm run server:dev
```
### Customize configuration
```
See [Configuration Reference](https://cli.vuejs.org/config/).
```
### Brief
```
Build a browser based game for which we chose to recreate the popular TV game show “Countdown”.
```
### MVP
```
The minimum viable product was that there should be a letters round where players can choose consonants or vowels to populate a letters board, there should be a timer for the game, players should be able to submit answers when timer up and that there should be a scoring system, so players can see who has won the game.
```
Homepage where you can choose to either play an individual section of the game or the full game.
For this demo we will use the full game which will lead us from one section into the next.
![countdown_demo_homepage](https://user-images.githubusercontent.com/74567808/113994672-7ce1ab00-984d-11eb-9721-ff05e8a6f552.png)

You have to select either consonant or vowel to populate the 9 character grid.
Once the grid is populated the timer will start.
![countdown_demo_letters_1](https://user-images.githubusercontent.com/74567808/114046491-c992a980-9880-11eb-814a-383c0ee4594e.png)

Now that the timer is running you have 30 seconds to make the longest word you can using the letters in the grid.
![countdown_demo_letters_1](https://user-images.githubusercontent.com/74567808/113994673-7d7a4180-984d-11eb-8795-73675ff16c3d.png)

Both players then enter their words into the text boxes and submit.
Whoever has the longest word gets 5 points based on word length added to their score.
You can click the definition button below each players word which gets the definition from a dictionary API
![countdown_demo_letters_2](https://user-images.githubusercontent.com/74567808/113994677-7e12d800-984d-11eb-94b4-3cec68e00302.png)

To start the numbers round you have to select how many large numbers you want (25, 50, 75 or 100) and the rest of the grid is populated
with numbers 1 - 10.

![countdown_demo_numbers_1](https://user-images.githubusercontent.com/74567808/113994680-7eab6e80-984d-11eb-9355-8cef09438bdf.png)

Once the grid is populated, a number is shown in the black box and the timer starts.
![countdown_demo_numbers_2](https://user-images.githubusercontent.com/74567808/113994683-7eab6e80-984d-11eb-9648-ec7752f20126.png)

When the timer stops both players have to enter the closest number they managed to get to with a calculation using the numbers in the grid.
The points are added to the player who was closest to the given number.
![countdown_demo_numbers_3](https://user-images.githubusercontent.com/74567808/113994688-7f440500-984d-11eb-96a4-3e7b4153084e.png)


![countdown_demo_anagram_1](https://user-images.githubusercontent.com/74567808/113994650-79e6ba80-984d-11eb-86c2-8ea6a25a175e.png)

![countdown_demo_anagram_2](https://user-images.githubusercontent.com/74567808/113994663-7c491480-984d-11eb-8583-8d68dc146bd3.png)


