**Each input of a super-neuron in a dataflow matrix machine can be considered to be an attention device combining incoming linear streams together.**

Unlike Transformers which tend to be very regular, DMMs are quite flexible, and they can be feed-forward or recurrent. 
The trade-off is that training is much less trivial because of this flexibility.

This link between DMMs and attention-based models including Transformers inspired us to research flexible neural machines involving matrix multiplication, 
and we were able to obtain interesting preliminary results, see my 
[JuliaCon 2021 poster](https://github.com/anhinga/JuliaCon2021-poster)
