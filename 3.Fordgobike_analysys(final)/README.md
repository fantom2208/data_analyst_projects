# Exploration of Ford GoBike system data (by Rodion Boriskin)


## Dataset
This data set includes information about individual rides made in a bike-sharing
system covering the greater San Francisco Bay area.
Data was collected for Feb-2019 from 319 different renting statons.


## Summary of Findings
Dataset contains information about each renting oreder (start/end date, time, station id, 
staion coordinates) also short info about customers: gender, contract type, bithd year.
After short clening (NULL values) I've made some data enginnering exercises:
 - add parameters about day of week, renting hour range
 - add parameter for customer age
 - add parameter for direct distance between start and end stations

Main features of interest (based on detailed data) are:
 - how distribution of renting period, distance, user ages, genders, contract types look like
 - renting peaks and downs during the day and week
 - undertanding correlation of user types (subscriber or customer) also gender with 
   renting durations and frequences
 - ratio between amount of rented and returned bikes at station (to understend if 
   bike relocation process needed)

I've discovered following specifities:
1) In general renting period is quite short 5-10 minutes and distnace covers 
   500 - 2500 meters.
2) Main renting peacks are at 8-10AM and 16-19PM. Downtime period from 23PM til 06AM.
3) Main customers are men (total 71%), prefer "subscriber" contract (total 91%) 
   in ages from 23 till 39.
4) Amount of rents during working days are approximatelly 2 times more then during weekends.
   But at weekends renting period is longer and distance shorter (anothe directions to cycle).
   Main supposition: during working days mornings and evenings people use bikes to go to work 
   (specific distance and time to cycle, more faster cycling).
5) Due due to short period of renting in general there is no bike lacking issue. 
   But for some station such issue exists.
6) As solution for low level of rents at weekend, and solving bike relocation 
   necessaty - organize some discount.
   For famale ratio increasing - investigate reasons (ex. not convenient bike types, colors)

## Key Insights for Presentation
1) one if the insight is a way to conver geographical coordinates to meters 
   (formula or library)
2) initialy I think people are using bikes for rest and travel. 
   in reality they go for a work and back during work days
3) logically there is correlation between renting time and distance
   but 7% of ouliers records breaks this correlation.
   after removing outliers correlation is 0,76
4) gender and contract ratio's quite constant during week days, hours
5) for most of the station ratio between rented and returned bikes well ballanced
   some station requires bike redistribution.