## for loop

`{Array.from({ length: rating }, (_, index) => (`\
`       <Star className="star" key={index} />`\
`      ))}`


## Switch case
`{`\
`        {`\
`          'My Feedback': <MyFeedback Component/>,`\
`          'All Feedback': <All Feedback Component />`\
`        }[selectedOption]`\
`}`



## Error image
`onError={(e) => (`\
`              ((e.target as HTMLInputElement).onerror = null),`\
`              ((e.target as HTMLInputElement).src = Placeholder)`\
`             )}`
