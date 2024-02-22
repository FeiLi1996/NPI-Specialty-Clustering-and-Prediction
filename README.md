# NPI-Specialty-Clustering-and-Prediction

## About NPI Specialty Clustering

Knowing a NPI's Specialty can give lots of information. For instance, we would expect a cardiologist to have a different prescribing behavior than a psychiatrist.Knowing how  NPIs act based on their specialties can be useful for many reasons. Some reasons are fraud detection and marketing campaigns. This can be helpful in fraud detection because if  a cardiologist is prescribing high percentages of adderall or meth, then we can predict that this person is probably a fraud. If we are promoting a weight loss drug, we would want to target primary care specialties like family medicine, etc . We wouldn't want to target pulmonologist and urologist as their prescribing behaviors are unlikely related to weight loss.

However, sometimes the specialty is unknown or it is known but not very helpful. For example, Nurse Practioner(NP) and Physician assistant(PA) often specialize in a particular field like pain , cardiac stuff or pediatric. Unfortunately healthcare data don't  really track their specialties so they just list them as NP or PA. This is an issue because if a NP prescribes lots of opioid, should we flag the NPI as guaranteed fraud? What if the NP works in a surgical clinic? Furthermore,  if NPs/PAs make up 50% of a local clinical dataset, should we advertise our weight loss medication  to them? What if the local clinic only focuses on addiction therapy? Then the marketing team would lose lots of money because the investment would be wasted as addiction therapy isn't related to weight loss.

## About the Data set

This  synthetic dataset gives information about the doctors and their prescriptions. There are only 4 columns. We will use it to visualize their prescription behaviors in a 2D graph via PCA. Then we will try to cluster similiar doctors with or without their reliable specialty titles based on their prescription behaviors with kmeans.

* Attribute Information
  +	rx_id 
      +	__Meaning__: The unique ID for the prescription
      +	__Variable Type__: character
      +	__Possible values__:  any number from 1 to infinity
  +	doctor_id 
      +	__Meaning__: The unique ID of a  doctor 
      +	__Variable Type__: character
      +	__Possible values__:  any number from 1 to infinity
  +	specialty 
      +	__Meaning__: a branch of medicine the clinician is involved with
      +	__Variable Type__: character
      +	__Possible values__:  'cardiologist' , 'general practice', 'nurse practioner',etc
  +	therapeutic_labeling 
      +	__Meaning__: the clinical category of the prescription drug
      +	__Variable Type__: character
      +	__Possible values__:  'ocular' , 'bronchodilator', 'cardiology',etc  
	  
	  



## Cluster Graph
![Alt text](PCA%20with%20kmeans%20NPI%20Specialty.PNG)


## Conclusion
Using PCA, we were able to visualize Doctors' prescription behavior in a 2D graph. Using k-means , we can cluster doctors with similiar prescribing behavior together. This is super helpful when a doctor's specialty is unknown or vague like nurse practioner. For example: In the graph above , we can see that nurse practioner 5 is clustered(purple) near the cardiologists. This means that nurse practioner 5 must be involved with drugs related to the heart. If we were doing a campaign to promote a specialty drug related to the heart, we can safely assume that it is great to target this nurse practioner 5. Without PCA and kmeans, we wouldn't be as confident to target a clinician with specialty title nurse practioner because it is a vague title. Without PCA and kmeans, it is still possible to understand doctors prescription but this would require a person to manually check each doctors prescription and this could take a very long time.
