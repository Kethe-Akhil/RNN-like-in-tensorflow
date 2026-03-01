# RNN-like-in-tensorflow
Implemented full fledged RNN from scratch just by using and numpy and pandas 
I'm implemented the Many to one RNN sequential model from scratch without using tensorflow frame work and keras api 
in forward pass we do caluclate the ht=tanh(xt@wx.T+ht@wh.T+b)
so then wx is the weight matrix with shape = no.of hidden_size X vacubluary length,wh=hidden_size X hidden_size,ht=batch_size X hidden_size
so the t=total no.words (example [i love ml]=[1,2,3]=[1,0,0],[0,1,0],[0,0,1] so t=3 
when t=0 so it will take all samples of the first word which is padded equal to vaub lenght 
then it will perform the matrix multiplication then hidden states weight is wh will get multiplied by the previous hidden states and then after completing we get the all hiddestates values 
so, the multiplicaton is here is too beautiful because the when we get multiply the firstword we get a the values for the hiddden state one then while we are doing it for the second word then the values og hidden state one will get added to the present hidden state it will maintian the context of the words 
After doing that all we get all state values the from there we do consider the hidden state final values which we done for the last word because here it will consist o the context all words in that sentences and we do the matrix mul z=wout(hidden_size X classes)@hidden_sstate[:,-1,:]
On the implement the softmax over the z then we get  the y_pred
Then caluclate the error then we go with the backpropagation the backpropagation till gradientswout is like normal but from the gradients doul/doua3 which from final hidden state values to intial it will be of BPTT .So at every timestamp the weights will keep on updating till to the 1st hidden state 
