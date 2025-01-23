# Social Reply (Text to Text)

## Goal

Given the text of a social media post, the model should generate relevant, concise, and engaging comments tailored to the threads's tone and audience. The comments should aim to maximize interaction.

## Evaluation

Generated comments will be evaluated for:

- Relevance to the original post
- Engagement potential (e.g., humor, thoughtfulness, or insight)
- Conciseness (limited to the platform's character constraints)
- Appropriateness (avoiding offensive or controversial remarks unless humor or satire is explicitly requested in the input)

## Actions

### `GenerateComment()`

- **Params**:

  - `postText` (string): The text of the social media post. It is not expected that links are read if a link is included the user can include that in the context.
  - `context` (string, optional): Can contain other related posts to define the theme, like it being crypto twitter, or left win twitter, or other themes.

- **Returns**:
  - `text`: A single comment relevant to the post
  - UTF-8 encoded and under 1KB in size.
