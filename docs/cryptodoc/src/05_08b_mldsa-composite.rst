.. _pubkey/mldsa_composite:

ML-DSA-Composite
================

In the module ``ML-DSA-composite`` Botan implements the "ML-DSA with traditional
algorithm" composite signature algorithms defined in
draft-ietf-lamps-pq-composite-sigs-19. This upcoming
standard defines composite signature algorithms that have the property that
their security is guaranteed as long as at least one of the two component
algorithms remains secure.



Parameter Support
-----------------

All parameters from draft-ietf-lamps-pq-composite-sigs are supported:

 - MLDSA44-RSA2048-PKCS15-SHA256
 - MLDSA65-RSA3072-PKCS15-SHA512
 - MLDSA65-RSA4096-PKCS15-SHA512
 - MLDSA44-RSA2048-PSS-SHA256
 - MLDSA65-RSA3072-PSS-SHA512
 - MLDSA65-RSA4096-PSS-SHA512
 - MLDSA87-RSA3072-PSS-SHA512
 - MLDSA87-RSA4096-PSS-SHA512
 - MLDSA44-ECDSA-P256-SHA256
 - MLDSA65-ECDSA-P256-SHA512
 - MLDSA65-ECDSA-P384-SHA512
 - MLDSA65-ECDSA-brainpoolP256r1-SHA512
 - MLDSA87-ECDSA-P384-SHA512
 - MLDSA87-ECDSA-brainpoolP384r1-SHA512
 - MLDSA87-ECDSA-P521-SHA512
 - MLDSA44-Ed25519-SHA512
 - MLDSA65-Ed25519-SHA512
 - MLDSA87-Ed448-SHAKE256

Note that the availability of each parameter set depends not only on the
availability of the module ``ML-DSA-Composite``, but also on the respective
traditional component algorithm in Botan's build configuration.

API
---

:ref:`pubkey/mldsa_composite/files` lists the header files that are part of Botan's public API.

.. _pubkey/mldsa_composite/files:

.. table:: ML-DSA-Composite Header File Locations

   +-----------------------------------------------------------------------+-----------------------------------------+
   |Header File                                                            |Purpose                                  |
   +=======================================================================+=========================================+
   |``pubkey/mldsa-composite/mldsa_comp.h``                                |Public and Private key objects           |
   +-----------------------------------------------------------------------+-----------------------------------------+
   |``pubkey/mldsa-composite/mldsa_comp_parameters.h``                     |Parameter type for ML-DSA-Composite      |
   +-----------------------------------------------------------------------+-----------------------------------------+

Note that the context parameter is not available as an input parameter and thus
signature and verification operations will always use the empty context.,
