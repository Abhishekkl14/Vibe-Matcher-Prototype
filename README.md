# Vibe-Matcher-Prototype

**Vibe Matcher**
Ever tried searching for clothes online but couldn't find the right words? You're not looking for a "blue shirt," you're looking for a "chill, beachy, summer vibe." This project is a simple prototype of a search engine that gets that.It's a "Vibe Matcher"! Instead of matching keywords, it matches meaning and feeling. This script is a hands-on demo of how modern "semantic search" works, all in one runnable Python file.

**How it Works**

It's basically a matchmaker for your feelings and your products.
Starts with Products: It loads a small, hard-coded list of 7 fashion items (like a "Boho Dress" or "Urban Techwear Jacket"). Learns the Vibe: It uses an AI embedding model (sentence-transformers) to "read" all the product descriptions and turn them into "vibe vectors" (just lists of numbers that represent their meaning).Understands You: You provide a query, like "cozy and relaxed for a weekend in". Finds the Match: It turns your query into a vector, too. Then, it uses math (cosine similarity) to find the product vectors that are "closest" to your query's vector. Shows the Results: It prints out the Top 3 products that best match your vibe!

**What's Inside?**

This isn't just a simple script; it's a full prototype designed to be studied:
100% Local & Free: It uses the sentence-transformers library, so it runs entirely on your machine. No API keys or "free trials" needed. (The first run will download the model).
Professional Test Harness: I built a data-driven test suite (see Section 4) that automatically runs multiple test queries to prove that:
"energetic urban chic" correctly finds the Techwear Jacket.
"cozy and relaxed" correctly finds the Knit Cardigan.
"food for my dog" (an irrelevant query) is correctly identified as a weak match.
The "Why This Doesn't Scale" Test: The best part! Section 5 includes a latency test (timeit + matplotlib) that simulates how slow this search gets as you add more products. It proves why this simple O(n) "scan-everything" approach is only good for demos, and why real apps use...
The Reflection: The final section of the script (and this project) is a reflection on what's next. This prototype is the "before" picture, and the "after" would be plugging this logic into a real vector database (like Pinecone, FAISS, or Weaviate) to get lightning-fast results.

**How to Use**

Make sure you have Python 3.
**Install the libraries:
**
pip install pandas scikit-learn sentence-transformers matplotlib
Just run the script!

python vibe_matcher_code.py

That's it. You'll see the test harness run and then a plot will pop up showing the latency. Feel free to tweak the queries in Section 4!
