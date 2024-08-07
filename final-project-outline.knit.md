
<!-- rnb-text-begin -->

---
title: "Final Project"
author: "Nandagopal Panicker"
output: html_notebook
---


## Research Objective 

The aim of this project is to successfully compare two datasets to derive valuable insights from both of them. I have a couple of objectives in mind with regards to spotting trends:

* I want to find the top 5 songs appearing the most in playlists in 2023 and 2024 and make a vizualization revolving around the same.

* Since this is not a key feature in the 2024 dataset, I want to see if the bpm of a song has a correlation of sorts to how popular it is on the most popular streaming platform(Spotify).

* In addition to this, I want to compare the streams for songs over Spotify, Deezer, and Apple Music and see if the music in 2024 is more popular than the music in 2023.


## Data Processing 

#### Data Intake 

A couple of things are important to note with regards to these data-sets. The 2023 spotify dataset has a lot less data than the 2024 one.

Both these datasets have been provided by the Spotify API. For the sake of visualization and data preprocessing steps, we will take only the top 50 songs of each year of each dataset.

I have downloaded the two datasets from Kaggle, they are publicly available datasets with the links as follows:

[Click here for the link to the 2023 Spotify Dataset](https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023)

[Click here for the link to the 2024 Spotify Dataset](https://www.kaggle.com/datasets/nelgiriyewithana/most-streamed-spotify-songs-2024?resource=download)


I have uploaded the csv files on the 'Final Project' Git repository, and pulled the files onto my local workspace.


#### Data Wrangling 

Include R code and written explanation for wangling your data (you can make multiple wrangled data sets). 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-frame-begin eyJtZXRhZGF0YSI6eyJjbGFzc2VzIjpbImRhdGEuZnJhbWUiXSwibnJvdyI6NiwibmNvbCI6MjQsInN1bW1hcnkiOnsiRGVzY3JpcHRpb24iOlsiZGYgWzYgw5cgMjRdIl19fSwicmRmIjoiSDRzSUFBQUFBQUFBQnBWVnpXN2JSaENtUkZteTVkL0VCZUpUUWlDWEdJMEpTcVFsT2tBUjJJNFNJM1dRd25MYUZDMHFyTW0xeElyY1paY3JPUXFRb3BkZUNoUW8wTGZvc1kvUUYraXBUOUJEM3lMdFVOcWhTT1pVQVI5Mjl2dDJkbmRtUjhPTEo2L3Q1dXVtcG1tNlZxdFZOSDBGVEczbDFlWFRBMWZUYWxXWVZMU2F0cGFPYjJEUkxoaDdnQjFBWFFuMyszUkttZkhnbWhKcEd1ZEVTcjV2UE9pOWljUEFDNlR4T1JYbXZscGFPejgrUDFaMlkwcWlPQkJVVFRkT3hZU0dSbjhTUlZRb2J1dUxzOTVGeitpZjlZeG5MM3Q5eGE3Mll4RXdDYXVLOTlpWkgvM1FlRDVoUStOVHpzZUtYMzh4RzFQamt0OVFrZURHTDhOZ0doRGpndnNpR0hLOHdpV1poVndZL1p2Z1dpcHU3WVQ0eHNtRXNaa2liajBoVS9yUU9LVk1DaExDU0lIY25GOUQweGI1S3FLNjFCdi81UEQzMHM3OEcvT0hXTmlyNlVNb0cvVXR3QjNBWFRYZVZtY292Ym9QTG44QUpyRGtkd2pvRTlqbXA1ei9yd0FMOEIzQUI3UUJYNVhTdU5aeVdyYmI2bHAyUnRoMnQ5VnB1NTNsQ3N1eTdLT3VnNFJyV2E1amdSTVN0bVczN1k3ZGJtY3VydDIxT20zYnlkM21ZM1diYndBU2NBazRYZXFWTkJ2ZkEvNVUrQkh3VittMlZlY1FyVU1YcmFPV3N2UldPNVBkYm1hNXVVczBWVnBUYkFDMjB6Y3VIYUs3Yll4ZHQxMk1TVDl5anRBOGRQQnczY21PaEFXZDNFbnZBRjhEMGdmNURmQUw0T2ZTU1pVVHZPVHBmYVNlb25GY050SkZSZitWRitSYkx2N3ZKR0JsWlhucnp3RFBBRGFnQ3poV1VhRCtKUURLVERNQWoxUlpudVQwUHVBNTRCQndwdlo3bE5QdmFZdXlUM08rcnQ1aE42ZVhmNC9WaVBxcWVzTjd5bjlkY2FqWEZPcnFiZE54cjlUYVZoaUphS0pTdWFmSUp2eS92ZkVnbGJCckVDR0RSSnFKbVdjM0Z1ekE0eE9HWFdOVDBKQ1NoUHFER1NWWk44dklpRE01UXZlTTlRbjJtSThDTmtoaUxvUHIyU0FPb1NuQi90aTZidVUwYndSbm85QklwS0Frd3VsdFdFZmlPS1FmN0xDZEtRWC9YYUI5U3Q5UzhZSEh6bElxdUtSOE1pSnZTVlRrOWFzNFFuTk1NYXBheFAwc2xUNWhIaVZYUVJqSTJjREVMakVsSVFVK0kxWXBvMks0WExCRklNdUpERHhHa3lSaklWU0lmUkpCU3laaFFXbENtNmNGWmpPSktmVkdnU0tMZGJBbStJMkp0WkFXVVBXSFJiSFZ5d1hqaFNUQmdrR3k2Uk5Kekd1UmxvYW12Uys1Tkhnc0E4N0FxYnFyeWpEdlhCRWxZaHUrT2JDVGYrQ05KbXg4NEpSa1BXWkRWZm40b2RsVVl6MW5xMHF2L3FzViswU2RzaUhrQU1NSnlSVU5jV2VmVHJPSzVUZnpkSmp6THk3R0NXeGlTZzdKUnNiaklUTHp5TFgzL3dGS1hiZjBXUWdBQUE9PSJ9 -->

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["track_name"],"name":[1],"type":["chr"],"align":["left"]},{"label":["artist.s._name"],"name":[2],"type":["chr"],"align":["left"]},{"label":["artist_count"],"name":[3],"type":["int"],"align":["right"]},{"label":["released_year"],"name":[4],"type":["int"],"align":["right"]},{"label":["released_month"],"name":[5],"type":["int"],"align":["right"]},{"label":["released_day"],"name":[6],"type":["int"],"align":["right"]},{"label":["in_spotify_playlists"],"name":[7],"type":["int"],"align":["right"]},{"label":["in_spotify_charts"],"name":[8],"type":["int"],"align":["right"]},{"label":["streams"],"name":[9],"type":["chr"],"align":["left"]},{"label":["in_apple_playlists"],"name":[10],"type":["int"],"align":["right"]},{"label":["in_apple_charts"],"name":[11],"type":["int"],"align":["right"]},{"label":["in_deezer_playlists"],"name":[12],"type":["chr"],"align":["left"]},{"label":["in_deezer_charts"],"name":[13],"type":["int"],"align":["right"]},{"label":["in_shazam_charts"],"name":[14],"type":["chr"],"align":["left"]},{"label":["bpm"],"name":[15],"type":["int"],"align":["right"]},{"label":["key"],"name":[16],"type":["chr"],"align":["left"]},{"label":["mode"],"name":[17],"type":["chr"],"align":["left"]},{"label":["danceability_."],"name":[18],"type":["int"],"align":["right"]},{"label":["valence_."],"name":[19],"type":["int"],"align":["right"]},{"label":["energy_."],"name":[20],"type":["int"],"align":["right"]},{"label":["acousticness_."],"name":[21],"type":["int"],"align":["right"]},{"label":["instrumentalness_."],"name":[22],"type":["int"],"align":["right"]},{"label":["liveness_."],"name":[23],"type":["int"],"align":["right"]},{"label":["speechiness_."],"name":[24],"type":["int"],"align":["right"]}],"data":[{"1":"Seven (feat. Latto) (Explicit Ver.)","2":"Latto, Jung Kook","3":"2","4":"2023","5":"7","6":"14","7":"553","8":"147","9":"141381703","10":"43","11":"263","12":"45","13":"10","14":"826","15":"125","16":"B","17":"Major","18":"80","19":"89","20":"83","21":"31","22":"0","23":"8","24":"4","_rn_":"1"},{"1":"LALA","2":"Myke Towers","3":"1","4":"2023","5":"3","6":"23","7":"1474","8":"48","9":"133716286","10":"48","11":"126","12":"58","13":"14","14":"382","15":"92","16":"C#","17":"Major","18":"71","19":"61","20":"74","21":"7","22":"0","23":"10","24":"4","_rn_":"2"},{"1":"vampire","2":"Olivia Rodrigo","3":"1","4":"2023","5":"6","6":"30","7":"1397","8":"113","9":"140003974","10":"94","11":"207","12":"91","13":"14","14":"949","15":"138","16":"F","17":"Major","18":"51","19":"32","20":"53","21":"17","22":"0","23":"31","24":"6","_rn_":"3"},{"1":"Cruel Summer","2":"Taylor Swift","3":"1","4":"2019","5":"8","6":"23","7":"7858","8":"100","9":"800840817","10":"116","11":"207","12":"125","13":"12","14":"548","15":"170","16":"A","17":"Major","18":"55","19":"58","20":"72","21":"11","22":"0","23":"11","24":"15","_rn_":"4"},{"1":"WHERE SHE GOES","2":"Bad Bunny","3":"1","4":"2023","5":"5","6":"18","7":"3133","8":"50","9":"303236322","10":"84","11":"133","12":"87","13":"15","14":"425","15":"144","16":"A","17":"Minor","18":"65","19":"23","20":"80","21":"14","22":"63","23":"11","24":"6","_rn_":"5"},{"1":"Sprinter","2":"Dave, Central Cee","3":"2","4":"2023","5":"6","6":"1","7":"2186","8":"91","9":"183706234","10":"67","11":"213","12":"88","13":"17","14":"946","15":"141","16":"C#","17":"Major","18":"92","19":"66","20":"58","21":"19","22":"0","23":"8","24":"24","_rn_":"6"}],"options":{"columns":{"min":{},"max":[10],"total":[24]},"rows":{"min":[10],"max":[10],"total":[6]},"pages":{}}}
  </script>
</div>

<!-- rnb-frame-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

This is the head of the 2023 Spotify Most Streamed Charts.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZGF0YTIwMjQgPC0gcmVhZC5jc3YoXCJNb3N0IFN0cmVhbWVkIFNwb3RpZnkgU29uZ3MgMjAyNC5jc3ZcIilcbmhlYWQoZGF0YTIwMjQpXG5gYGAifQ== -->

```r
data2024 <- read.csv("Most Streamed Spotify Songs 2024.csv")
head(data2024)
```

<!-- rnb-source-end -->

<!-- rnb-frame-begin eyJtZXRhZGF0YSI6eyJjbGFzc2VzIjpbImRhdGEuZnJhbWUiXSwibnJvdyI6NiwibmNvbCI6MjksInN1bW1hcnkiOnsiRGVzY3JpcHRpb24iOlsiZGYgWzYgw5cgMjldIl19fSwicmRmIjoiSDRzSUFBQUFBQUFBQm8xWHkyN2JSaFNsL0pBaU9ZNkRCc2tpYUFCK3dGam1QTWdoTjRVVk8ybWMya2xxeVlGVGRFUExURXlZSWdXS2lpTjNrMjZLSWwvUWR0ZDF1KzZxNkJlMFhiVC9rL2FNclJuUnRQc2dNQ1o1T2ZkOXp0VjRkM09mdC9aYmxtWE5Xd3NMTld0K0VZL1c0bDd2NGFwdldRdHplS2xaQzFaVDNkOWcweTA4M01PNmlWV2ZmcmkxczdXOXZmWDBpYjM1ZEh1N3MydmY3OXgvTWYyMDlDUXI3TzM0T0xMM1JsUFIzZGhPbEtBNGl1eVRjR0pQc3JGOUhJOUc5aUNhN21nOFRMS1RLTmNLalVmWitEQk9ZMjF5TzNzZHAvYlQxTjZKS29GOHVCTW5TWnlsOW1hV0pHRnUzdzhQSnZhcTNZM1RWMG4wTHhGdC9WZEVONmNSVlkzOS85Q1dlOWxnTUxGMzQvN1JJRXlud2h1ZlJPbGhIdmVQN2Uxd0VPYmFhQ2N2b2tHb28xdENVdEhFM3Bqa1l5MnFQeGpFYVRUUUd4NkhzUEFvekJGanhXdFRyREZ2alRsTVRBWFgzRFZSZm0veU5ScGNFTkExeXBTQWE0Rzd4bWw1UjR0aWkzTys1YUszNjUvdU1ORmx3bUV1ODdWc3I3djNNWVhNQ2FoajluMzIyQmRLeG4wNTI5ZmRvWXc1Z1pTeXFzdDVVTExYNlRIR0tlV1NWdnpYcUg1ZytrRm5VZFBSMTF6OTRLa0dLTzMxcjM3ZzZsci9jdVg4L3ZiUDgvc1h2NzlVMS9wcDhTdXUzOVluMzMrTDY3dUsxeVVlT0VSSWh3VGNNeUxHaVhRNDhYM3RkOGx6S09GT1FKaXZZMXBteE9FVUFvZDRYQXVYcUNNaEZpUmd6S2pDdU9lNVJIQy80cnZPSFNLcGRsdG5Qa0ZkOUpzckNPZTZKQTNtQmNSM3RNMUZTWmhwY1lNNkx2RURWazJNQmg0aW84VDFmU09TZ3JpQkpLaStGakZLaVllZ1BTOHd1N2hIWFBoejVFelJwVVNvRUtTWTJVSktqS3BzVlRYT1BGdlc1NlcxaDdXUDFhMUUxdklGWVloRXVqTmoxQ05jb0hUQ01TTEdFR3VBa3VnQ0xjTVpjcUtPZzNSMXRDMHBDWmVjQks2Y3hVOEpGVDQyVnlIV3BLZzNKNVJwazAxT2hPOFJ5Ylc1SmtObGZRaDBIQzJLN3JHQXlLQ2tvMXBLVFZsaGxRY3EyQ3FqbWk2Um5nU1V0TEdHcDlJMnI3QUVzaEV4RTZBMVBxcE1kZC9ycUV2cE0rcm1NTUk5V2UyMWgvNjR3RmhnOXJhNHF6QkNYREZyTlRwR0FTdG11cThxS3BHdEswbmc2WFNzR1RTQVk2RXFGRlRIb1F0c29sSStMZE9HT1Q3RWdjcEo3K01JRmkxa3FLR1pIemRnMWdPN0pGSVBBbEh4Q2xvRjNDZWU3NTNScW9wcDF6a0RjQmtuTHFBREVuSlhGMjFKNFVFQ1pJRmJEZ1FsUXM5QUI4Tk1TaGthQko0YlZYajNQVVV1QnUrc2hPcy9zSDdHK2dXajV4M3VQMkc5cTlKWllJcEl0L1FtRFlQcVV0R1p6eEFqRkJJTWl1dUloUHBhdGVIQ3Z5T3FqSjczekR3eWszSGVOZlZmVkNiTTZOUVpMYUxZYnBtaEgyRnRZSDJOVGRkdzM4VjZYbVVvbFNnemdFRjlJOEdVUkZSaVJneE1DUTcrK3daZ0xRWmZpdHZDTDlueFBFVWdVWkpRVmVFTE1lVllHZGFQMDBySFdOOWNpZ21NZGxRMnVreGdpMFRqSGZOckJiNDVxblBNSUlGaXVETUV3TXl2RWpna2dndWpuUUp1TGhqT3ZXckI2MHlCMFhBUmMwRUlyYmJvQWlHNmZRMEdQSE5qRXVQWmNjeFlCMlFEdjJvYVlmaElTSmlwMVFUZVFWZEhsckpUaFBJTU5xMlpNOVJRbW9rVnFGOFdNT3JTc0dOcXFDTjlqUW1nanNJbm02bGlSUGlnc3BnTk8vUlRKUzIwVGdNUkVvZVdxdWVxRG5MbFRCMDc2Mi94NTZwVjZxNjZhdGJzcXAydkM2ZlR4VFFjUktOcEJ2ZTBzSmZqYktSajZ5UUg0MEg3U1dpT2RYV2N0T0pSb1k4V3UxRVNoYU9vdlJrV2VzZkNWbmQzUTFPN2t5VHRYanlJMnJ0aHFvMHVuWGxvZC90WnJuVld1c09zaUY5TzJ0MGlqOEtCUHJUZDBlSm5TVGhKNExhOWtZM1Q0aCsvN2taaC8yajY5UVB6TlJ1T2NiS05pNGtPNmtVMjdvMFBvdmJ6T0RvWlZZWHFuS3VGMTN2eGNTODdob2xSVVpWZHRhOXM4STQyZUdWMGR6dkRZUksxZDhhanVIOTFkc3VkT0ZjZjJ0MWhuR3FqTjdweEhvOUgrenNYcExjM28rZzB5cSsyYytsak9ZemJuVUY0bXFWWGE2NDhDOVBETEErclRkSGlhUnVMc01EL0R5TlRkbGc0N0NjNDVGZjBscnRINFdrNE9IZWhoVGQ3VzV1ZDdjczl1dkhnelRDSiszRng3cVVDM0dhZW5iUTFlQlhpNTZib3IxY1Izay9Da1VhNEZyWU93eUpzdjh3VnFDM3JmVVdsa1EzUDg3SG1iazI1VkZhdTVSWEJ5amhWa1J5dTlvL0c2ZkVxcTN5ZUg2YXZwclNkVXZBczROclV0SDYrZHg3RjNGK1ZlVktQMGxmNHYwV25rNFFIVWFJdEgwYXZkYlZRajdOeXRJZDViUHJYZ25UVUxySWkxQ3F0ZnBab3lWbm0xdnUvQWNtaW1NSE5EZ0FBIn0= -->

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["Track"],"name":[1],"type":["chr"],"align":["left"]},{"label":["Album.Name"],"name":[2],"type":["chr"],"align":["left"]},{"label":["Artist"],"name":[3],"type":["chr"],"align":["left"]},{"label":["Release.Date"],"name":[4],"type":["chr"],"align":["left"]},{"label":["ISRC"],"name":[5],"type":["chr"],"align":["left"]},{"label":["All.Time.Rank"],"name":[6],"type":["chr"],"align":["left"]},{"label":["Track.Score"],"name":[7],"type":["dbl"],"align":["right"]},{"label":["Spotify.Streams"],"name":[8],"type":["chr"],"align":["left"]},{"label":["Spotify.Playlist.Count"],"name":[9],"type":["chr"],"align":["left"]},{"label":["Spotify.Playlist.Reach"],"name":[10],"type":["chr"],"align":["left"]},{"label":["Spotify.Popularity"],"name":[11],"type":["int"],"align":["right"]},{"label":["YouTube.Views"],"name":[12],"type":["chr"],"align":["left"]},{"label":["YouTube.Likes"],"name":[13],"type":["chr"],"align":["left"]},{"label":["TikTok.Posts"],"name":[14],"type":["chr"],"align":["left"]},{"label":["TikTok.Likes"],"name":[15],"type":["chr"],"align":["left"]},{"label":["TikTok.Views"],"name":[16],"type":["chr"],"align":["left"]},{"label":["YouTube.Playlist.Reach"],"name":[17],"type":["chr"],"align":["left"]},{"label":["Apple.Music.Playlist.Count"],"name":[18],"type":["int"],"align":["right"]},{"label":["AirPlay.Spins"],"name":[19],"type":["chr"],"align":["left"]},{"label":["SiriusXM.Spins"],"name":[20],"type":["chr"],"align":["left"]},{"label":["Deezer.Playlist.Count"],"name":[21],"type":["int"],"align":["right"]},{"label":["Deezer.Playlist.Reach"],"name":[22],"type":["chr"],"align":["left"]},{"label":["Amazon.Playlist.Count"],"name":[23],"type":["int"],"align":["right"]},{"label":["Pandora.Streams"],"name":[24],"type":["chr"],"align":["left"]},{"label":["Pandora.Track.Stations"],"name":[25],"type":["chr"],"align":["left"]},{"label":["Soundcloud.Streams"],"name":[26],"type":["chr"],"align":["left"]},{"label":["Shazam.Counts"],"name":[27],"type":["chr"],"align":["left"]},{"label":["TIDAL.Popularity"],"name":[28],"type":["lgl"],"align":["right"]},{"label":["Explicit.Track"],"name":[29],"type":["int"],"align":["right"]}],"data":[{"1":"MILLION DOLLAR BABY","2":"Million Dollar Baby - Single","3":"Tommy Richman","4":"4/26/2024","5":"QM24S2402528","6":"1","7":"725.4","8":"390,470,936","9":"30,716","10":"196,631,588","11":"92","12":"84,274,754","13":"1,713,126","14":"5,767,700","15":"651,565,900","16":"5,332,281,936","17":"150,597,040","18":"210","19":"40,975","20":"684","21":"62","22":"17,598,718","23":"114","24":"18,004,655","25":"22,931","26":"4,818,457","27":"2,669,262","28":"NA","29":"0","_rn_":"1"},{"1":"Not Like Us","2":"Not Like Us","3":"Kendrick Lamar","4":"5/4/2024","5":"USUG12400910","6":"2","7":"545.9","8":"323,703,884","9":"28,113","10":"174,597,137","11":"92","12":"116,347,040","13":"3,486,739","14":"674,700","15":"35,223,547","16":"208,339,025","17":"156,380,351","18":"188","19":"40,778","20":"3","21":"67","22":"10,422,430","23":"111","24":"7,780,028","25":"28,444","26":"6,623,075","27":"1,118,279","28":"NA","29":"1","_rn_":"2"},{"1":"i like the way you kiss me","2":"I like the way you kiss me","3":"Artemas","4":"3/19/2024","5":"QZJ842400387","6":"3","7":"538.4","8":"601,309,283","9":"54,331","10":"211,607,669","11":"92","12":"122,599,116","13":"2,228,730","14":"3,025,400","15":"275,154,237","16":"3,369,120,610","17":"373,784,955","18":"190","19":"74,333","20":"536","21":"136","22":"36,321,847","23":"172","24":"5,022,621","25":"5,639","26":"7,208,651","27":"5,285,340","28":"NA","29":"0","_rn_":"3"},{"1":"Flowers","2":"Flowers - Single","3":"Miley Cyrus","4":"1/12/2023","5":"USSM12209777","6":"4","7":"444.9","8":"2,031,280,633","9":"269,802","10":"136,569,078","11":"85","12":"1,096,100,899","13":"10,629,796","14":"7,189,811","15":"1,078,757,968","16":"14,603,725,994","17":"3,351,188,582","18":"394","19":"1,474,799","20":"2,182","21":"264","22":"24,684,248","23":"210","24":"190,260,277","25":"203,384","26":"","27":"11,822,942","28":"NA","29":"0","_rn_":"4"},{"1":"Houdini","2":"Houdini","3":"Eminem","4":"5/31/2024","5":"USUG12403398","6":"5","7":"423.3","8":"107,034,922","9":"7,223","10":"151,469,874","11":"88","12":"77,373,957","13":"3,670,188","14":"16,400","15":"","16":"","17":"112,763,851","18":"182","19":"12,185","20":"1","21":"82","22":"17,660,624","23":"105","24":"4,493,884","25":"7,006","26":"207,179","27":"457,017","28":"NA","29":"1","_rn_":"5"},{"1":"Lovin On Me","2":"Lovin On Me","3":"Jack Harlow","4":"11/10/2023","5":"USAT22311371","6":"6","7":"410.1","8":"670,665,438","9":"105,892","10":"175,421,034","11":"83","12":"131,148,091","13":"1,392,593","14":"4,202,367","15":"214,943,489","16":"2,938,686,633","17":"2,867,222,632","18":"138","19":"522,042","20":"4,654","21":"86","22":"17,167,254","23":"152","24":"138,529,362","25":"50,982","26":"9,438,601","27":"4,517,131","28":"NA","29":"1","_rn_":"6"}],"options":{"columns":{"min":{},"max":[10],"total":[29]},"rows":{"min":[10],"max":[10],"total":[6]},"pages":{}}}
  </script>
</div>

<!-- rnb-frame-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

This is the head of the Spotify 2024 most streamed charts.


Next, it is important for us to use some kind of imputational model normally with regards to data cleaning for handling of missing values. I am not too familiar with the use of imputational models on R, instead, since the datasets are so vast, we can find rows with missing values for each data set and remove them from our data-sets. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc3VtKGlzLm5hKGRhdGEyMDIzKSkgIyBDaGVja2luZyBmb3Igcm93cyB3aXRoIG1pc3NpbmcgdmFsdWVzIGluIDIwMjMgU3BvdGlmeSBEYXRhc2V0IFxuYGBgIn0= -->

```r
sum(is.na(data2023)) # Checking for rows with missing values in 2023 Spotify Dataset 
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIDBcbiJ9 -->

```
[1] 0
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

As it turns out there are no missing values in this data-set, but for the sake of safety, we can remove any if at all:

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZGF0YTIwMjMgPC0gbmEub21pdChkYXRhMjAyMylcbnN1bShpcy5uYShkYXRhMjAyMykpXG5gYGAifQ== -->

```r
data2023 <- na.omit(data2023)
sum(is.na(data2023))
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIDBcbiJ9 -->

```
[1] 0
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

For data cleaning, it is important to note that while this is not the case for 2023, in 2024 a lot of variables are in string format, we will change them to numerical values accordingly for better help with regards to visualization:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZGF0YTIwMjQgPC0gZGF0YTIwMjQgJT4lXG4gIG11dGF0ZShcbiAgICBTcG90aWZ5LlN0cmVhbXMgPSBhcy5udW1lcmljKGdzdWIoXCIsXCIsIFwiXCIsIFNwb3RpZnkuU3RyZWFtcykpLFxuICAgIFNwb3RpZnkuUGxheWxpc3QuQ291bnQgPSBhcy5udW1lcmljKGdzdWIoXCIsXCIsIFwiXCIsIFNwb3RpZnkuUGxheWxpc3QuQ291bnQpKSxcbiAgICBTcG90aWZ5LlBsYXlsaXN0LlJlYWNoID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBTcG90aWZ5LlBsYXlsaXN0LlJlYWNoKSksXG4gICAgWW91VHViZS5WaWV3cyA9IGFzLm51bWVyaWMoZ3N1YihcIixcIiwgXCJcIiwgWW91VHViZS5WaWV3cykpLFxuICAgIFlvdVR1YmUuTGlrZXMgPSBhcy5udW1lcmljKGdzdWIoXCIsXCIsIFwiXCIsIFlvdVR1YmUuTGlrZXMpKSxcbiAgICBUaWtUb2suUG9zdHMgPSBhcy5udW1lcmljKGdzdWIoXCIsXCIsIFwiXCIsIFRpa1Rvay5Qb3N0cykpLFxuICAgIFRpa1Rvay5MaWtlcyA9IGFzLm51bWVyaWMoZ3N1YihcIixcIiwgXCJcIiwgVGlrVG9rLkxpa2VzKSksXG4gICAgVGlrVG9rLlZpZXdzID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBUaWtUb2suVmlld3MpKSxcbiAgICBZb3VUdWJlLlBsYXlsaXN0LlJlYWNoID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBZb3VUdWJlLlBsYXlsaXN0LlJlYWNoKSksXG4gICAgQXBwbGUuTXVzaWMuUGxheWxpc3QuQ291bnQgPSBhcy5udW1lcmljKEFwcGxlLk11c2ljLlBsYXlsaXN0LkNvdW50KSxcbiAgICBEZWV6ZXIuUGxheWxpc3QuQ291bnQgPSBhcy5udW1lcmljKERlZXplci5QbGF5bGlzdC5Db3VudCksXG4gICAgRGVlemVyLlBsYXlsaXN0LlJlYWNoID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBEZWV6ZXIuUGxheWxpc3QuUmVhY2gpKSxcbiAgICBBbWF6b24uUGxheWxpc3QuQ291bnQgPSBhcy5udW1lcmljKEFtYXpvbi5QbGF5bGlzdC5Db3VudCksXG4gICAgUGFuZG9yYS5TdHJlYW1zID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBQYW5kb3JhLlN0cmVhbXMpKSxcbiAgICBQYW5kb3JhLlRyYWNrLlN0YXRpb25zID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBQYW5kb3JhLlRyYWNrLlN0YXRpb25zKSksXG4gICAgU291bmRjbG91ZC5TdHJlYW1zID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBTb3VuZGNsb3VkLlN0cmVhbXMpKSxcbiAgICBTaGF6YW0uQ291bnRzID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBTaGF6YW0uQ291bnRzKSlcbiAgKVxuYGBgIn0= -->

```r
data2024 <- data2024 %>%
  mutate(
    Spotify.Streams = as.numeric(gsub(",", "", Spotify.Streams)),
    Spotify.Playlist.Count = as.numeric(gsub(",", "", Spotify.Playlist.Count)),
    Spotify.Playlist.Reach = as.numeric(gsub(",", "", Spotify.Playlist.Reach)),
    YouTube.Views = as.numeric(gsub(",", "", YouTube.Views)),
    YouTube.Likes = as.numeric(gsub(",", "", YouTube.Likes)),
    TikTok.Posts = as.numeric(gsub(",", "", TikTok.Posts)),
    TikTok.Likes = as.numeric(gsub(",", "", TikTok.Likes)),
    TikTok.Views = as.numeric(gsub(",", "", TikTok.Views)),
    YouTube.Playlist.Reach = as.numeric(gsub(",", "", YouTube.Playlist.Reach)),
    Apple.Music.Playlist.Count = as.numeric(Apple.Music.Playlist.Count),
    Deezer.Playlist.Count = as.numeric(Deezer.Playlist.Count),
    Deezer.Playlist.Reach = as.numeric(gsub(",", "", Deezer.Playlist.Reach)),
    Amazon.Playlist.Count = as.numeric(Amazon.Playlist.Count),
    Pandora.Streams = as.numeric(gsub(",", "", Pandora.Streams)),
    Pandora.Track.Stations = as.numeric(gsub(",", "", Pandora.Track.Stations)),
    Soundcloud.Streams = as.numeric(gsub(",", "", Soundcloud.Streams)),
    Shazam.Counts = as.numeric(gsub(",", "", Shazam.Counts))
  )
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



We can now perform the same check for the 2024 Data-set.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc3VtKGlzLm5hKGRhdGEyMDI0KSkgIyBDaGVja2luZyBmb3Igcm93cyB3aXRoIG1pc3NpbmcgdmFsdWVzIGluIDIwMjQgU3BvdGlmeSBEYXRhc2V0IFxuYGBgIn0= -->

```r
sum(is.na(data2024)) # Checking for rows with missing values in 2024 Spotify Dataset 
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIDIwMTc0XG4ifQ== -->

```
[1] 20174
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

There seem to be 25759 rows with missing information. This is expected since it is a much larger dataset than that of the 2023. We must now fill in these rows and check again:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGlicmFyeSh0aWR5dmVyc2UpXG5kYXRhMjAyNFtpcy5uYShkYXRhMjAyNCldIDwtIDBcbnN1bShpcy5uYShkYXRhMjAyNCkpXG5gYGAifQ== -->

```r
library(tidyverse)
data2024[is.na(data2024)] <- 0
sum(is.na(data2024))
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIDBcbiJ9 -->

```
[1] 0
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Instead of ommitting these rows since a very large number of observations seem to be left out, we have just replaced the N/A's with a value of 0 thus retaining the dataset, since no observation was left if we tried to omit all rows with missing values. Another imputational model could have been employed by calculating the mean or median of columns but for the sake of simplicity, I assigned 0.


Let us continue with the data wrangling methods now that we have gotten a better understanding of our dataset.


For the first part of our objective, we need to find the top 5 songs appearing the most in spotify playlists in 2023 and 2024 respectively:


* In 2023:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxudG9wNV8yMDIzIDwtIGRhdGEyMDIzICU+JVxuICBhcnJhbmdlKGRlc2MoaW5fc3BvdGlmeV9wbGF5bGlzdHMpKSAlPiVcbiAgc2xpY2VfaGVhZChuID0gNSlcblxudG9wNV8yMDIzXG5gYGAifQ== -->

```r
top5_2023 <- data2023 %>%
  arrange(desc(in_spotify_playlists)) %>%
  slice_head(n = 5)

top5_2023
```

<!-- rnb-source-end -->

<!-- rnb-frame-begin eyJtZXRhZGF0YSI6eyJjbGFzc2VzIjpbImRhdGEuZnJhbWUiXSwibnJvdyI6NSwibmNvbCI6MjQsInN1bW1hcnkiOnsiRGVzY3JpcHRpb24iOlsiZGYgWzUgw5cgMjRdIl19fSwicmRmIjoiSDRzSUFBQUFBQUFBQm8xVnpZNFRSeEJ1LzYyeHlTNUxOb0k5anBKVEl0dWFHZHRqV3prQkcxQVVkaUdMWVJFSVdiMHp0WGJIODZlZXRzRUlpVHhFSGlES0MrUVZrSkNTQTFJdU9lZFZTS3J0N3ZITWJBNk05S21ydi9ycHFsSzVmSHIwdE50ODJpU0VWRWkxV2lLVkdvcWs5bmg4dHowa3BGckdTNGxVU1VPZXI5RG9BSVZEeEw2MFVvb2I5MEFZOXhmdWZHVzBqVlBxc2NqNHptTkNhZmVPZWNlNHpkbDBKaExtZ1dKdm50RTVHTWRnUEk3L3orbnJSd0g0Zm1MY1oyZzFCZ2lOUnpIalRFaGJDR2dpZ0lObjJLWnRLWWZtV01aN0VHTElRbmJmUEp4UnpqR2FjY1o4bjlFZ2FSa256QWZqTlBLbXdQRjJSQytFOFhBUnpwWEgxZkVNakIvUUdMV0sycm0xWkM1ajZsWS9ZWHhKUTZxdVZkcWVVVHgzMTYvS1RzcW01YUYwOVg4UWY2dnpUOFM3akorMGEyVE9aa0YzVTUyU1A5anEvdnFOa0E5WENma0Q0NzIvUjhqdmJ6Tis4cnVHK0ZMRnZGN29UbVBVN1E2dHZtTjFkU090b2VrNDFtQmc5bEptTkRDZFFkY2VEVkxHR1puV3lCN1pXNlkzR0ZsVzMrdzdtY2MvWUw0MjRsdEVReVdSTGNoRi9JcFlxVVN6aWRXR0xkdnE2MHUvWlRvNnc1clRzb2M2dVIzTGJuV2R3ZGJPTW9lRjhzdnF0YW8wTDd4U01wVlFzV3d0bG50T1Nqcm0xbkFiVlNCK1FieEJMQkRqUXRUeTNhKzBkRWRMcGFOTGxEUXJGSDNNd29pbkYvclRKMTNXUHR2c0hpQms0RDZpaHhobGRHZGs4L085amZnZThTU2oreEh4QW5HQ2VJNTRsdEZWU2Y0ckYzcGMvTFN1cVNDTHhCRmRKNXlOZVVYSjljMloyemUxa0FhUUtPZERQV2lDVTNjK2tTcTlYeWdYTEJHZHBKTmxQOXV3RXpkYWhIcXA3T0lXQUpxQU4xa0IxZTNiUzhrZ0NzVk11NmVzUjFlSys0S0ZreVNPQkx0WVRXS2ZybnlNci9mRDlZek94WDJUS3VxSjRJQTdSMTAvUnpzYXh6NWNpbkF0MWVUOEQ1RDJBRjREditTeHYxWGxYQ1Nmek9ockd1VDV5bmtjYUhFT3VxcHFFS1ZMZWMram9RdjBuUGxNckNZZHZTS1cxQWZrVStJS2hNQ25XNE05aWwxT0JITkRTSktVeFZLeDlrVUFvYUIrVHRQMDJSSnl6RzRTQTdnenBzajhIRFI0OUxLalowRU9UL25uelpCZEdoalhwNGtlR0UwMlBTcG81NExMMFNEa1k4R2xIc1dDUlNFNmxlVkczU2s0bDNpQjJGK0VNaE92N2M3dy82SnQ5UXI2U2h4TzFjaVhNaitGa2hwekxSOXUwaWovcTl4MzlEYURjSXBOMFBYNDlCeDhIZG1EWlRxeTBjdDFQem94WitsME41Rk5PaUxDYm12R2pYek5yRXNuSC84RDZ6OWpIdThIQUFBPSJ9 -->

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["track_name"],"name":[1],"type":["chr"],"align":["left"]},{"label":["artist.s._name"],"name":[2],"type":["chr"],"align":["left"]},{"label":["artist_count"],"name":[3],"type":["int"],"align":["right"]},{"label":["released_year"],"name":[4],"type":["int"],"align":["right"]},{"label":["released_month"],"name":[5],"type":["int"],"align":["right"]},{"label":["released_day"],"name":[6],"type":["int"],"align":["right"]},{"label":["in_spotify_playlists"],"name":[7],"type":["int"],"align":["right"]},{"label":["in_spotify_charts"],"name":[8],"type":["int"],"align":["right"]},{"label":["streams"],"name":[9],"type":["chr"],"align":["left"]},{"label":["in_apple_playlists"],"name":[10],"type":["int"],"align":["right"]},{"label":["in_apple_charts"],"name":[11],"type":["int"],"align":["right"]},{"label":["in_deezer_playlists"],"name":[12],"type":["chr"],"align":["left"]},{"label":["in_deezer_charts"],"name":[13],"type":["int"],"align":["right"]},{"label":["in_shazam_charts"],"name":[14],"type":["chr"],"align":["left"]},{"label":["bpm"],"name":[15],"type":["int"],"align":["right"]},{"label":["key"],"name":[16],"type":["chr"],"align":["left"]},{"label":["mode"],"name":[17],"type":["chr"],"align":["left"]},{"label":["danceability_."],"name":[18],"type":["int"],"align":["right"]},{"label":["valence_."],"name":[19],"type":["int"],"align":["right"]},{"label":["energy_."],"name":[20],"type":["int"],"align":["right"]},{"label":["acousticness_."],"name":[21],"type":["int"],"align":["right"]},{"label":["instrumentalness_."],"name":[22],"type":["int"],"align":["right"]},{"label":["liveness_."],"name":[23],"type":["int"],"align":["right"]},{"label":["speechiness_."],"name":[24],"type":["int"],"align":["right"]}],"data":[{"1":"Get Lucky - Radio Edit","2":"Pharrell Williams, Nile Rodgers, Daft Punk","3":"3","4":"2013","5":"1","6":"1","7":"52898","8":"0","9":"933815613","10":"203","11":"1","12":"8,215","13":"0","14":"0","15":"116","16":"F#","17":"Minor","18":"79","19":"87","20":"81","21":"4","22":"0","23":"10","24":"4"},{"1":"Mr. Brightside","2":"The Killers","3":"1","4":"2003","5":"9","6":"23","7":"51979","8":"15","9":"1806617704","10":"306","11":"99","12":"5,063","13":"2","14":"120","15":"148","16":"C#","17":"Major","18":"35","19":"24","20":"93","21":"0","22":"0","23":"10","24":"8"},{"1":"Wake Me Up - Radio Edit","2":"Avicii","3":"1","4":"2013","5":"1","6":"1","7":"50887","8":"34","9":"1970673297","10":"315","11":"160","12":"6,284","13":"1","14":"46","15":"124","16":"D","17":"Major","18":"53","19":"66","20":"78","21":"0","22":"0","23":"16","24":"5"},{"1":"Smells Like Teen Spirit - Remastered 2021","2":"Nirvana","3":"1","4":"1991","5":"9","6":"10","7":"49991","8":"9","9":"1690192927","10":"265","11":"121","12":"12,367","13":"4","14":"160","15":"117","16":"C#","17":"Major","18":"52","19":"73","20":"91","21":"0","22":"0","23":"11","24":"7"},{"1":"Take On Me","2":"a-ha","3":"1","4":"1984","5":"10","6":"19","7":"44927","8":"17","9":"1479115056","10":"34","11":"0","12":"5,108","13":"6","14":"0","15":"84","16":"F#","17":"Minor","18":"57","19":"86","20":"90","21":"2","22":"0","23":"9","24":"5"}],"options":{"columns":{"min":{},"max":[10],"total":[24]},"rows":{"min":[10],"max":[10],"total":[5]},"pages":{}}}
  </script>
</div>

<!-- rnb-frame-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


* In 2024:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxudG9wNV8yMDI0IDwtIGRhdGEyMDI0ICU+JVxuICBhcnJhbmdlKGRlc2MoU3BvdGlmeS5QbGF5bGlzdC5Db3VudCkpICU+JVxuICBzbGljZV9oZWFkKG4gPSA1KVxuXG50b3A1XzIwMjRcbmBgYCJ9 -->

```r
top5_2024 <- data2024 %>%
  arrange(desc(Spotify.Playlist.Count)) %>%
  slice_head(n = 5)

top5_2024
```

<!-- rnb-source-end -->

<!-- rnb-frame-begin eyJtZXRhZGF0YSI6eyJjbGFzc2VzIjpbImRhdGEuZnJhbWUiXSwibnJvdyI6NSwibmNvbCI6MjksInN1bW1hcnkiOnsiRGVzY3JpcHRpb24iOlsiZGYgWzUgw5cgMjldIl19fSwicmRmIjoiSDRzSUFBQUFBQUFBQnJWV1hXd1VWUlNlYm5kTHUzU2hDRVYrVXAzVW9HQzIwNW1kM1cyWHA1bTJVSXEwd3M2VUZpV2swOTNiM2NuT3ptem5wMzlLTEpnWW9wRWdSb0lJc1FhaWIwUWpHa01FU2Z3SmlXSU1MMEJpU0JOak5mb2dLb3JFV0wxM1p1NTJkaWlQVHJMNTd2M3VPZDg5NTU0emV5ZmROY2lHQjhNRVFWUVR3V0FWVVIyQ1F5TFVMMjV0YVNlSVlBQk9xb2dnVVlkd0FocXRoSU1tK0d0QVZ1N0M4ZzVGVnJPeW1pTjN5TG04YWJoMGVCdVFUSEpBR2dPWVdTdUkvQjV5NDdoczVzbnRsbUhLS3RraGcyR2diOEpLd2pqMEFUbzVBQ0VQZEpkK1VDZ0NSVEdnZkFHUUlnQXFLWlJrWFRiL3R6anFleDRya29LbTY1TVVSYmtjMHdmR2dGNkVPNUFiV1JwNjhxb3FROGFROUVseVMxWTJaUTNHWlpWZzlGMUFzU2JBSmw5NFlURVBZR0tnb0daZEp0S3RTSVlCaGVTaXBPRGdJc2pzQ1RsTDd1RFRUL2E0NUFwRTlnR1kxckJtNlhsTnd4SkwrbVI5VEZJbC8xNE0weHBMdGNab0p1VXlkVW1IaU5FdVVkdldhczhaUEdkYUdlUVF3dzV3TmQ3S3BGS01UN3UrWCtqdlpwZ1VIWS9SU2N4MWQvVDN0c1ZvbW82ejdJS2QwTXZFR0pwTnhWTVZITU5DdzNaNmdldmVDdmVKeHhLMGY2OUFBdThRYU1PQkJtSnQ3cWk2bmNiQ29YZzB3ZEJ3c0F4TnVEeUgycGpnd0t5RHBUTmZ3ZWNLdC8xM0ZqMGMrenA2VG1CNy9wYzViZzRPK0xuMHArRkxFSDk0TkgxdEJ1TDM1MCs5TkFUeEpubjNtcTNrMmpjSFMyakNONTFkWStQNm96dHRYTHZ2a0lOTDFoQmUrOU1mRThjUWYrTEswMmNRenF3NHVnL2hXMSt2K2hIaEczWGZiUFBZYytJbEoyNXgya0hCeFg0M0w0RWpLdlF2M3hoOUdlbGN2ZlBSQ3lqK3ErZnZka0lYL3ZxUnliM1FsRC8zU1YrOTF6N0RDVVBJWGpsNDNJNjM4T2NjaVhCMC8rWWpDSGY5dGVhUzEzN0xQN1cyWGVKa3pzYTloNTlIRWZGc1pMODliM2o0M1lwNHpxMXY3a1Q4eGVQZm5rVTRlK0hMQ3dqZkg2ejlHK0d4RDhhQ1h2dWZHdTlzUlhIZVBuejVWMWovanRXTkU2ZFhvZk4vcjJZVnl1ZnpjZkhRdE1kKzl1b2ZRWlRmYjl5ZUFWaGkvdFpESjY2Z09yMnlOSUVDNFRjZFhlZU5oM3Z4dW5OdXp6cGhjdE8xRHVabUhCeTloYyt6Z1Zqb3Zqb21ta3dsb3JFNHZVREVtWGlValNVWENOaDJVU2FCbTdNbXlVUlpObzdmVGlhZWpMWXpyRTgzeEVRWkpya3dpWmNkWUJ2VHFYTExzN2k3cTJQdGJlVmNEcmd4QTdjWHNrNmx1TDNPQVhFbG5JcDdWaU83UnUzYWpzeTBJQTkrZDhNak5qWmJGKzNhOVkzZm1QYWVWYzZaY0FPdTdwQTdiM1p4a0t2VXYvRDR3ekdrYzJwRERwbnk3MWhQelNQODhPZEROeEYrOXVid2xMZDJLdy9hcmM1WHZ6Wmg2ODAvWnlmRWI3ZzlhK1BLZkh1Ri9qUGlyWEoxMFBvQmNUTjZ5ZmpPVjZ1UUxKLy9MalJVWWYvMkYzWitvNkdUTThTOUQ1L2ZGL0RxTDJKeXZ5ZmlzNjlhR0ZiY2xDRlZLc0xMeGlsNkV5WkZYY29VOFA4enJ3eGJSYW9QMnVIRzRYVlROa3o4bjVnR0NwQU1RSFhCNjlEbGdqMUN1aE5mRXJ5aVVLSmNCRlJhVXJIb1Vuc0hTc2hvT3ZaWkxwUTBVeDZacEFSVEIxSVIzekdyTWIxVGtTWVZ1QzNWcVZtcWVkL1ZOSkF5ZVhmMWdmS3FWcklVQ1Y3RGt6aW9QWm9sV3NPQTJpMkRjY05Qb3NzYmsvV2lYQkMxQXBRd1REKzNtSjFYY0RVV1hEUzZkWHlwcEFDcTF6TGt6T0xaUlhoWlJ3c1UvSVpRc2VneUFYNVBXTVpnYndYYjJBWEFGTkFYMTdsbjBSdEdJMStVcGpSMWNjL2xPeVUxcSttU3Z5aVlkc3RvU3VpVHdpZ2ZPMVRJWmhUTnl2cjhJa0plbXBLS3poYVliQkI3dXZnZDk5Wm8yWmFKa2lKblpOUFp4ZGU0ZGJvMlR1SG1SZDBlbUhiYU8rVHY4QXo2Y25FN0hKUGhyR1JLMUlpT21wb2c1bjB1UzdTU2t3OFJRQitSTlQ3bkt0MUhORmdxaWlUYmtzbGJhcUdGU2ZqV3Ewc3ErcWNLZTk3RGlEc09lY1pOVGhpQmYxMzNHdnkrQVRVbnEvZzlDU25TTUZDd2NoYU00ZU9DQjJLZkIxWFM1WElCdzVBMUtGTXpKZXdTem1nS1p1elVpZm4vQU1JOWlSSmFDd0FBIn0= -->

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["Track"],"name":[1],"type":["chr"],"align":["left"]},{"label":["Album.Name"],"name":[2],"type":["chr"],"align":["left"]},{"label":["Artist"],"name":[3],"type":["chr"],"align":["left"]},{"label":["Release.Date"],"name":[4],"type":["chr"],"align":["left"]},{"label":["ISRC"],"name":[5],"type":["chr"],"align":["left"]},{"label":["All.Time.Rank"],"name":[6],"type":["chr"],"align":["left"]},{"label":["Track.Score"],"name":[7],"type":["dbl"],"align":["right"]},{"label":["Spotify.Streams"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["Spotify.Playlist.Count"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["Spotify.Playlist.Reach"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["Spotify.Popularity"],"name":[11],"type":["dbl"],"align":["right"]},{"label":["YouTube.Views"],"name":[12],"type":["dbl"],"align":["right"]},{"label":["YouTube.Likes"],"name":[13],"type":["dbl"],"align":["right"]},{"label":["TikTok.Posts"],"name":[14],"type":["dbl"],"align":["right"]},{"label":["TikTok.Likes"],"name":[15],"type":["dbl"],"align":["right"]},{"label":["TikTok.Views"],"name":[16],"type":["dbl"],"align":["right"]},{"label":["YouTube.Playlist.Reach"],"name":[17],"type":["dbl"],"align":["right"]},{"label":["Apple.Music.Playlist.Count"],"name":[18],"type":["dbl"],"align":["right"]},{"label":["AirPlay.Spins"],"name":[19],"type":["chr"],"align":["left"]},{"label":["SiriusXM.Spins"],"name":[20],"type":["chr"],"align":["left"]},{"label":["Deezer.Playlist.Count"],"name":[21],"type":["dbl"],"align":["right"]},{"label":["Deezer.Playlist.Reach"],"name":[22],"type":["dbl"],"align":["right"]},{"label":["Amazon.Playlist.Count"],"name":[23],"type":["dbl"],"align":["right"]},{"label":["Pandora.Streams"],"name":[24],"type":["dbl"],"align":["right"]},{"label":["Pandora.Track.Stations"],"name":[25],"type":["dbl"],"align":["right"]},{"label":["Soundcloud.Streams"],"name":[26],"type":["dbl"],"align":["right"]},{"label":["Shazam.Counts"],"name":[27],"type":["dbl"],"align":["right"]},{"label":["TIDAL.Popularity"],"name":[28],"type":["dbl"],"align":["right"]},{"label":["Explicit.Track"],"name":[29],"type":["int"],"align":["right"]}],"data":[{"1":"Blinding Lights","2":"Blinding Lights","3":"The Weeknd","4":"11/29/2019","5":"USUG11904206","6":"56","7":"194.0","8":"4281468720","9":"590392","10":"165544011","11":"83","12":"833807130","13":"10093211","14":"2882064","15":"337322563","16":"3501177394","17":"2258085924","18":"859","19":"1,695,240","20":"1,116","21":"564","22":"11701129","23":"184","24":"489299762","25":"319634","26":"28659471","27":"28994660","28":"0","29":"0"},{"1":"Heat Waves","2":"Heat Waves","3":"Glass Animals","4":"6/29/2020","5":"GBUM72000433","6":"71","7":"175.0","8":"2996181078","9":"486278","10":"112416489","11":"82","12":"1272898075","13":"14947520","14":"1416295","15":"513334446","16":"5518429969","17":"4899313022","18":"459","19":"1,414,326","20":"1,434","21":"170","22":"11862378","23":"95","24":"122247640","25":"160431","26":"0","27":"17848778","28":"0","29":"0"},{"1":"STAY (with Justin Bieber)","2":"STAY (with Justin Bieber)","3":"The Kid LAROI","4":"7/9/2021","5":"USSM12103949","6":"27","7":"266.3","8":"3107100349","9":"451732","10":"134793519","11":"78","12":"1256973582","13":"14661425","14":"7485966","15":"2246991336","16":"23712377029","17":"4327058646","18":"513","19":"1,510,151","20":"4,096","21":"166","22":"5783693","23":"128","24":"196783487","25":"124922","26":"36341585","27":"0","28":"0","29":"1"},{"1":"Sweater Weather","2":"I'm Sorry...","3":"The Neighbourhood","4":"1/1/2012","5":"USSM11300080","6":"809","7":"53.9","8":"2916412507","9":"415650","10":"149359220","11":"85","12":"1648485745","13":"18338729","14":"1248637","15":"324536571","16":"2911383718","17":"71486828","18":"189","19":"61,334","20":"39","21":"114","22":"604895","23":"9","24":"384534750","25":"719472","26":"2565635","27":"0","28":"0","29":"0"},{"1":"Smells Like Teen Spirit","2":"Nevermind (30th Anniversary Edition Super Deluxe)","3":"Nirvana","4":"9/24/1991","5":"USGF19942501","6":"4,510","7":"19.6","8":"2021910364","9":"410054","10":"113406994","11":"77","12":"348081676","13":"4710499","14":"264172","15":"95247745","16":"720283921","17":"837901","18":"287","19":"146,813","20":"287","21":"256","22":"3993523","23":"97","24":"691979509","25":"317966","26":"13047851","27":"12775440","28":"0","29":"0"}],"options":{"columns":{"min":{},"max":[10],"total":[29]},"rows":{"min":[10],"max":[10],"total":[5]},"pages":{}}}
  </script>
</div>

<!-- rnb-frame-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Computing Correlation between bpm and popularity(2023:



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubm9uX251bWVyaWNfc3RyZWFtcyA8LSBkYXRhMjAyMyAlPiVcbiAgZmlsdGVyKCFpcy5uYShzdHJlYW1zKSAmICFncmVwbChcIl5cXFxcZCskXCIsIGdzdWIoXCIsXCIsIFwiXCIsIHN0cmVhbXMpKSlcblxuZGF0YTIwMjNfY2xlYW5lZCA8LSBkYXRhMjAyMyAlPiVcbiAgbXV0YXRlKFxuICAgIGJwbSA9IGFzLm51bWVyaWMoYnBtKSxcbiAgICBzdHJlYW1zID0gYXMubnVtZXJpYyhnc3ViKFwiLFwiLCBcIlwiLCBzdHJlYW1zKSlcbiAgKSAlPiVcbiAgZmlsdGVyKCFpcy5uYShicG0pICYgIWlzLm5hKHN0cmVhbXMpKVxuYGBgIn0= -->

```r
non_numeric_streams <- data2023 %>%
  filter(!is.na(streams) & !grepl("^\\d+$", gsub(",", "", streams)))

data2023_cleaned <- data2023 %>%
  mutate(
    bpm = as.numeric(bpm),
    streams = as.numeric(gsub(",", "", streams))
  ) %>%
  filter(!is.na(bpm) & !is.na(streams))
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiV2FybmluZzogVGhlcmUgd2FzIDEgd2FybmluZyBpbiBgbXV0YXRlKClgLlxu4oS5IEluIGFyZ3VtZW50OiBgc3RyZWFtcyA9IGFzLm51bWVyaWMoZ3N1YihcIixcIiwgXCJcIiwgc3RyZWFtcykpYC5cbkNhdXNlZCBieSB3YXJuaW5nOlxuISBOQXMgaW50cm9kdWNlZCBieSBjb2VyY2lvblxuIn0= -->

```
Warning: There was 1 warning in `mutate()`.
ℹ In argument: `streams = as.numeric(gsub(",", "", streams))`.
Caused by warning:
! NAs introduced by coercion
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubWVhbl9icG1fMjAyMyA8LSBtZWFuKGRhdGEyMDIzX2NsZWFuZWQkYnBtKVxubWVhbl9zdHJlYW1zXzIwMjMgPC0gbWVhbihkYXRhMjAyM19jbGVhbmVkJHN0cmVhbXMpXG5jb3ZfMjAyMyA8LSBtZWFuKChkYXRhMjAyM19jbGVhbmVkJGJwbSAtIG1lYW5fYnBtXzIwMjMpICogKGRhdGEyMDIzX2NsZWFuZWQkc3RyZWFtcyAtIG1lYW5fc3RyZWFtc18yMDIzKSlcbnNkX2JwbV8yMDIzIDwtIHNkKGRhdGEyMDIzX2NsZWFuZWQkYnBtKVxuc2Rfc3RyZWFtc18yMDIzIDwtIHNkKGRhdGEyMDIzX2NsZWFuZWQkc3RyZWFtcylcbmNvcnJlbGF0aW9uX2JwbV9zdHJlYW1zXzIwMjMgPC0gY292XzIwMjMgLyAoc2RfYnBtXzIwMjMgKiBzZF9zdHJlYW1zXzIwMjMpXG5cbnByaW50KHBhc3RlKFwiUGVhcnNvbiBjb3JyZWxhdGlvbiBmb3IgMjAyMzpcIiwgY29ycmVsYXRpb25fYnBtX3N0cmVhbXNfMjAyMykpXG5gYGAifQ== -->

```r
mean_bpm_2023 <- mean(data2023_cleaned$bpm)
mean_streams_2023 <- mean(data2023_cleaned$streams)
cov_2023 <- mean((data2023_cleaned$bpm - mean_bpm_2023) * (data2023_cleaned$streams - mean_streams_2023))
sd_bpm_2023 <- sd(data2023_cleaned$bpm)
sd_streams_2023 <- sd(data2023_cleaned$streams)
correlation_bpm_streams_2023 <- cov_2023 / (sd_bpm_2023 * sd_streams_2023)

print(paste("Pearson correlation for 2023:", correlation_bpm_streams_2023))
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIFwiUGVhcnNvbiBjb3JyZWxhdGlvbiBmb3IgMjAyMzogLTAuMDAyNDM1MzQ3MzEwMzk1NDVcIlxuIn0= -->

```
[1] "Pearson correlation for 2023: -0.00243534731039545"
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Therefore, we can see the pearson correlation coeff is -0.002. 


## Data Visualization

Now, we have to visualize the Data we have wrangled.

Top 5 most popular playlist songs in 2023 and 2024:


In 2023, the 5 most popular songs in playlists were:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGlicmFyeShnZ3Bsb3QyKVxuXG5nZ3Bsb3QodG9wNV8yMDIzLCBhZXMoeCA9IHRyYWNrX25hbWUsIHkgPSBpbl9zcG90aWZ5X3BsYXlsaXN0cykpICtcbiAgZ2VvbV9iYXIoc3RhdCA9IFwiaWRlbnRpdHlcIiwgZmlsbCA9IFwiYmx1ZVwiKSArXG4gIGNvb3JkX2ZsaXAoKSArXG4gIGxhYnModGl0bGUgPSBcIlRvcCA1IFNvbmdzIGluIFNwb3RpZnkgUGxheWxpc3RzICgyMDIzKVwiLFxuICAgICAgIHggPSBcIlRyYWNrIE5hbWVcIixcbiAgICAgICB5ID0gXCJOdW1iZXIgb2YgUGxheWxpc3RzXCIpICtcbiAgdGhlbWVfbWluaW1hbCgpXG5cbmBgYCJ9 -->

```r
library(ggplot2)

ggplot(top5_2023, aes(x = track_name, y = in_spotify_playlists)) +
  geom_bar(stat = "identity", fill = "blue") +
  coord_flip() +
  labs(title = "Top 5 Songs in Spotify Playlists (2023)",
       x = "Track Name",
       y = "Number of Playlists") +
  theme_minimal()

```

<!-- rnb-source-end -->

<!-- rnb-plot-begin eyJoZWlnaHQiOjQzMi42MzI5LCJ3aWR0aCI6NzAwLCJzaXplX2JlaGF2aW9yIjowLCJjb25kaXRpb25zIjpbXX0= -->

<img src="data:image/png;base64,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" />

<!-- rnb-plot-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

In 2024, the 5 most popular songs in playlists were:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2dwbG90KHRvcDVfMjAyNCwgYWVzKHggPSBUcmFjaywgeSA9IFNwb3RpZnkuUGxheWxpc3QuQ291bnQpKSArXG4gIGdlb21fYmFyKHN0YXQgPSBcImlkZW50aXR5XCIsIGZpbGwgPSBcImdyZWVuXCIpICtcbiAgY29vcmRfZmxpcCgpICtcbiAgbGFicyh0aXRsZSA9IFwiVG9wIDUgU29uZ3MgaW4gU3BvdGlmeSBQbGF5bGlzdHMgKDIwMjQpXCIsXG4gICAgICAgeCA9IFwiVHJhY2sgTmFtZVwiLFxuICAgICAgIHkgPSBcIk51bWJlciBvZiBQbGF5bGlzdHNcIikgK1xuICB0aGVtZV9taW5pbWFsKClcbmBgYCJ9 -->

```r
ggplot(top5_2024, aes(x = Track, y = Spotify.Playlist.Count)) +
  geom_bar(stat = "identity", fill = "green") +
  coord_flip() +
  labs(title = "Top 5 Songs in Spotify Playlists (2024)",
       x = "Track Name",
       y = "Number of Playlists") +
  theme_minimal()
```

<!-- rnb-source-end -->

<!-- rnb-plot-begin eyJoZWlnaHQiOjQzMi42MzI5LCJ3aWR0aCI6NzAwLCJzaXplX2JlaGF2aW9yIjowLCJjb25kaXRpb25zIjpbXX0= -->

<img src="data:image/png;base64,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" />

<!-- rnb-plot-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



Visualization for correlation between bpm and popularity in 2023:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2dwbG90KGRhdGEyMDIzX2NsZWFuZWQsIGFlcyh4ID0gYnBtLCB5ID0gc3RyZWFtcykpICtcbiAgZ2VvbV9wb2ludChjb2xvciA9IFwiYmx1ZVwiKSArXG4gIGdlb21fbGluZShjb2xvciA9IFwiZ3JlZW5cIikgK1xuICBsYWJzKHRpdGxlID0gXCJCUE0gdnMuIFN0cmVhbXMgKDIwMjMpXCIsXG4gICAgICAgeCA9IFwiQlBNXCIsXG4gICAgICAgeSA9IFwiU3RyZWFtc1wiKSArXG4gIHRoZW1lX21pbmltYWwoKVxuYGBgIn0= -->

```r
ggplot(data2023_cleaned, aes(x = bpm, y = streams)) +
  geom_point(color = "blue") +
  geom_line(color = "green") +
  labs(title = "BPM vs. Streams (2023)",
       x = "BPM",
       y = "Streams") +
  theme_minimal()
```

<!-- rnb-source-end -->

<!-- rnb-plot-begin eyJoZWlnaHQiOjQzMi42MzI5LCJ3aWR0aCI6NzAwLCJzaXplX2JlaGF2aW9yIjowLCJjb25kaXRpb25zIjpbXX0= -->

<img src="data:image/png;base64,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" />

<!-- rnb-plot-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->




## Conclusion

The 5 most popular songs in the 2023 playlist were(in increasing order of playlist presence):

i) Take on me
ii) Smells Like Teen Spirit - Remastered 2021
iii) Wake Me Up - Radio Edit
iv) Mr. Brightside
v) Get Lucky - Radio Edit

The 5 most popular songs in the 2024 playlist were(in increasing order of playlist presence):

i) Smells Like Teen Spirit
ii) Sweater Weather
iii) STAY(with Justin Bieber)
iv) Heat Waves
v) Blinding Lights


With regards to the BPM Vs Streams Correlation: 

There seems to be a slightly negative correlation between BPM and Popularity of Songs, and the graph reflects that there is no correlation that proves that the higher the BPM of a song.





<!-- rnb-text-end -->

