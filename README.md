Learning Sequence: <br>
1. `RAG_Reformulate.py`<br>
2. `RAG_Hybrid_Retrieval.py`<br>
3. `RAG_Re-ranking.py`<br>

4. `RAG-Part2/1-RAG-PDF-Split`<br>
5. `RAG-Part2/2-RAG-LLM`<br>
6. `RAG-Part2/3-RAG-Eval`<br>

1-3 are basic RAG rechniques.<br>
4-6 We chunk the PDF, then the retrieved text are as the context inputted into the LLM (qwen2-0.5) to get the response/answer, and finally evaluate this RAG using metrics such as hit rate. 

---

1.Reformulate: Use **BART model** to reformulate.

```python RAG_Reformulate.py```

![1](https://github.com/user-attachments/assets/41e145b6-0979-4b71-a83b-fbfc299c0f0d)


2.Hybrid Retrieval：sparse (BM25) + dense (FAISS + Sentence Transformer Embeddings)

```pip install faiss-gpu```<br>
```python RAG_Hybrid_Retrieval.py```

![2](https://github.com/user-attachments/assets/571993af-ecf8-4828-ac2b-4f77dba5ad31)


3.Re-ranking: Use cross-encoder (ms-marco-MiniLM-L-6-v2) to count the scores of the pair data (query + initial retrieval results), and then rerank based on the scores.

```python RAG_Re-ranking.py```

![3](https://github.com/user-attachments/assets/8a06d5ba-be5d-488f-9af4-c578e7b050a8)
