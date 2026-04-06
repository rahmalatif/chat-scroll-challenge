UX Issues Identified and Fixed
1. Auto-scroll always triggered on new messages

Issue:
The chat view always scrolled to the bottom whenever a new message was added, even if the user was reading older messages.

Fix:
Implemented conditional auto-scroll logic. The chat now checks whether the user is currently at the bottom before automatically scrolling. Auto-scroll only happens if the user is already near the bottom.

2. Auto-scroll during streaming responses

Issue:
While messages were streaming in chunks, the chat continuously forced scrolling to the bottom, which made it impossible for the user to read older messages while a response was still streaming.

Fix:
Auto-scroll during streaming is now conditional. The chat only scrolls while streaming if the user is at the bottom. If the user scrolls up, auto-scroll pauses until the user scrolls back down.

3. Pause auto-scroll on manual scroll

Issue:
When the user manually scrolled up, the chat did not properly pause auto-scroll behavior.

Fix:
Added scroll position tracking to detect whether the user is at the bottom or not. Auto-scroll is paused when the user scrolls up and resumes automatically when the user scrolls back to the bottom.

4. Resume auto-scroll when returning to bottom

Issue:
Auto-scroll did not always resume correctly after the user manually scrolled back to the bottom.

Fix:
Implemented bottom detection logic so that once the user scrolls near the bottom again, auto-scroll is re-enabled automatically for new and streaming messages.

Technical Implementation Summary:
Implemented scroll position tracking using ScrollController.
Auto-scroll is triggered only when the user is near the bottom.
Manual scrolling disables auto-scroll temporarily.
Auto-scroll resumes automatically when the user scrolls back to the bottom.
Streaming messages also respect the auto-scroll state.


## Deployed URL
[https://amazing-site-123.netlify.app](https://quiet-sprite-4e726e.netlify.app/)
