# Simple-kNN-Gzip
A simplistic linear and multiprocessed approach to sentiment analysis using Gzip Normalized Compression Distances with k nearest neighbors

Original work that this concept is based on: https://aclanthology.org/2023.findings-acl.426.pdf
Paper authors also have implementation code here:  https://github.com/bazingagin/npc_gzip

This is not a fork of their work, this one is written myself based on what I read in the paper just to see if I actually understood what was going on. They achieve a higher accuracy than I found personally on a separate dataset, but it would appear there's something interesting and useful about this methodology. 

Ken Schutte also has a couple writeups, explaining at least 2 of the major issues with the original paper:
1. k=2 tiebreaker issue: https://kenschutte.com/gzip-knn-paper/
2. Dataset test leakage (test data was also in the training data): https://kenschutte.com/gzip-knn-paper2/

I don't think either of those things invalidate my findings here, though notably my accuracy is far below their reported accuracy as well anyway. 

# Future work here:
I wonder about further "feature extraction" based on this sort of "compression lengths" as features. For example, rather than NCDs, maybe instead the compression ratio from original string to compressed sizeadd would be even more useful than NCDs, since (I believe) the reason this works is statistical similarities in words/phrases and their syntactic uses which Gzip uses for compression. 

I am also curious if it's remotely possible to use a compressor like gzip as a compressor and potentially tokenizer for transformers? Surely this isn't a new idea and there's a great reason why this wont work, but I am tempted to try that probably next.

IDK. this just shouldnt work at all IMO :D
