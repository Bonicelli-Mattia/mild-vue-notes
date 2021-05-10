# 🥑 Week 3 challenge questions

## `(state) => UI`
### This week we kept repeating the phrase **"UI as a function of state"**. What does it mean to you now?
`It refers to the UI dynamically loading components based on the current status of operation (e.g. fetching files would trigger a loading visualization) to better convey the user what is happening`

## User interactivity 
### Describe in plain language (no code) what steps would you take in order for a user to be able to edit a note in our app? **(Think: which HTML element(s) would you use? Which events? How would you decide when to re-render your components?)**
`I would use a model similar to our NoteThumb component where the user inputs a title saved in a header, the text itself saved in a paragraph and optionally a summary that would get saved in a level above, that will wrap our note using the NoteThumb component. The rerender would be triggered as soon as the user inputs the new note.`

## UI frameworks
### What is the utility of front end frameworks like React or Vue? Why do you think they are so popular?
`Front-end frameworks allow developers to dynamically load only certain parts of the DOM therefore improving responsiveness of the site and reducing the overall rendering costs`

# 🎉 Bonus Whacks

## Virtual DOM
### Frameworks like React and Vue are optimized for updating the parts of the DOM whose state has changed, and leaving everything else intact. How do you think they achieve this? What DOM methods do you think they use under the hood to detect changes, and swap DOM nodes?
`My guess is that they compare the virtual DOM to the actual DOM to check what the differences are, and if there are any they propagate the changes from one to the other. To be able to only change the different things I assume they would have to check every attribute of every tag, then cache those and flag an element as untouched, if any further update is done to that element it checks which attribute changes.`