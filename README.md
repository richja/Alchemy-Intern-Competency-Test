## Alchemy Intern Competency Test

#### 1. Can you list few techniques which you can use to make responsive websites as a frontend developer?
- Using a UI framework, such as Bootstrap, Material UI, Semantic UI, and Onsen UI
- With HTML by setting the viewport with a meta tag
- With CSS, for example:
  - using flexbox
  - @media queries
  - controlling size of elements with percentages, and vh/vw (viewport height/width)
  
#### 2. How can you test a website responsiveness? Which tools in modern browsers you can use for that?
- By utilising the inspect console in a browser: in Google Chrome for example, the device toolbar lets you try the website scaling with the screen size of different common smartphone models
- Scaling the browser window itself on your screen
- Testing the website on a mobile device, or on an emulated mobile device
- Using an online tool to test responsiveness, such as Browserstack

#### 3. What is your favourite text editor and why?
Atom for its simplicity and customizability. I previously used VS Code, but found it too heavy to my taste, and moved to Brackets for a while, before trying Atom and I haven't changed since

#### 4. What is the one keyboard shortcut you wish everyone would know?
Ctrl + A and ctrl + X. It's like the lesser known cousin of ctrl + C and ctrl + V.

#### 5. What was the last article or book you have read related to IT? What did you learn from it?
If video game related content counts, I was reading a book called Gaming Representation: Race, Gender, and Sexuality in Video Games. It was an excellent look into inclusivity and brought up many problems I had myself been faced with, as a female working in the male-dominated tech industry, and as a female playing online video games. Misogyny is unfortunately very common in online game communities, and it was very insightful to read about something I'd dealt with my entire life. Not to say the rest of the book wasn't brilliant too!

#### 6. Have you ever worked with API? Can you describe what is it for?
Many times! API makes it easier to access data and files, for example on a company's server, and makes it more readable. This gives a developer a simpler way to use this data.

For example, Blizzard Entertainment offers different APIs to access data from their games. This is a link including a request to the Creature API, fetching information of the different creatures in World of Warcraft:
https://us.api.blizzard.com/data/wow/media/creature-display/30221?namespace=static-us&locale=en_US&access_token=USHJa9n3tQc1dAMxpG8kEXAEjUEbgqLt5e

If we paste this into a web browser, we get this response:
```json
{
  "_links": {
    "self": {
      "href": "https://us.api.blizzard.com/data/wow/media/creature-display/30221?namespace=static-9.0.1_36072-us"
     }
  },
  "assets": [
    {
      "key": "zoom",
      "value": "https://render-us.worldofwarcraft.com/npcs/zoom/creature-display-30221.jpg"
     }
  ],
  "id": 30221
}
```

This is significantly easier for a developer to read and work with - the API works as a gateway of sorts.

#### 7. Ignoring cookies, what other technology or approach you can use to store data on client side?
By using local storage with Javascript, an API like Web Storage API, and utilising the cache (for example when creating web apps, making it into a PWA and using service workers)

#### 8. Pick a site you are familiar with and list 3-5 things you would do to improve its UI/UX.
