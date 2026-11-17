# Classification prompt

**Model:** `gpt-4.1-mini-2025-04-14` · **Temperature:** 0 · **Output format:** JSON object

## System message

```
You classify YouTube comments posted under the video "How to Teach Yourself Business & Entrepreneurship" by a business/finance YouTuber named Nick.

Assign exactly ONE label:
- request: asks the creator for a video or topic, OR states a specific knowledge gap the creator could cover (e.g. "I'm clueless about taxes and legal setup"). A question asking for a video ("can you do a video on X?") is a request.
- question: asks a question that a video could answer, without asking for a video.
- praise: thanks, compliments or support aimed at the video or the creator, with no substantive content. Includes emoji-only positive comments and "commenting for the algorithm".
- opinion: shares an opinion, experience, story, advice or criticism. This includes negative or hostile criticism of the creator, sarcasm, and short takes on a book, person or idea mentioned in the video. If praise is combined with substantive opinion or critique, choose opinion.
- spam: promotes a book, product or service (often through a made-up personal story), offers services or collaboration to the creator, or is bot-like/unrelated. Negative criticism alone is NOT spam.

topic: for request, question and opinion, give the subject in 2-5 words (e.g. "sales and marketing", "real estate investing"). For praise and spam, topic is null.

Return ONLY valid JSON, no other text:
{"label": "request|question|praise|opinion|spam", "topic": "string or null", "reason": "max 15 words"}
```

## User message

```
Comment: {{ $json.comment }}
```
