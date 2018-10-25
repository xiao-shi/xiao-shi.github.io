plotly
================
Xiao Shi
October 23, 2018

``` r
set.seed(1)

data(nyc_airbnb)
nyc_airbnb = 
  nyc_airbnb %>% 
  mutate(rating = review_scores_location / 2) %>%
  select(boro = neighbourhood_group, neighbourhood, rating, price, room_type,
         latitude, longitude) %>%
  filter(!is.na(rating), 
         boro == "Manhattan",
         room_type == "Entire home/apt",
         price %in% 100:500)  %>% 
  sample_n(5000)
```
