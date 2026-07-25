Final training loss (4 d.p.):
0.2969

Total trainable parameters:
65

OpenCode model/provider:
Chatgpt 5

Reflection (max 250 words):
One thing OpenCode helped with:

OpenCode helped me understand the structure of two layer neural network using NumPy. It explained the forward pass, backpropagation, and how to update the weight and bias during training.

One thing it got wrong or you had to fix:

I did not had to fix anything in the code as it was provided directly. I understood that the network is only using NumPy library and while running the code I observed that the loss is consitently decreasing with increase in number of epochs. By the given plot I ensured that loss is inversely proportional to epochs.

How you verified the final notebook:

I ran every notebook cell without any errors. Also I tried changing the hidden size to check how the graph changes according to the data. When hidden size was 16 the total trainable parameters were 65, I changed hidden size to 32 the trainable parameters were 129 and epoch remained unchanged throughput the process. I saw slight difference in the plot.With all these changes I reviewed implementation to ensure it met all the assignment requirements.
