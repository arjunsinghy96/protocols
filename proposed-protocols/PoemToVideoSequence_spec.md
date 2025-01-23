# Poem-to-Video-Sequence  (Text to Video and Audio)

## Goal

Given a poetic text, the model should generate a cohesive sequence of short videos that visually illustrate the poem and are syncronized with audio narration reading the poem text. The videos must maintain a consistent visual style, narration audio style and character reperesentiaont if mentioned twice in the poem .  

## Evaluation

Outputs will be evaluated based on:
- **Narrative Alignment**: The video sequence should accurately reflect the poem's themes and imagery.
- **Video Quality**: The video quality will begraded on realism and relation to the text. Aswell asneeding a  consistent style (e.g., color palette, animation style, or cinematography) throughout all video segments.
  - Extra score will be given to responses that have the same characters visually depicted in more than one of the videos. 
- **Audio Quality**: The narration must be clear and synchronized with the visual elements. Background music and sound effects should enhance the poem's tone without overshadowing the narration.
  - The narration should accurately reflect the poem without altering its meaning or tone.

- All media (visuals, music, sound effects) must be original or adhere to copyright laws.


## Action

### `GeneratePoemVideo()`
- **Params**:
  - `poemText` (string): The text of the poem to illustrate. Max 2000 characters.
  - `visualStyle` (string, optional): Desired visual and audio style style, such as `realistic`, `cartoon`, `minimalist`, or anything else. Max 300 characters
  - `voiceStyle` (string, optional): Voice style for narration (e.g., `calm`, `dramatic`, `neutral`). Defaults to `calm`.  Max 300 characters 
- **Returns**:
   - `JSON` object with an arrow of videos (http links) and the portion of the poem that is depicted and spoken in that section.  Each section should include video link and the text from the poem prompt that is being spoken there.
        - `videoLink` (string): An HTTP link to the generated video file.
        - `textSection` (string):  The text which is represented and spoken in this section 
     - All videos should be in MP4  encoding.
     - Each video should have a resolution of 720 × 1280 
     - Each video section should between 1 and 10 seconds long.  
     - All videos together should not be longer than 90 seconds 

## Performance Requirements
- Query response within 60 minutes for a video up to 1 minute length.
- Rate limit of at least 1 request per 60 minutes.
- Minimum 30 API calls per subscription per month.


## Example 

~~~~~~~
When the flush of a newborn sun fell first on Eden's green and gold,   
Our father Adam sat under the Tree and scratched with a stick in the mold;   
And the first rude sketch that the world had seen was joy to his mighty heart,   
Till the Devil whispered behind the leaves: "It's pretty, but is it Art?"   
   
Wherefore he called to his wife and fled to fashion his work anew— 
The first of his race who cared a fig for the first, most dread review;   
And he left his lore to the use of his sons—and that was a glorious gain   
When the Devil chuckled: "Is it Art?" in the ear of the branded Cain.   
   
They builded a tower to shiver the sky and wrench the stars apart,   
Till the Devil grunted behind the bricks: "It's striking, but is it Art?" 
The stone was dropped by the quarry-side, and the idle derrick swung,   
While each man talked of the aims of art, and each in an alien tongue.   
   
They fought and they talked in the north and the south, they talked and they fought in the west,
Till the waters rose on the jabbering land, and the poor Red Clay had rest—   
Had rest till the dank blank-canvas dawn when the dove was preened to start,  
And the Devil bubbled below the keel: "It's human, but is it Art?"   
   
The tale is old as the Eden Tree—as new as the new-cut tooth—   
For each man knows ere his lip-thatch grows he is master of Art and Truth;   
And each man hears as the twilight nears, to the beat of his dying heart,   
The Devil drum on the darkened pane: "You did it, but was it Art?"

~~~~~~~
Good Video response : 
CID   QmZxFGNbaMZ7FoHbN2PUgMe5ED4GmueAEajazZRh187bjx   

https://rolling-rose-frog.myfilebase.com/ipfs/QmZxFGNbaMZ7FoHbN2PUgMe5ED4GmueAEajazZRh187bjx?download=true&filename=sample_video_output_PoemToVideo.mp4 

https://i.imgur.com/poIiEgO.mp4  


https://github.com/user-attachments/assets/15555589-36b9-4980-bc85-1430fae95a55



