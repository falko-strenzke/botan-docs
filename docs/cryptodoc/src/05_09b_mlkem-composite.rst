.. _pubkey/mlkem-composite:

ML-KEM-Composite
================


In the module ``ML-KEM-composite`` Botan implements the "ML-KEM with traditional
algorithm" composite KEM algorithms defined in
draft-ietf-lamps-pq-composite-kem. This upcoming standard defines composite KEM
algorithms that have the property that their security is guaranteed as long as
at least one of the two component algorithms remains secure.


Parameter Support
-----------------

All parameters from draft-ietf-lamps-pq-composite-kem are supported:

 - MLKEM768-RSA2048-SHA3-256
 - MLKEM768-RSA3072-SHA3-256
 - MLKEM768-RSA4096-SHA3-256
 - MLKEM768-X25519-SHA3-256
 - MLKEM768-ECDH-P256-SHA3-256
 - MLKEM768-ECDH-P384-SHA3-256
 - MLKEM768-ECDH-brainpoolP256r1-SHA3-256
 - MLKEM1024-RSA3072-SHA3-256
 - MLKEM1024-ECDH-P384-SHA3-256
 - MLKEM1024-ECDH-brainpoolP384r1-SHA3-256
 - MLKEM1024-X448-SHA3-256
 - MLKEM1024-ECDH-P521-SHA3-256


Note that the availability of each parameter set depends not only on the
availability of the module ``ML-KEM-Composite``, but also on the respective
traditional component algorithm in Botan's build configuration. 

API
---

Table :ref:`pubkey/mlkem_composite/files` lists the header files that are part of Botan's public API.

.. _pubkey/mlkem_composite/files:

.. table:: ML-KEM-Composite Header File Locations

   +-----------------------------------------------------------------------+-----------------------------------------+
   |Component                                                              |Purpose                                  |
   +=======================================================================+=========================================+
   |``pubkey/mlkem-composite/mlkem_comp.h``                                |Public and Private key objects           |
   +-----------------------------------------------------------------------+-----------------------------------------+
   |``pubkey/mlkem-composite/mlkem_comp_parameters.h``                     |Parameter type for ML-KEM-Composite      |
   +-----------------------------------------------------------------------+-----------------------------------------+

