# Trello API

**Description:** I created a board, a list, a card, a label, a check list and check items on Trello using APIs and Postman.
<br>

<a href="https://developer.atlassian.com/cloud/trello/rest/api-group-actions/" target="blank">API Documentation</a><br>
<a href="https://trello.com/app-key" target="blank">API Keys</a>
<br><br>


### CREATE NEW COLLECTION
<p>
I created new collection in Postman app. <br>
Collection's name: Trello. <br>
  
**Variables:** <br>
{{baseurl}} = https://api.trello.com <br><br>
  
### CREATE A NEW BOARD
`POST` 
/1/boards/
<br>

**Query params:**
  - name: API Board
  - key
  - token

Status: 200 OK <br>
Result: The "API Board" was created.
<br><br>
  
### GET BOARDS THAT MEMBER BELONGS TO
`GET`
/1/members/me/boards
<br>

**Query params:**
  - key
  - token

Status: 200 OK <br>
Result: I got the list of all my boards. "API Board" ID is 63e66c84d9e22ffc54d7c267.
<br><br>
  
### CREATE A LIST ON A BOARD
`POST` 
/1/boards/{id}/lists
  
**Query params:**
- board ID: 63e66c84d9e22ffc54d7c267
- list name: In progress
- key
- token

Status: 200 OK <br>
Result: A "In Progress" list was created with ID 63e6b255a9038a48f879f22c. <br><br>
  
### GET LISTS ON A BOARD
`GET` 
/1/boards/{id}/lists
<br>

**Query params:**
- ID of the board: 63e66c84d9e22ffc54d7c267
- key
- token

Status: 200 OK <br>
Result: I got the lists on the API Board - "To Do", "In Progress", "Doing" and "Done". <br><br>
  
### CREATE A NEW CARD
`POST` 
/1/cards?idList={id}
<br>

**Query params:**
- ID of the list: 63e6b255a9038a48f879f22c
- name: There's a card name
- desc: You can write a description here
- key
- token

Status: 200 OK <br>
Result: A new card was created with ID 63e75259e839c8cee7a01029. <br><br>

### GET CARDS ON A BOARD
`GET`
/1/boards/{id}/cards
<br>

**Query params:**
- ID of the board: 63e66c84d9e22ffc54d7c267
- key
- token
  
Status: 200 OK <br>
Result: I got a list of cards on the API Board. <br><br>
  
### UPDATE A CARD
`PUT` 
/1/cards/{id}
<br>
  
**Query params:**
- ID of the card: 63e75259e839c8cee7a01029
- name: Update name
- desc: Update description
- key
- token

Status: 200 OK <br>
Result: The name and description of the card were changed. <br><br>

### CREATE A NEW LABEL ON A CARD
`POST` 
/1/cards/{id}/labels
<br>

**Query params:**
- ID of the card: 63e75259e839c8cee7a01029
- label: 
  - name: BUG
  - color: red
- key
- token

Status: 200 OK <br>
Result: The red BUG label was added to a card. <br><br>
  
### CREATE CHECKLIST ON A CARD
`POST` 
/1/cards/{id}/checklists
<br>

**Query params:**
- ID of the card: 63e75259e839c8cee7a01029
- name: Checklist 
- pos: top
- key
- token

Status: 200 OK <br>
Result: The Checklist with ID 63f0bcb72ce7ab9d7e12677f was created on the card. <br><br>
  
### CREATE CHECKITEM ON CHECKLIST
`POST` 
/1/checklists/{id}/checkItems
<br>
  
**Query params nr 1:**
- ID of the checklist: 63f0bcb72ce7ab9d7e12677f
- name: Step 1
- key
- token

**Query params nr 2:**
- ID of the checklist: 63f0bcb72ce7ab9d7e12677f
- name: Step 2
- key
- token
  
**Query params nr 3:**
- ID of the checklist: 63f0bcb72ce7ab9d7e12677f
- name: Step 3
- key
- token
  
Status: 200 OK <br>
Result: Check items were created on the checklist. <br><br>

<img src="https://user-images.githubusercontent.com/80547490/219868653-9670f00b-fc93-4235-b445-0ce3166e12d9.png" width=90% high=90%>
  
<br>
  
<img src="https://user-images.githubusercontent.com/80547490/219868603-6e0e16e9-d205-4fd6-b78a-c1448b9411c4.png" width=60% high=60%>
