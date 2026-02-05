# Lab3 Results

Dataset description:
This lab uses rental agreement PDFs and related images to simulate a multimodal compliance auditing scenario.
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

