Here is a copy of the settings we used for fine-tuning in our thesis and RAG (Retrieval-Augmented Generation) implementation. Fine-tuning is a process where a pre-trained model, such as BERT, is further trained on a specific, smaller dataset that is tailored to the task at hand. This allows the model to adapt its general knowledge to a particular domain, improving its ability to perform specific tasks more effectively.

In the context of our work, fine-tuning involves taking BERT, which has already been trained on a vast amount of general language data, and adjusting its parameters so that it can better understand and respond to domain-specific terminology and nuances. This process enables the model to recognize specialized words, phrases, and patterns that are unique to our field of study, ensuring more accurate predictions and insights for our specific task.

For the fine-tuning process, we set several key hyperparameters that were crucial for optimizing model performance:

Epochs: We selected 6 epochs for training, meaning the model processed the entire training dataset 6 times. This number of epochs was chosen after monitoring the training and validation losses, which indicated that 6 epochs provided a good balance between sufficient learning and avoiding overfitting (where the model becomes too focused on the training data and performs poorly on new data).

Batch Size: A batch size of 8 was used, which means that the model processed 8 training examples at a time before updating its weights. Smaller batch sizes generally allow the model to update its weights more frequently, which can lead to faster learning and better generalization. However, smaller batches also introduce more noise, which can help prevent overfitting and improve the model's performance on unseen data.

Learning Rate: We set the learning rate to 2e-5, which controls the size of the updates made to the model’s weights during training. A smaller learning rate helps ensure that the updates are more stable and less likely to cause the model to overshoot optimal solutions. This is particularly important for fine-tuning, as we want to make gradual adjustments to the model's parameters without drastically changing its pre-trained knowledge.

Optimizer (AdamW): The AdamW optimizer was chosen because it is an efficient method for adjusting the weights of the model. It combines the benefits of both the Adam optimizer (which adapts learning rates based on individual parameters) and weight decay, a form of regularization that helps prevent overfitting by penalizing overly large weights. This optimizer is particularly well-suited for fine-tuning models like BERT