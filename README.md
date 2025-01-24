
# HelpMateAI with RAG  
**Retrieval Augmented Generation for HDFC Insurance Policy Documents**  

This project demonstrates a **RAG (Retrieval Augmented Generation)** framework designed to retrieve information from seven types of HDFC insurance policy documents using LlamaIndex.  

### Key Components:
1. **Information Retriever**: Finds the most relevant documents based on the query.  
2. **LLM Generator**: Uses the retrieved documents and query to generate responses.  

### How It Works:
- **Vector Database Creation**:  
   Documents are split into chunks and stored in a vector database for semantic search.  

- **Query Response Workflow**:  
   - Retrieve the most semantically similar documents.  
   - Combine the documents with the user query and pass them to the LLM generator for a response.  

---

### System Architecture:
1. **Document Reading**:  
   - Used `SimpleDirectoryReader` and `PDFReader` to read various insurance PDF files.  

2. **Data Parsing and Indexing**:  
   - Parsed documents into nodes with `SimpleNodeParser`.  
   - Created an index using `VectorStoreIndex` from LlamaIndex.  

3. **Query Engine**:  
   - Built a query engine to handle user queries.  
   - Allows interaction in a chat format with functions like `query_response` and `initialize_conv`.  
   - Includes user feedback through a rating system.  

4. **Tracking Responses**:  
   - Maintained a **pandas DataFrame** with columns:  
     - *Question*  
     - *Response*  
     - *Page*  
     - *Review*  

---

### Enhancements Made:
1. **Custom Prompting**:  
   Tested OpenAI’s GPT-3.5 Turbo and Microsoft’s phi-3 mini 4k LLM models for better responses.  

2. **Improved Embeddings**:  
   Used advanced embedding models like:  
   - `all-mpnet-base-v2`  
   - `bge-small-en-v1.5`  

3. **Sub-Question Querying**:  
   Implemented a sub-question structure for faster, smoother querying.  

--- 

This setup enables efficient and user-friendly querying of HDFC insurance policy details while maintaining room for iterative improvements.  
