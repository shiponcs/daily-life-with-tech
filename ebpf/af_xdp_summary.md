- XDP in AF_XDP: Using XDP redirect mechanism, we can redirect frames to af_socker like redirecting to other net devices. AF_XDP is another target for redirect.
-  In typical INET sockets, each send/recv is a syscall and syscall is expensive. 
Steps:
1. Call `socket()` with formats/address family `AF_XDP`
2. Create Buffer
3. setsocketopt for XDP_MEME
4. setsocketopt for XDP_RX_RING
5. setsocketopt for XDP_TX_RING
6. mmap the buffer to kernel tx/rx
7. Bind to a if and queue by id
8. then read, process, send
   
