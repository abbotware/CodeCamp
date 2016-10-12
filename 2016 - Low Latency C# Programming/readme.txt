PseudoDisrupter (not the real disrupter pattern)

it is very quick attempt to show non-blocking/lock-free designs.  It does not perform well under extreme load since consumers have to keep 'repeating' their work until their 'transaction' is committed via the CompareExchange.  There is no built in 'fairness' / scheduler to properly balance the work between the consumers.  The real disrupter pattern does not have this issue.

SuperCollider

Removes the flaw, but uses a lock (hence the name) on the shared resource. The queue is still non-blocking queue, and it performs much better underload as no cpu cycles are wasted repeating the same work. The lock has a built in wait queue so the work gets more evenly distrbuted and scheduled between consumers.
