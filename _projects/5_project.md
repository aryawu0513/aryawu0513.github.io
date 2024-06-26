---
layout: page
title: DayEscape Mobile App
description: Final Project for Wellesley CS317 Mobile App Development
img: assets/img/dayescape.jpg
importance: 4
category: course projects
---

DayEscape is a user-friendly app designed for easy day trip planning.

<iframe width="800" height="500" src="https://www.youtube.com/embed/vd5ugvWTing" frameborder="0" allowfullscreen></iframe>
<br>
<h5>Core Feature: Route Creation & Verification</h5>
<ul>
    <li><b>Create Trip:</b> The user starts by clicking on markers of places from a places database they created, and entering their planned arrive and leave times. The App checks for invalid inputs, as well as overlapping time duration with existing places in the trip. The user can always go back and change their input time constraints. The places form a trip in the order of their ideal arrive time.</li>
    <li><b>Select transportation:</b> User then picks the transportation mode between places. According to the transportation selected, our App leverages Google Map Directions API to get real-life data of transportation time needed, and checks if the user can arrive at the next place on time. Our App prompts the user where they will be late if the trip’s constraint is unsatisfiable. The user can go back and change the transportation mode to meet the time constraints.</li>
    <li><b>Save Trip:</b> If the trip is valid, the real-life routes are shown. The user can then choose to save the trip with a name, or go back to make changes, or delete the trip. The trip also has associated notes for each place that the user can edit.</li>
</ul>

<h5>Additional Feature: Pin Places & NotePad & View Past Trips</h5>
<ul>
    <li><b>Create Place:</b> Each User has their own associated Places Database. Users can save places they want to visit in the future by putting down pins on a map. We leveraged Google Search API.</li>
    <li><b>Take Notes:</b> Every place has a notepad that can always be edited and saved for users to take notes. Additionally, we leveraged Firestore so that users are allowed to upload images. A list of notes associated with a place in saved trips will show up for users to see past notes they have written.</li>
    <li><b>Trip Summary:</b> On creation of a trip, the notepad of places in this trip will be copied and added to the trip. Users can access an overall summary of a trip they saved. Notes displayed here belong only to this trip and can be edited and saved. Changes made here will be reflected in past notes.</li>
</ul>
