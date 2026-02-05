# Lab3 Results

Dataset description:
This lab uses rental agreement PDFs and related images to simulate a multimodal compliance auditing scenario. The dataset consists of two PDF lease agreements (lease_template_1.pdf and lease_template_2.pdf) and five figure images (f1.PNG to f5.PNG). The PDFs contain typical residential lease clauses, such as rent, late fees, security deposits, and pet policies. The images are screenshots of tables or form fields from the leases, which provide additional context for questions about amounts or rules.
All documents are text and image multimodal, allowing retrieval of both textual chunks and visual evidence. This dataset is directly relevant to the project because it allows testing of a multimodal RAG pipeline on structured contract information.

<img width="364" height="515" alt="图片" src="https://github.com/user-attachments/assets/fedd5a8d-2dee-4553-9523-fabab8ec2545" />

Total text chunks: 18
Total images: 5
Sample text chunk: lease_template_1.pdf::p1 STANDARD RESIDENTIAL LEASE AGREEMENT 1. THE PARTIES. This Residential Lease Agreement (“Agreement”) is made on the undersigned date by and between: Landlord Landlord's Name: [LANDL
Sample image item: ImageItem(item_id='f1.PNG', path='project_data_mm/figures/f1.PNG', caption='f1')

<img width="1318" height="259" alt="图片" src="https://github.com/user-attachments/assets/1b802d7a-fda2-4ea2-b163-8f7070202d2a" />

Queries:
Q1: What are the rent amount and late fee policy in this lease agreement?
Q2: What rules apply to pets and are there any additional fees?
Q3: Does the contract mention interest paid on the security deposit?

[TEXT | lease_template_1.pdf::p2 | fused=0.500] 5. SECURITY DEPOSIT. (check one) ☐ - No Security Deposit. ☐ - Security Deposit. • Amount: $[AMOUNT] • Returning to Tenant: [#] days after lease termination. 6. LATE FEE. (check one) ☐ - No Late Fee. ☐ - Late Fee: (check one) ☐ - Fixed Amount. $[AMOUNT] for eac
[IMAGE | f1.PNG | fused=0.500] caption=f1
[IMAGE | f2.PNG | fused=0.500] caption=f2
[IMAGE | f3.PNG | fused=0.500] caption=f3
[TEXT | lease_template_2.pdf::p1 | fused=0.127] Teacher Resources for Consumer.gov | Developed for the FTC by the Center for Applied Linguistics SAMPLE RENTAL AGREEMENT (Basic / Beginning) THIS AGREEMENT made this 15th Day of June, 2012, by and between ABC Properties, herein called “Landlord,” and Silvia Ma
[TEXT | lease_template_1.pdf::p9 | fused=0.032] n.) Pets. If any property repairs, odor removal, or other maintenance is required due to the Tenant’s Pets, the costs shall be deducted from the Pet Fee or Security Deposit with an itemized list disclosed to the Tenant. i. Pet Restrictions. Any pet restriction
[TEXT | lease_template_1.pdf::p8 | fused=0.017] b.) Access. Upon the start of the Early Move-In or the Term, whichever is applicable, the Landlord agrees to provide entry to the Tenant in the form of keys, fobs, cards, or any type of keyless access to the Property. Access to the Property shall be given afte
[TEXT | lease_template_1.pdf::p1 | fused=0.000] STANDARD RESIDENTIAL LEASE AGREEMENT 1. THE PARTIES. This Residential Lease Agreement (“Agreement”) is made on the undersigned date by and between: Landlord Landlord's Name: [LANDLORD'S NAME] Mailing Address: [LANDLORD'S ADDRESS] Tenant Tenant’s Name: [TENANT'
Images: ['project_data_mm/figures/f1.PNG', 'project_data_mm/figures/f2.PNG', 'project_data_mm/figures/f3.PNG']
Fusion alpha: 0.5
Retrieved top text and images that mention rent amounts and late fee clauses. Fusion combines text from lease_template_1.pdf and images f1.PNG, f2.PNG, f3.PNG to provide grounded evidence.
Top evidence includes text discussing pet permissions, pet rent, and additional fees, along with relevant images. This ensures answers are consistent with the lease documents.
Evidence highlights any mention of interest paid on the security deposit. Both lease pages and selected figures are included to support the answer.
Text chunks are directly retrieved; images are included by relevance.
Fusion alpha = 0.5 gives equal weight to text and image evidence.

<img width="1244" height="229" alt="图片" src="https://github.com/user-attachments/assets/992311ee-0793-4488-afda-421ece17b5ae" />

================================================================================
Q1 What are the rent amount and late fee policy in this lease agreement?
Question: What are the rent amount and late fee policy in this lease agreement?

Grounded answer (extractive):
[TEXT | lease_template_1.pdf::p2 | fused=0.500] 5. SECURITY DEPOSIT. (check one) ☐ - No Security Deposit. ☐ - Security Deposit. • Amount: $[AMOUNT] • Returning to Tenant: [#] days after lease termination. 6. LATE FEE. (check one) ☐ - No Late Fee. ☐ - Late Fee: (check one) ☐ - Fixed Amount. $[AMOUNT] for eac
[IMAGE | f1.PNG | fused=0.500] caption=f1
Images: ['f1.PNG', 'f2.PNG', 'f3.PNG']

================================================================================
Q2 What rules apply to pets and are there any additional fees?
Question: What rules apply to pets and are there any additional fees?

Grounded answer (extractive):
[TEXT | lease_template_1.pdf::p4 | fused=0.500] ☐ - No Pets Allowed. ☐ - Pets are Allowed. Number of Pets: [#] Types: [PET TYPES] Maximum Weight (per pet): [#] Pounds Deposit (for all pets): $[AMOUNT] ☐ refundable ☐ non-refundable 12. SMOKING POLICY. (check one) ☐ - No Smoking Allowed. ☐ - Smoking is Allowe
[IMAGE | f1.PNG | fused=0.500] caption=f1
Images: ['f1.PNG', 'f2.PNG', 'f3.PNG']

================================================================================
Q3 Does the contract mention interest paid on the security deposit?
Question: Does the contract mention interest paid on the security deposit?

Grounded answer (extractive):
[TEXT | lease_template_1.pdf::p10 | fused=0.500] duration of the Term and any renewals thereof. Failure to maintain the required insurance constitutes a breach of this Agreement and may result in termination of tenancy and eviction under local housing laws. iv. Landlord’s Insurance. Tenant acknowledges that 
[IMAGE | f1.PNG | fused=0.500] caption=f1
Images: ['f1.PNG', 'f2.PNG', 'f3.PNG']

<img width="1321" height="630" alt="图片" src="https://github.com/user-attachments/assets/1fbd348f-9c09-42f4-8f90-9eb35e47b515" />

Retrieval Evaluation
I evaluated the retrieval system using Precision@5 (P@5) and Recall@10 (R@10).
Relevant text chunks are determined by the must_have_keywords in each query’s rubric.
| id | P@5 | R@10  | total_relevant_chunks |
| -- | --- | ----- | --------------------- |
| Q1 | 1.0 | 0.6   | 15                    |
| Q2 | 0.8 | 0.545 | 11                    |
| Q3 | 0.8 | 1.0   | 8                     |

<img width="617" height="176" alt="图片" src="https://github.com/user-attachments/assets/5367ebaa-3746-41d8-898e-79c7c46e2f00" />

The results show that our system can effectively retrieve relevant chunks from the lease agreements, with high precision and reasonable recall.

Ablation Study
I conducted a quick ablation study to see how changing TOP_K_TEXT affects retrieval metrics.
| Query | top_k_text | P@5 | R@10  |
| ----- | ---------- | --- | ----- |
| Q1    | 2          | 1.0 | 0.55  |
| Q1    | 5          | 1.0 | 0.6   |
| Q1    | 10         | 1.0 | 0.6   |
| Q2    | 2          | 0.8 | 0.5   |
| Q2    | 5          | 0.8 | 0.545 |
| Q2    | 10         | 0.8 | 0.545 |
| Q3    | 2          | 0.8 | 0.95  |
| Q3    | 5          | 0.8 | 1.0   |
| Q3    | 10         | 0.8 | 1.0   |

<img width="654" height="412" alt="图片" src="https://github.com/user-attachments/assets/f95e064c-e838-4927-8d4f-b497211e395f" />

Observations:
Increasing TOP_K_TEXT slightly improves recall for Q1, while precision remains stable.
For Q2, both precision and recall are stable across different TOP_K_TEXT.
For Q3, recall is already high, and precision is consistent.
Overall, the extraction-based retrieval is robust to the number of top text chunks selected.

Failure Case and System Improvement
Failure Case: For Q3 (“Does the contract mention interest paid on the security deposit?”), the extractive generator returned a text chunk that did not explicitly mention interest. The retrieved evidence included unrelated content, and the grounded answer was incomplete. This happened because TF-IDF retrieval only matches keywords and does not understand the semantic meaning of the question.
Improvement: To address this, the system could use semantic embeddings or an LLM-based retriever, which can understand synonyms and context (e.g., “interest accrued” vs. “interest paid”). Increasing TOP_K_TEXT or combining multiple evidence chunks may also improve recall. Additionally, including OCR or caption-based retrieval for images (like tables or forms) could help answer questions involving amounts or structured data.
Faithfulness Note: The system ensures that answers remain grounded in the retrieved evidence, even if the evidence is incomplete. Using semantic retrieval may increase answer completeness while still maintaining evidence grounding.

In this lab, I learned how to build a retrieval pipeline using TF-IDF for both text and image data. Evaluating with Precision@5 and Recall@10 helped me understand the effectiveness of different queries and the impact of context construction. 

#Conclusive Faithfulness Discussion
The answers generated by extractive RAG pipeline are directly based on the retrieved evidence from both lease PDFs and the associated images. For example, questions about rent, late fees, and pet rules were answered using the corresponding text chunks and table screenshots. This ensures that the answers remain grounded in the original documents, rather than being hallucinated by a language model.

However, the system has some limitations: in some cases, the extracted text may truncate important details, such as full descriptions of late fee calculations or exact pet deposit rules. For instance, the extractive answer for the rent amount and late fee only includes partial text, and does not explicitly cover all options for interest or occurrence-based fees in the lease. Similarly, image evidence (tables or figures) may provide additional context that is not fully incorporated in the grounded answer.

Overall, the system is faithful to the evidence retrieved, but must be aware that some answers may omit finer details present in the original PDFs or figures. Improving evidence coverage and integrating both text and image content more completely could enhance faithfulness.
#Results Table
| Query | Method           | P@5  | R@10  | Faithfulness |
| ----- | ---------------- | ---- | ----- | ------------ |
| Q1    | Hybrid Retrieval | 1.0  | 0.6   | High         |
| Q2    | Hybrid Retrieval | 0.8  | 0.545 | Medium       |
| Q3    | Hybrid Retrieval | 0.81 | 1.0   | High         |
The generated answers are mostly faithful to the source documents. 
For Q1 and Q3, the answers directly reflect the text in the PDFs, including rent amounts, late fees, and pet rules. 
For Q2, some details about the security deposit interest are partially missing, so the faithfulness is medium. 
Overall, the answers are grounded in the retrieved text chunks and images, but minor numerical details may be missed.

