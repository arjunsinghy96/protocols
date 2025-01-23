# Media Commentary Humor    (Text + Image to Image)


## Goal

Given an image of a public person and text description of a current event the model should produce an satirical image and text commentary with the goal of maximizing entertainment value relevant to the event.  

## Evaluation 

Image responses will be human evaluated for relevance and humor.  If resposne is funny but not related to the current event it should receive a low score. 
Two responses should be returned one which is targeted to be funny for a left leaning audiance and one which is desiged to be funny for the right leaning audiance. Validators will consider the humar and relevance score for each response with respect to the target group but will only report one score, the maximum of both scores. 

It is permissable for a model (miners) to focus one one audiance type leaving the second image black but validators must be capable of judging humor quality for both audiance types. 

The subnet will start by restricting current events to US current events or global events interesting for the US audience.  In the future 


## Actions 

### `EventImageToMeme_US()`
- **Input Arguments**:
  - `promptTect` (string):  Text Describing current event.  Max 4000 characters.  
  - `promptImage` (string):  An image of a person place or thing related to the event.  200KB in size.   JPEG or  PNG encoded.  
- **Returns**:
   - `JSON` object with two satirical images about the event one designated for a left leaning audiance one targeting a right leaning audience. 
    - Images are output as HTTP links to be loaded seperately 
    - Images must be <1MB in size 
    - Images must be 1024 x 1024 pixels. 
    - Supported image encodings are JPEG and PNG 
- **Performance  Requirements**:
    - Query response within 30 seconds
    - Rate limit of at least 1 request per 30 seconds.
    - Minimum 100 API calls per subscription per month.



