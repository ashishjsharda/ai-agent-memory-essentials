
# Segment 3 Bonus — messing around with the memory patterns

**Bigger window.** Went from 4 to 6 to 8 turns. The name was buried 8 turns back, so 6 still misses it. You need the full 8 to catch it. Bigger window remembers more but costs more tokens. Nothing's free.

**Moved the name later.** Same tiny 4 turn window, but put "my name is Aria" at turn 8 instead of turn 2. Caught it no problem. The window didn't change at all. It just depends on whether the important bit lands inside or outside it. Kind of random honestly.

**Told the summarizer to keep names.** Added "always keep the user's name" to the summarization prompt. Actually helps, but only with a real LLM call. The offline stub in the notebook just does dumb keyword matching, it's not following instructions at all. So this one's basically invisible unless you've got a real API key plugged in.

**Combined window and summary.** This is the one that actually matters. Keep the last few turns word for word, and instead of tossing everything older, compress it into a running summary. Best of both. Recent stuff stays accurate, old stuff doesn't just vanish. Pretty much what real memory systems do.

