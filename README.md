First Tableau Data App - style viz for MakeoverMonday 2026 Week 45, exploring Hot Air Balloons data. 

# 🎈 Hot Air Balloons | an explorer
 
An interactive explorer of **7,235 hot air balloons** from [The HAB Database](https://thehabdatabase.com/), built for **[#MakeoverMonday 2026 · Week 45: Hot Air Balloons](https://makeovermonday.vercel.app/dataset/hot-air-balloons)** (9 November 2026).
 
**▶ Live app:** `https://<your-username>.github.io/hot-air-balloon-explorer/`
**▶ On Tableau Public:** `<link to your Tableau Public viz>`
 
Designed by **Serena Purslow** with **Claude**.
 
---
 
## What's inside
 
The app has five pages. Use the navigation panel on the left to move between them; the filters underneath it (search, status, type, manufacturer, location and year built) apply to every page.
 
| Page | What you can explore |
|---|---|
| **Overview** | Headline figures drawn as floating balloons, balloons built per year (still in service vs out of service), the top manufacturers, and the mix of balloon types. Click a year, a maker or a type to see how the other charts change. |
| **Size** | A "size ladder" with balloons drawn to scale by volume, whether balloons are getting bigger over time, and the most common exact sizes. Sizes are in cubic feet (ft³), with metric equivalents in the tooltips. |
| **Location** | A US tile map and a chart of other countries. Click any state or country to meet its balloons: its key figures, biggest fleets and manufacturers. |
| **Pilots & Owners** | The top 20 fleets. Click a pilot to see every balloon they own and compare how often their balloons have changed hands. |
| **Balloon Finder** | Searchable, sortable cards for every balloon. Click one for its full details and a link to its photo. |
 
And, as requested, the occasional hot air balloon drifts up the page and disappears. They can be switched off with the button at the top right, and they stay hidden for anyone whose device is set to reduce motion.
 
## How the clicks work
 
- **The filters in the left-hand panel** apply to every page.
- **Clicking a chart** only affects the page you're on. It appears as a blue "Selected" chip and clears when you move to another page.
- **"Browse" buttons and clickable sizes** hand you over to the Balloon Finder, showing just those balloons.
## About the data
 
The data comes from [The HAB Database](https://thehabdatabase.com/), shared for Makeover Monday via [Kaggle](https://www.kaggle.com/datasets/matthuff4/hot-air-balloon) by Matt Huff.
 
A few notes on how it was prepared:
 
- Around 700 rows in the original spreadsheet were broken fragments of the row above (long "previous owners" entries had split across rows). These were stitched back together, leaving **7,235 balloons**.
- Sizes were converted from text such as "90,000 cu ft." into numbers. Build years like "1983, Rebuilt: N/A" were reduced to the first year, and impossible years were removed.
- Locations are a mix of US states and countries. US states are grouped as the USA for the map and the country chart.
- Balloons with more than one type are grouped under one main type: Special Shape, then Racer, then Hopper, then Standard.
- Some balloons have no size, year or location recorded, so they don't appear in the charts that need those fields.
## Built with
 
- A single `index.html` file: plain HTML, CSS and JavaScript, with no frameworks or build step. The data is embedded in the page.
- Every balloon illustration is drawn in code (SVG), so each balloon in the Finder gets its own generated design.
- Fonts: [Poppins](https://fonts.google.com/specimen/Poppins) and [Caveat](https://fonts.google.com/specimen/Caveat) from Google Fonts.
- Hosted on GitHub Pages and embedded in Tableau Public with a Web Page object.
### Inspiration
 
- [Major Marathons 2000–2026](https://public.tableau.com/app/profile/rob.taylor6175/viz/MajorMarathons2000-2026/SixMajors) by Rob Taylor, for the idea of building a Data App-style page and embedding it in Tableau Public.
- [Kyoto, Japan | Cherry blossom seasonality](https://public.tableau.com/app/profile/shreya.arya/viz/KYOTOJAPANCherryblossomseasonalityB2VB/CherryBlossoms) by Shreya Arya, for the whimsical, airy feel.
- My own [Human Resources Dashboard](https://public.tableau.com/app/profile/serena.purslow/viz/HumanResourcesDashboard-RWFD/Overview) and [The Updated Visual Vocabulary](https://public.tableau.com/app/profile/serena.purslow/viz/TheUpdatedVisualVocabulary/VisualVocabularyEntryPage), for the colours and overall look.
---
 
## How it was made: my prompts
 
This app was built in a conversation with Claude. These are the prompts I used, in order, from my first question about Tableau Data Apps to the final tweaks.
 
<details>
<summary><b>1. Getting started</b></summary>
> Hi, I want to create a Tableau Data app but not sure how to get started - can you walk me through the process so I can get to creating one today?
 
> Can I create a tableau data app that's hosted on tableau public?
 
When Claude asked about data, hosting and style, I chose to share my own file and to host on GitHub Pages, and for the style I answered:
 
> My data viz style which you can see via these two vizzes: https://public.tableau.com/app/profile/serena.purslow/viz/TheUpdatedVisualVocabulary/VisualVocabularyEntryPage and https://public.tableau.com/app/profile/serena.purslow/viz/HumanResourcesDashboard-RWFD/Overview
 
</details>
<details>
<summary><b>2. The brief</b></summary>
> This is the data, that comes from this website - https://thehabdatabase.com/ - for this makeover monday challenge - https://makeovermonday.vercel.app/dataset/hot-air-balloons. What I'd like to do is create an interactive explorer of the different hot air balloons, being able to explore them by size, location, pilots and locations to see trends. I'd like the visuals to be really cool with some hot balloon designs and I'd love it if there could be the occasional hot air balloon floating in the background from the bottom to the top of the page then disappearing.
 
</details>
<details>
<summary><b>3. Making the interactions make sense, and a more whimsical look</b></summary>
>There's a few changes I'd like before we do anything with it. Some of the click to filter actions don't make sense - for example on the location page, why would you filter the by the UK as it doesn't relate to any other data in the view? Can you review some of the filter actions to make sure they make sense. The second thing is the general design, whilst it looks really like my style, I'd like it to be a little more whimsical - perhaps something that looks a bit more like this: https://public.tableau.com/app/profile/shreya.arya/viz/KYOTOJAPANCherryblossomseasonalityB2VB/CherryBlossoms - but still using my colours and general look. Can you also edit the design acknowledgment to include Claude? I also would love it if the hot air balloons were more visible.
 
</details>
<details>
<summary><b>4. Finding the middle ground</b></summary>
> Okay lets go somewhere in between. I think now the background is too bright that it's in competition with the actual bits of the viz, and I still prefer the navigation being on the left hand side. I also don't like the hot air balloons at the end of the bars as it makes it difficult to read, and I prefer the bars to be thicker. But I love the general background with the moving clouds but I don't like the swirly bits at the bottom. Also why is it called envelope volume/size? Would it be better to say balloon?
 
</details>
<details>
<summary><b>5. Polishing</b></summary>
> Okay loving it. Have a few more thoughts. I think the background could be a tiny bit paler, and a few less balloons floating up. For the balloon KPIs I'd like the colours to be a bit brighter. For the title - make it a little bigger and reduce the intensity of the colours in the subtitle. I'd like the navigation panel to align all the way to the bottom, matching the bottom point of the other chart sections. On the Overview page - the balloons by type could do with some sort of % of total visual in there. On the location page - I'd like the bar charts in the meet the balloons section to take up more of the space, so there's less white space below them. In the pilots and owners section - the biggest fleets is that a top 20 or random selection or all the fleets? 
 
> The featured fleet section shouldn't have white space at the bottom - can we make it take up that whole box, and then I'd prefer the balloons by type bar to be a bit more transparent, and underneath the balloons. With regards to colours  - on the overview page, purple is used to mean quite a few things - perhaps we should change the colour on the balloons per year chart to be a bit different? 
 
> The balloon KPIs - I don't like the stripes, can we make them an ombre/radial fade type effect? and then I don't like the colours on the balloons built per year, can we make the green a touch more vibrant and then the shade different between out of service and unknown a bit stronger? also does cu ft mean cubic feet? I think this should be detailed somewhere if possible on the sizes charts. Or would it make more sense to write cubic feet as ft3? not sure
 
> Okay great. Final thing can you add somewhere which makeover monday challenge it was, perhaps above the title and at the bottom?
 
</details>
---
 
## Credits
 
- **Design:** Serena Purslow, with Claude
- **Data:** [The HAB Database](https://thehabdatabase.com/), via [Kaggle](https://www.kaggle.com/datasets/matthuff4/hot-air-balloon) and [#MakeoverMonday](https://makeovermonday.vercel.app/dataset/hot-air-balloons)
- The balloon data belongs to The HAB Database and isn't covered by any licence in this repository.
