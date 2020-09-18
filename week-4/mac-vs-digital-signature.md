# MAC vs Digital Signature

### Identify a case when you will use MAC over a digital signature and explain the reason.

Performance alone is a reason to use MAC. Consider a TLS connection. For every packet, the 
receiving party needs to verify that the packet wasn't modified in transit by a 
man-in-the-middle attacker. So for every packet, the sender needs to calculate a 
MAC/signature and the receiver needs to verify it.

### Identify a case when you will use a digital signature over MAC and explain the reason.

MAC Does not provide non-repudiation whereas Digital Signature provides non-repudiation integrity as
well. So, when creating an application for a Bank or a Stock Brokerage Firm where a user should not 
be able to repudiate messages such as money transfer or stock buy/sell orders, hence in these 
applications we should use Digital Signatures.
