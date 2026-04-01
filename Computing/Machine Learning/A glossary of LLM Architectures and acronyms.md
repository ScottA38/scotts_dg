po
### The **GLUE** evaluation framework

	=> A sort of 'LLM agility obstacle course' (paraphrased)
	
['Glue'](](https://h2o.ai/wiki/glue/)) _aliases_ General Language Understanding-Evaluation framework is a series of tasks to road-test LLMs on a range of use cases.

Standardised tests allow researchers to measure and compare the efficacy of different LLM models within different operational contexts

Consists of 9 (representative) NLP use cases, i.e:
- Sentence Classification
- Sentiment Analysis
- Question Answering

Each task consists of:
- Training set
- Development set
- Evaluation set

Fosters collaboration between researchers through standardisation.

### RAG (Retrieval-Augmented Generation)

RAG helps to eliminate uncertainty around information relevance in an LLM response due to the inherent gap between dataset publication and the current date.

RAG intercepts LLM requests, searches relevant resources within it's assigned catalogue of external data, and attaches this to the original user request, like an appendix.

RAG helps LLMs to balance their reasoning against data outside of their training set, to try to ensure that outdated data is not presented as fact

**RAG process:** 

1. User request is sent (prompt submitted)
2. Request to LLM is intercepted and converted to vector format ([according to AWS](https://aws.amazon.com/what-is/retrieval-augmented-generation/) )
3. External data is sourced from a vector database (according to AWS)
4. External data injected into original prompt via prompt engineering techniques 

#### RAG Context

RAG is primarily focussed on research-based tasks, or tasks where relevancy is critical. This means that the quality and volume of content inspected is highly important.


#### Semantic search

Semantic search allows LLMs to connect disparate information resources.

With RAG's search mechanisms, individual words will be identified. Synonyms, word omissions and typo tolerances will be applied in a sort of 'best-fit' approach (_paraphrased_).

Semantic search will consider factors such as:

- **Geographical location**
	- _i.e_: Soccer -> 🇺🇸, Football -> 🇬🇧
- **Word ordering**
	- _i.e_: Consider "chocolate milk." A semantic search engine will distinguish between "chocolate milk" and “milk chocolate.” Though the keywords in the query are the same, the order in which they are written affects the meaning. As humans, we understand that milk chocolate refers to a variety of chocolate, whereas chocolate milk is chocolate-flavored milk. [elastic.co](https://www.elastic.co/what-is/semantic-search)
- **User's past search history**
	- _i.e_: Locations you have searched from in the past (?)

Semantic search is highly context-sensitive - it uses mechanisms to interpret _user intent_, as opposed to keyword-matching.

> "Car" is no longer only matched to "car" or "cars," it is also matched to "driver," "insurance," "tires," "electric," "hybrid," and so on because those words are connected to the vector of "car."

Semantic search is a knowledge-base preparation technique, essentially sewing together or enmeshing different, unrelated knowledge sources. 

"Semantic search enhances RAG results for organizations wanting to add vast external knowledge sources to their LLM applications" ...[according to AWS](https://aws.amazon.com/what-is/retrieval-augmented-generation/)


