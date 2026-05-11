Inference means using the model. One user, giving one query and model taking it token by token, and producing output token by token, in between waiting on memory on every step. It stores this memory in KV cache.

It is a memory bound processs.