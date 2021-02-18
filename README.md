# Discord Emote Data Freaks
by Dennis Wang

This project is intended to be a data visualization exercise for emote usage by a certain Discord server. Quantitative measures of interest include total frequency of each emote and frequency/day usage of that emote since its addition to the server. The results of this project would be used to better inform the decision as to which emotes will be purged from the Discord server due to limited emote slots.

Data collected and cleaned by Elias on 1/31/2021.

## [Published Deepnote Project](https://deepnote.com/publish/f3f0cdc0-9d67-4ea8-b8bf-c520b1e27f8e)

## Data Collection and Cleaning
Data on the frequency of each emote was collected by recording the number of search results in Discord's search function for that particular emote's ID.

The dataset contains 90 rows for each of the emotes, and seven columns that refers to the emote ID, its total usage, the month it was added, the current month, the total days that have passed since adding, and the Usage of the emote per day.

Usage per day is a derived column calculated by dividing total frequency by the number of days since adding that emote.

## Findings
Usage per day is likely the best metric to decide which emotes to be cut. Since new emotes are regularly added to the server, total usage may not be the best metric since older emotes will naturally have higher total usage frequencies while new emotes will have lower total usage. Therefore, dividing the total usage of the emote by the number of the days it has been in the server will push older, no-longer-used emotes lower in priority to be saved, and newer, heavily used emotes higher in priority. This gives a better idea as to which emotes are most relevant and used today. 

Creating a barchart shows that the five least used emotes by usage per day are :doubt:, :betterbelieveit:, :lamon:, :huh:, and :keanu:. These emotes will likely be considered to be cut. 

A double bar chart comparing the total usage and usage per day of the top 10 emotes by usage per day shows that while :kek: has the highest total frequency, it only has the second highest frequency per day. Instead, :edwardu: holds the highest frequency per day, indicating that it's currently more popular and will likely overtake :kek: in total frequency sometime in the near future. Other emotes such as :smug: and :oh: have high total frequency but lower frequency per day, indicating that these emotes are not as popular as they used to be.

As a data visualization exercise, a histogram was used to visualize the shape of the total usage and usage per day distribution of data. Visualizing the distribution of the data can show which emotes are distinctly the most used emotes (i.e. outliers). To reduce possible binning bias, a swarmplot from the Seaborn statistical visualization library was used. There are about eight emotes that are clearly distinct in total usage rate compared to others. These are :kek:, :edwardu:, :oh:, :smug:, :hell:, :karCHAMP:, :killme:, and :pepewoah:. On the other hand, when using usage per day to get more relevant and current results, there were only three distinctly popular emotes. These were :edwardu:, :kek:, and :killme:. This indicates that popular emotes tend to slide in and out of common use as new emotes continuously get added to the server and old emotes get cut.

## Further Avenues of Exploration
Since each Discord message is timestamped, it should theoretically be possible to record emote use per day (not averaged). This information could be used to observe how changes in emoji use can vary throughout the week (e.g. Mondays may have more :pensive:-related emojis while Fridays may have more :pepewhoah:'s). We could also see how emoji use coincides with holidays and news events such as Christmas and the US presidential election, respectively.

This data can be visualized through a linechart to emphasize change throughout time. In addition, machine-learning models such as regression trees could be applied to predict the usage of certain emojis on certain days of the week. Another method, association rules, can be used to see if certain emojis tend to be used in conjunction with each other.

While of course data collection is the biggest hurdle to this endeavor, coding a Discord bot to automatically collect these user metrics in regards to emote use, while a challenge, could be another (related) exciting project to tackle.


